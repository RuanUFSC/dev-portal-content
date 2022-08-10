---
title: "Image"
slug: "localizaseminovoshom-store-components-custom-image"
excerpt: "localizaseminovoshom.store-components-custom@3.165.1"
hidden: true
createdAt: "2022-08-02T18:04:01.788Z"
updatedAt: "2022-08-09T14:37:37.890Z"
---
The `Image` is a VTEX block that allows to **add any image** in the store. 

![image](https://user-images.githubusercontent.com/284515/70230392-f982e780-1736-11ea-921b-e83208e80620.png)

## Configuration

1. Import the `vtex.store-component` app to your theme's dependencies in the `manifest.json`;

```json
  "dependencies": {
    "vtex.store-components": "3.x"
  }
```

2. Add the `image` block in any template from your theme. For example:

```json
  "image#example": {
    "props": {
      "src": "https://storecomponents.vteximg.com.br/arquivos/box.png",
      "maxHeight": 24
    }
  },
```

| Prop name     | Type       | Description                                                                | Default value | 
| ------------- | ---------- | -------------------------------------------------------------------------- | - |
| `src`         | `String!`  | Specifies the URL of an image                                              | - |
| `alt`         | `String`   | Specifies an alternate text for an image                                   | - |
| `maxWidth`    | `String`   | Specifies the max width of an image                                        | - |
| `maxHeight`   | `String`   | Specifies the max height of an image                                       | - |
| `srcset`      | `String`   | Specifies the URL of the image to use in different situations              | - |
| `sizes`       | `String`   | Specifies image sizes for different page layouts                           | - |
| `link`        | [`Link`](https://github.com/vtex-apps/native-types/blob/f63aeeb8f6e62f4a9aaec052a8be34973be7389b/pages/contentSchemas.json#L52-L74)| Specifies the link the image will redirect when clicked on                 | - |

## Customization

In order to apply CSS customizations in this and other blocks, follow the instructions given in the recipe on [Using CSS Handles for store customization](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization).

| CSS Handles |
| --- |
| `imageElement` |