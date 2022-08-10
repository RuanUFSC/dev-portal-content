---
title: "Logo"
slug: "localizaseminovoshom-store-components-custom-logo"
excerpt: "localizaseminovoshom.store-components-custom@3.165.1"
hidden: true
createdAt: "2022-08-02T18:04:01.672Z"
updatedAt: "2022-08-09T14:37:37.924Z"
---
`Logo` is a VTEX block responsible for displaying an image logo for the store header.

![logo](https://user-images.githubusercontent.com/52087100/70247921-f1d43a80-1758-11ea-853e-065dfed06c73.png)

## Configuration

1. Import the `vtex.store-component` app to your theme's dependencies in the manifest.json;

```json
 "dependencies: {
    "vtex.store-components": "3.x"
  }
 ```
  
2. Add the `logo` block into your [Header](https://vtex.io/docs/components/all/vtex.store-header/). For example:

```json
"header.full": {
  "blocks": [
    "login",
    "minicart",
    "logo",
    "search-bar",
    "menu-link",
    "telemarketing",
    "category-menu"
  ]
},

 "logo": {
    "props": {
      "width": 132,
      "height": 32,
      "mobileWidth": 90,
      "mobileHeight": 32
    }
  }
}

```


| Prop name | Type | Description | Default value |
| --------- | ---- | ----------- | ------------- |
| `title` | `String!` | The image alt description | `VTEX logo` |
| `color` | `String` | The image fill color | `#F71963` |
| `showLabel` | `Boolean` | Set the label visibility  | true |
| `width` | `Number` | The logo image width | `493` |
| `height` | `Number` | The logo image height | `177` |
| `url` | `String` | The image url | - |
| `href` | `String` | Image link | - |

## Customization

In order to apply CSS customizations in this and other blocks, follow the instructions given in the recipe on [Using CSS Handles for store customization](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization).

| CSS Handles | 
| ---------- | 
| `sizeDesktop` | 
| `sizeMobile` | 
| `logoContainer` | 
| `logoImage` |