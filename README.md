# DE_InterfacesInteractivasVue_PokeAPI

Este proyecto es una aplicación web desarrollada en Vue.js que permite a los usuarios descubrir Pokémon utilizando la API de PokeAPI. Los Pokémon se muestran en tarjetas y los usuarios deben ingresar el nombre correcto del Pokémon para descubrirlo. El contador de Pokémon descubiertos se actualiza dinámicamente a medida que se descubren más Pokémon.

## Estructura del Proyecto

El proyecto tiene la siguiente estructura:
```
└── 📁DE_InterfacesInteractivasVue_PokeAPI
    └── 📁public
        └── favicon.ico
    └── 📁src
        └── 📁assets
            └── logo.svg
            └── main.css
            └── pokemon-logo.png
        └── 📁components
            └── PokemonCard.vue
        └── App.vue
        └── main.js
    └── index.html
    └── README.md
```
- `src/assets/`: Contiene los archivos de recursos, como imágenes.
- `src/components/`: Contiene los componentes Vue.js.
- `src/App.vue`: Componente principal de la aplicación.
- `src/main.js`: Archivo de entrada de la aplicación.
- `public/index.html`: Archivo HTML principal.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
