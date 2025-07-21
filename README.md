# Rspack project

## Setup

Install the dependencies:

```bash
npm install
```

## Get started

Start the dev server, and the app will be available at [http://localhost:8080](http://localhost:8080).

```bash
npm run dev
```

Build the app for production:

```bash
npm run build
```

Preview the production build locally:

```bash
npm run preview
```

## Learn more

To learn more about Rspack, check out the following resources:

- [Rspack documentation](https://rspack.dev) - explore Rspack features and APIs.
- [Rspack GitHub repository](https://github.com/web-infra-dev/rspack) - your feedback and contributions are welcome!

## instalar dependencias

```bash
bun i
```

## correr el proyecto

```bash
bun run dev
```

## Comando que inicializo el proyecto

```
bun create rspack@latest
```

### primero se eligio eslint y prettier en la configuracion

### procedemos a instalar dependencias

1. bun add -d eslint-config-airbnb
2. bun install -d eslint-plugin-import
3. bun install -d eslint-config-airbnb-typescript

### instalamos un parser

4. bun install -d @typescript-eslint/parser

### instala esto si falla

5. bun add -d @types/eslint-config-airbnb-typescript

### el eslint.config.mjs

```js
import js from "@eslint/js";
import { globalIgnores } from "eslint/config";
import reactHooks from "eslint-plugin-react-hooks";
import reactRefresh from "eslint-plugin-react-refresh";
import globals from "globals";
import tseslint from "typescript-eslint";
import airbnb from "eslint-config-airbnb-base";
import airbnbTypescript from "eslint-config-airbnb-base-typescript";
export default tseslint.config([
  globalIgnores(["dist"]),
  {
    files: ["**/*.{ts,tsx}"],
    extends: [
      js.configs.recommended,
      airbnb,
      airbnbTypescript,
      tseslint.configs.recommended,
      reactHooks.configs["recommended-latest"],
      reactRefresh.configs.vite,
    ],
    languageOptions: {
      ecmaVersion: 2020,
      globals: {
        ...globals.browser,
        ...globals.node,
      },
    },
  },
]);
```

### ahora instalamos biome

1. bun install -d -E @biomejs/biome

### ejecutamos

bunx biome init

### correr la migracion de biome de eslint y prettier

bunx biome migrate eslint
bunx biome migrate prettier


### escribir la migracion

bunx biome migrate eslint --write --include-inspired
