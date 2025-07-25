# Creating ReactJS (v19) Application with Vite

Vite requires Node.js version 20.19+, 22.12+

# Node

# NPM

# Create Application

```
https://vite.dev/guide/
```

### Creating the Application

```
npm create vite@latest my-react-vite-app -- --template react-ts
```

![](./documentation//images/create-app-01.png)

![](./documentation//images/create-app-02.png)

![](./documentation//images/create-app-03.png)

## Additional Components

### Fast Refresh via SWC (alternative to Babel)

To enable Fast Refresh using SWC, a high-performance JavaScript/TypeScript compiler written in Rust, install the official Vite React SWC plugin:

This replaces the default Babel-based plugin and offers significantly faster build and HMR times, especially in larger codebases.

```
npm install --save-dev @vitejs/plugin-react-swc
```

### Linting: React-Specific Best Practices

This plugin provides additional lint rules for React components and JSX beyond what's covered by base ESLint or eslint-plugin-react.

```
npm install --save-dev eslint-plugin-react-x
```

### To catch incorrect or risky use of React DOM APIs

This plugin helps identify and prevent misuse of React DOM methods and patterns, improving code safety and consistency.

```
npm install --save-dev eslint-plugin-react-dom
```

### To catch incorrect use of hooks

This plugin enforces the Rules of Hooks in React. It helps ensure correct usage of useEffect, useState, useCallback, etc.

```
npm install --save-dev eslint-plugin-react-hooks
```

Update the esLint configuration
eslint.config.js:

```
import js from "@eslint/js";
import globals from "globals";
import reactHooks from "eslint-plugin-react-hooks";
import reactRefresh from "eslint-plugin-react-refresh";
import tseslint from "typescript-eslint";
import react from "eslint-plugin-react";
import { globalIgnores } from "eslint/config";

export default tseslint.config([
  globalIgnores(["dist"]),
  {
    files: ["**/*.{ts,tsx}"],
    extends: [
      js.configs.recommended,
      tseslint.configs.recommended,
      react.configs.recommended,
      reactHooks.configs["recommended-latest"],
      reactRefresh.configs.vite,
    ],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser,
    },
  },
]);

```

# Storybook

```
https://storybook.js.org/docs/builders/vite
```

```
npm create storybook@latest
```

![](./documentation/images/install-storybook-01.png)

This is mostly automatic, you will be asked if you wish to install minimal or a fuller install.

![](./documentation/images/install-storybook-02.png)

# Vite Test

This is partially installed as part of the Storybook Install

```
npm install --save-dev vitest
```

runn the command will install playwrite, and test coverage node modules
