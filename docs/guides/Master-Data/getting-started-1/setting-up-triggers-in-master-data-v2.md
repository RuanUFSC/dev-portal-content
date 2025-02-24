---
title: "Setting up triggers in Master Data v2"
excerpt: "Learn how to create and configure triggers in Master Data v2 to automate actions after a document update."
slug: "setting-up-triggers-in-master-data-v2"
hidden: false
createdAt: "2022-07-05T16:11:49.082Z"
updatedAt: "2022-10-28T14:34:21.479Z"
---

This guide will teach you how to create and configure triggers in **Master Data v2** to automate actions after a document update. 

A **Master Data** trigger is an [action](#action) executed immediately after a document is inserted or updated.

**Master Data v2** supports the following types of triggers:

- Send an HTTP request.
- Send an email.
- Send email using [Message Center](https://help.vtex.com/en/tutorial/understanding-the-message-center--tutorials_84) template.
- Save data to another data entity.

> ⚠️ This article is about **Master Data v2** triggers. If you want to use **Master Data v1**, check the [How to create a trigger in **Master Data v1**](https://help.vtex.com/en/tutorial/creating-trigger-in-master-data--tutorials_1270) guide.

## Before you begin

You may use **Master Data v2** triggers to create and add hooks to VTEX first-party apps. To do that, [Create a new JSON schema](https://developers.vtex.com/docs/api-reference/master-data-api-v2#put-/api/dataentities/-dataEntityName-/schemas/-schemaName-) for the data entity used by the app and then follow the instructions below.

## Step by step

Each trigger is described as an item of the array `v-triggers` of a [JSON schema](https://developers.vtex.com/vtex-rest-api/docs/master-data-schema-lifecycle). If you want to create a trigger for a data entity with no associated schema, you may [create a new schema](https://developers.vtex.com/docs/api-reference/master-data-api-v2#put-/api/dataentities/-dataEntityName-/schemas/-schemaName-) with the trigger settings according to what is described below. 

To create a new trigger in an existing schema, follow these steps:

1. [Get the schema](https://developers.vtex.com/docs/api-reference/master-data-api-v2#get-/api/dataentities/-dataEntityName-/schemas/-schemaName-) associated with the data entity you wish to add a trigger to.
2. Copy the JSON schema from the response and create a new item in the `v-triggers` array, configuring the properties according to your desired behavior. See the [JSON properties](#json-properties) and [Example](#example) sections for more information.
3. Send the edited schema as the body to the [Save schema by name](https://developers.vtex.com/docs/api-reference/master-data-api-v2#put-/api/dataentities/-dataEntityName-/schemas/-schemaName-) endpoint.

> To edit Master Data v2 triggers, follow the steps described above, editing the properties you wish instead of creating a new array item.

### JSON Properties

| Property  | Type | Description                                  |
|-----------|------|---------------------------------------------|
| `name`      |`string`| A descriptive name for your trigger, limited to 100 characters. |
| `active`    | `boolean`| Whether the trigger is enabled (`true`) or disabled (`false`). |
| `condition` | `string` | A rule that validates the document before executing the trigger. See the [`condition`](#condition) section for more information. |
| `runAt`     | `object` | The scheduled date to execute the action. See the [`runAt`](#runAt) section for more information.    |
| `weight`    |`integer` | Percentage value used for A/B testing. See the [Setting up an A/B test with Master Data trigger](https://help.vtex.com/en/tutorial/setting-up-a-b-test--4xFzBMHYty6gmEosWGWMC0#) article for more information.|
| `retry`     | `object` | Defines the retry policy, specifying the number of attempts and delay between them. See the [`retry`](#retry) section for more information.        |
| `action`    | `object` | The action that will be executed. See the [`action`](#action) section for more information.                 |

#### `condition`

The rule is the same as Master Data API v2's [Search documents](https://developers.vtex.com/docs/api-reference/master-data-api-v2#get-/api/dataentities/-dataEntityName-/search) route. Example: `status=ready-for-handling`

To get further information, check the [Search documents](https://developers.vtex.com/docs/api-reference/master-data-api-v2#get-/api/dataentities/-dataEntityName-/search) endpoint reference.

#### `runAt`

In case of scheduling an action in the future, you can use the `runAt` property. See the examples below:

- Schedule the execution 10 minutes later.

```json
    {
    	"dateTime": "now",
    	"increment": {
    		"addMinutes": 10
    	}
    }
```

- Schedule the execution six months after the field value `createdIn`.

```json
    {
    	"dateTime": "{!createdIn}",
    	"increment": {
    		"addMonths": 6
    	}
    }
```

#### `retry`

By default, VTEX Master Data makes three attempts in an interval of 10 minutes. Use this property to override such behavior. See the example below of five attempts in an interval of 30 minutes.

```json
    {
    	"times": 5,
    	"delay": {
    		"addMinutes": 30
    	}
    }
```

#### `action`

Define the action to be executed, which can be one of the following types:  

<details>
<summary>Call an HTTP request</summary>

```json
    {
    	"type": "http",
    	"uri": "http://mydomain.com/api/test",
    	"method": "POST",
    	"headers": {
    		"content-type": "application/json"
    	},
    	"body": {
    		"id": "{!id}",
    		"test": "TestValue",
    		"count": 25
    	}
    }
```

</details>

<details>
<summary>Send an email</summary>
    
```json
{
    "type": "email",
    "provider": "default",
    "subject": "My email with VTEX Master Data",
    "to": [
        "{!email}",
        "test@email.com"
    ],
    "bcc": [
        "myemail@test.com"
    ],
    "replyTo": "noreply@company.com",
    "body": "My email with document {!id}."
}
```

</details>

<details>
<summary>Send an email action using a [Message Center](https://help.vtex.com/en/tutorial/understanding-the-message-center--tutorials_84) template.</summary>

```json
    {
        "type": "t-email",
        "template": "template-name",
        "provider": "default",
        "subject": "My template email with VTEX Master Data",
        "to": [
            "{!email}",
            "test@email.com"
        ],
        "bcc": [
            "myemail@test.com"
        ],
        "replyTo": "noreply@company.com",
         "body": {
                        "firstName": "{firstName}",
                        "email": "{email}",
                        "id": "{!id}",
                        "clientName": "{!clientProfileData.firstName} {!clientProfileData.lastName}",
                        "ownerListName": "{!customData.customApps[0].fields.ownerListName}",
                        "ownerListEmail": "{!customData.customApps[0].fields.ownerListEmail}",
                        "items": "{!items}",
                        "openTextField": "{!openTextField.value}"
                    }
    }
```

</details>

<details>
<summary>Save a document to another data entity.</summary>
    
```json
    {
    	"type": "save",
    	"dataEntity": "copy",
    	"json": {
    		"id": "{!id}",
    		"message": "{!message}",
    		"custom": "created/updated by VTEX Master Data triggers"
    	}
    }
```

</details>


### Example

```json
{
    "properties": {},
    "v-triggers": [
        {
            "name": "copy-document",
            "active": true,
            "condition": "status=window-to-cancel",
            "action": {
                "type": "save",
                "dataEntity": "copy",
                "json": {
                    "id": "{!id}",
                    "message": "{!message}",
                    "custom": "created/updated by VTEX triggers"
                }
            },
            "retry": {
                "times": 5,
                "delay": {
                    "addMinutes": 30
                }
            }
        }
    ]
}
```
