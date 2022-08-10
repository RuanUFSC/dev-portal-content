---
title: "Info Card"
slug: "localizaseminovoshom-store-components-custom-infocard"
excerpt: "localizaseminovoshom.store-components-custom@3.165.1"
hidden: true
createdAt: "2022-08-02T18:04:01.726Z"
updatedAt: "2022-08-09T14:37:38.040Z"
---
The `infoCard` block allows you to **display content combining image and text** in your store.

![image](https://user-images.githubusercontent.com/284515/70229574-4239a100-1735-11ea-9e30-00b286e03f7c.png)

## Configuration

1. Import the `vtex.store-component` app to your theme's dependencies in the `manifest.json`;

```json
  "dependencies": {
    "vtex.store-components": "3.x"
  }
```

2. Add the `info-card` block in your Home page template. Then, declare it in the same file. For example:

```json
  "info-card": {
    "props": {
      "id": "info-card-example",
      "isFullModeStyle": false,
      "textPosition": "left",
      "imageUrl": "https://storecomponents.vteximg.com.br/arquivos/banner-infocard2.png",
      "headline": "Clearance Sale",
      "callToActionText": "DISCOVER",
      "callToActionUrl": "/sale/d",
      "blockClass": "info-card-example",
      "textAlignment": "center"
    }
  },
```

| Prop name | Type | Description | Default value |
| --------- | ---- | ----------- | ------------- |
| `isFullModeStyle` | `Boolean` | If true, image provided will be used as a background image and text will be displayed over it | false |
| `textPosition` | `TextPostionEnum` | Choose in which position of the component text will be displayed, left, center or right | `"left"` |
| `textAlignment` | `TextAlignmentEnum` | Control the text alignment inside component. This prop is ignored if `isFullModeStyle` is true  | `"left"` |
| `headline` | `String` | Text to be used as headline. If not provided, it will not be rendered | `null` |
| `subhead` | `String` | Text to be displayed underneath the headline. If not provided, it will not be rendered | `null` |
| `callToActionMode` | `CallToActionEnum` | Set Call to Action component mode | `"button"` |
| `callToActionText` | `String` | Text to be displayed inside the CTA component | `""` |
| `callToActionUrl` | `String` | URL to be redirected when CTA component is clicked | `""` |
| `imageUrl` | `String` | URL of the image to be used on desktop | `""` |
| `mobileImageUrl` | `String` |  URL of the image to be used on mobile. If you do not provide any, the desktop image url will be used | `null` |
| `blockClass` | `String` | Adds an extra class name to ease styling | `null` |
| `htmlId` | `String` | Adds an ID to the container element | `null` |


- Possible values of `TextPostionEnum`:

| Enum name | Enum value | Description |
| --------- | ---- | ----------- |
| Left | 'left' | Text will be to the left. If `isFullModeStyle` is false, image will be on the right |
| Center | 'center' | Text will be in the center. Not applicable if `isFullModeStyle` is false. |
| Right | 'right' | Text will be to the right. If `isFullModeStyle` is false, image will be on the left |

- Possible values of `CallToActionEnum`:

| Enum name | Enum value | Description |
| --------- | ---- | ----------- |
| None | 'none' | Don't render any Call to Action component  |
| Button | 'button' | Call to Action component will be a button |
| Link | 'link' | Call to Action component will be a text in a link format |

- Possible values of `TextAlignmentEnum`:

| Enum name | Enum value | Description |
| --------- | ---- | ----------- |
| Left | 'left' | Text alignment will be to the left. |
| Center | 'center' | Text alignment will be to the center. |
| Right | 'right' | Text alignment will be to the right. |

## Customization

In order to apply CSS customizations in this and other blocks, follow the instructions given in the recipe on [Using CSS Handles for store customization](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization).

| CSS Handles |
| ---------- |
| `infoCardContainer` |
| `infoCardTextContainer` |
| `infoCardHeadline` |
| `infoCardSubhead` |
| `infoCardCallActionContainer` |
| `infoCardCallActionText` |
| `infoCardImageContainer` |
| `infoCardImage` |