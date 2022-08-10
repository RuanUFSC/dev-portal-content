---
title: "Metro Theme IO"
slug: "tiendasjumboqaio-metro-theme-v3"
excerpt: "tiendasjumboqaio.metro-theme@3.2.45"
hidden: true
createdAt: "2022-07-05T16:24:44.260Z"
updatedAt: "2022-08-02T16:50:11.740Z"
---
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
<!-- ALL-CONTRIBUTORS-BADGE:END -->

Metro theme IO es la base sobre la cual se implementa vtex io para tiendas metro.

## Preview

<img src='../assets/image/docs/main-theme.png'/>

## Configuración

### Paso 1 - Configuración Básica

Acceda a la [guía de configuración básica de VTEX IO](https://vtex.io/docs/getting-started/build-stores-with-store-framework/1) y siga todos los pasos indicados..

Al final de la configuración, debe tener instalada la interfaz de línea de comandos de VTEX (Toolbelt) junto con un espacio de trabajo de desarrollador en el que puede trabajar.

### Paso 2 - Clonación del repositorio metro-theme-io

[Clone este](https://github.com/ITGlobers/metro-theme-IO) repositorio a sus archivos locales para poder comenzar a trabajar en él de manera efectiva.

Luego, acceda al repositorio con la terminal

### Paso 3 - Editar el `Manifest.json`

Estando en el directorio del repositorio, es hora de editar el archivo `manifest.json` de metro-theme-io.

Debes reemplazar los valores `vendor` y `account`. `vendor` es el nombre de la cuenta en la que esta trabajando y `account` es el nombre que deseas colocar al tema. por ejemplo:

```json
{
  "vendor": "tiendametroqaio",
  "name": "metro-theme-io"
}
```

### Paso 4 - Instalar apps necesarias

Para usar Store Framework y trabajar en el tema de su tienda, es necesario tener instalados `vtex.store-sitemap` y `vtex.store`.

Ejecute `vtex list` y verifique si esas aplicaciones ya están instaladas.

Si no lo están, ejecute el siguiente comando para instalarlos: `vtex install vtex.store-sitemap vtex.store -f`

### Paso 5 - Desinstalar el store-theme predeterminado

Al ejecutar `vtex list`, puede verificar si algún tema está instalado.

Es común tener ya instalado el `vtex.store-theme` cuando inicia el proceso de desarrollo de la tienda.

Por lo tanto, si lo encuentra en la lista de aplicaciones, copie su nombre y utilícelo junto con el comando `vtex uninstall`. Por ejemplo:

```json
vtex uninstall vtex.store-theme
```

### Paso 6- Ejecute un preview de la tienda

ha llegado el momento de cargar todos los cambios que realizó en sus archivos locales a la plataforma. Para eso, use el comando `vtex link`.

Si el proceso se ejecuta sin ningún error, se mostrará el siguiente mensaje: `App linked successfully`. Luego, ejecute el comando `vtex browser` para abrir una ventana del navegador que tenga su tienda vinculada.

Esto le permitirá ver los cambios aplicados en tiempo real, a través de la cuenta y el espacio de trabajo en el que está trabajando.

## Dependencies

Todos los componentes de la tienda que ve en este documento también son de código abierto. Listo para la producción, puede encontrar esas aplicaciones en esta organización de GitHub.

Store framework es la base para crear cualquier tienda utilizando _VTEX IO Web Framework_.

- [Store](https://github.com/vtex-apps/store/blob/master/README.md)

Store GraphQL es un middleware para acceder a todas las APIs VTEX.

- [Store GraphQL](https://github.com/vtex-apps/store-graphql/blob/master/docs/README.md)

### Store Component Apps

- "vtex.store"
- "vtex.store-header"
- "vtex.product-summary"
- "vtex.store-footer"
- "vtex.store-components"
- "vtex.styleguide"
- "vtex.slider"
- "vtex.carousel"
- "vtex.shelf"
- "vtex.menu"
- "vtex.minicart"
- "vtex.product-details"
- "vtex.product-kit"
- "vtex.search-result"
- "vtex.login"
- "vtex.my-account"
- "vtex.flex-layout"
- "vtex.rich-text"
- "vtex.store-drawer"
- "vtex.locale-switcher"
- "vtex.product-quantity"
- "vtex.product-identifier"
- "vtex.breadcrumb"
- "vtex.sticky-layout"
- "vtex.product-customizer"
- "vtex.stack-layout"
- "vtex.product-specification-badges"
- "vtex.product-review-interfaces"
- "vtex.telemarketing"
- "vtex.order-placed"
- "vtex.checkout-summary"
- "vtex.product-list"
- "vtex.add-to-cart-button"
- "vtex.product-bookmark-interfaces"
- "vtex.responsive-layout"
- "vtex.slider-layout"
- "vtex.store-image"
- "vtex.store-icons"
- "vtex.modal-layout"
- "vtex.store-link"
- "vtex.store-video"
- "vtex.product-gifts"
- "vtex.product-price"
- "vtex.disclosure-layout"
- "vtex.store-form"
- "vtex.product-highlights"
- "vtex.product-specifications"
- "vtex.tab-layout"
- "vtex.condition-layout"
- "vtex.css-handles"
- "vtex.order-items"
- "vtex.visibility-layout"
- "vtex.search"
- "vtex.search-resolver"
- "vtex.my-authentication"
- "vtex.mega-menu"
- "vtex.recommendation-shelf"
- "vtex.shelf-components"
- "vtex.product-comparison"

### Custom Apps

Adicionalmente necesitaremos usar las siguientes apps custom: 

- ["tiendametroqaio.minicart"](https://github.com/ITGlobers/metro-minicart)
- ["tiendametroqaio.metro-general-apps"](https://github.com/ITGlobers/metro-general-apps-io)
- ["tiendametroqaio.custom-cart"](https://github.com/ITGlobers/metro-custom-cart)
- ["tiendametroqaio.delivery-modal"](https://github.com/ITGlobers/metro-delivery-modal)
- ["tiendametroqaio.wishlist-app"](https://github.com/ITGlobers/metro-wishlist)
- ["tiendametroqaio.calculate-pum"](https://github.com/ITGlobers/metro-pum-io)
- ["tiendametroqaio.buscador-multiple"](https://github.com/ITGlobers/metro-buscador-multiple)
- ["tiendametroqaio.countdown"](https://github.com/ITGlobers/metro-countdown-app)
- ["tiendametroqaio.main-menu"](https://github.com/ITGlobers/metro-mega-menu)
- ["tiendametroqaio.custom-pages"](https://github.com/ITGlobers/metro-custom-pages)
- ["metro-admin-tarjeta-regalo"](https://github.com/ITGlobers/metro-admin-tarjeta-regalo)
- ["metro-graph-service"](https://github.com/ITGlobers/metro-graph-service)

<!-- ## Contributing

Check it out [how to contribute](https://github.com/vtex-apps/awesome-io#contributing) with this project. -->

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><img src="https://avatars.githubusercontent.com/u/63118722?v=4" width="100px;" alt=""/><br /><sub><b>Daniel Acosta</b></sub></a><br /><a href="https://github.com/deacostac" title="Documentation">📖</td>
    <td align="center"><a href="http://www.hruiz.com"><img src="https://avatars.githubusercontent.com/u/75335391?v=4" width="100px;" alt=""/><br /><sub><b>Hector Ruiz</b></sub></a><br /><a href="https://github.com/hruiz13" title="Documentation">📖</a></td>
   <td align="center"><img src="https://avatars.githubusercontent.com/u/75432596?v=4" width="100px;" alt=""/><br /><sub><b>Leonardo Rincón</b></sub></a><br /><a href="https://github.com/LeoRincon" title="Documentation">📖</td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind are welcome!

<!-- DOCS-IGNORE:end -->