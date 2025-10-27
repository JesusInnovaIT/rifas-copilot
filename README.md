# Sistema de Gestión de Rifas

Una aplicación web moderna construida con Vue 3 y Vite para gestionar rifas de manera simple y eficiente.

## 🎯 Características

- **Nueva Rifa**: Crear rifas con información completa
  - Nombre de la rifa
  - Fecha de la rifa
  - Número de premios
  - Número de boletos
- **Validación de Formularios**: Validación en tiempo real de todos los campos
- **Interfaz Intuitiva**: Diseño limpio y fácil de usar
- **Listado de Rifas**: Visualiza todas las rifas creadas

## 📸 Capturas de Pantalla

### Formulario de Nueva Rifa
![Formulario vacío](https://github.com/user-attachments/assets/a1419c1d-fd99-4b83-9c9c-fb5a090876f9)

### Rifa Creada
![Rifa creada exitosamente](https://github.com/user-attachments/assets/6cc2fd57-cce9-418a-b0f6-8b2ce38eb02e)

## 🚀 Instalación y Uso

### Requisitos Previos

- Node.js 20.19.0 o superior
- npm 10.8.2 o superior

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

La aplicación estará disponible en `http://localhost:5173`

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

Los archivos de producción se generarán en el directorio `dist/`

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Run End-to-End Tests with [Playwright](https://playwright.dev)

```sh
# Install browsers for the first run
npx playwright install

# When testing on CI, must build the project first
npm run build

# Runs the end-to-end tests
npm run test:e2e
# Runs the tests only on Chromium
npm run test:e2e -- --project=chromium
# Runs the tests of a specific file
npm run test:e2e -- tests/example.spec.ts
# Runs the tests in debug mode
npm run test:e2e -- --debug
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

## 🛠️ Tecnologías Utilizadas

- **Vue 3**: Framework progresivo de JavaScript
- **Vite**: Build tool ultrarrápido
- **TypeScript**: Tipado estático para JavaScript

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd) 
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

