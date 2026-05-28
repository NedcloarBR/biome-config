<div align="center"> 

![BiomeJS Logo](https://raw.githubusercontent.com/biomejs/resources/main/svg/slogan-light-transparent.svg)

# @nedcloarbr/biome-config

**[BiomeJS](https://biomejs.dev/) Configuration used by [NedcloarBR](https://github.com/NedcloarBR) in their projects**

[![GitHub](https://img.shields.io/github/license/NedcloarBR/biome-config)](https://github.com/NedcloarBR/biome-config/blob/master/LICENSE)
[![npm](https://img.shields.io/npm/v/@nedcloarbr/biome-config?color=crimson&logo=npm&style=flat-square)](https://www.npmjs.com/package/@nedcloarbr/biome-config)

</div>

**Table of Contents**

- [Installation](#installation)
- [Configs](#configs)
  - [base](#base)
  - [css](#css)
  - [html](#html)
  - [nestjs](#nestjs)
  - [react](#react)
  - [next](#next)
  - [vue](#vue)
  - [angular](#angular)
  - [react-native](#react-native)
  - [ignore](#ignore)

## Installation

```sh
npm install --save-dev --save-exact @biomejs/biome @nedcloarbr/biome-config
yarn add --dev --exact @biomejs/biome @nedcloarbr/biome-config
pnpm install --save-dev --save-exact @biomejs/biome @nedcloarbr/biome-config
bun add --dev --exact @biomejs/biome @nedcloarbr/biome-config
```

> [!WARNING]
> BiomeJS doesn't fully support Yarn PnP yet — [discussion](https://github.com/biomejs/biome/discussions/3393).
> If you're using Yarn Modern (v2+), opt out of PnP:
> ```yaml
> # .yarnrc.yml
> nodeLinker: node-modules
> ```

## Configs

All configs extend `base` unless noted otherwise. The diagram below shows the full inheritance chain:

```
base
├── nestjs
├── css         (CSS formatter + linting + Tailwind support)
├── html        (HTML formatter + 16 a11y rules)
└── base + html + css
    ├── react
    │   ├── next
    │   └── react-native
    ├── vue
    └── angular
```

---

### `base`

General TypeScript/JavaScript config. Includes formatter, linter rules for correctness, style, complexity and suspicious groups, and import organization.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/base"]
}
```

---

### `css`

CSS formatter and full CSS linting. Includes Tailwind CSS support out of the box — `@tailwind`, `@apply`, `@config`, `theme()` and `screen()` are all recognized.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/css"]
}
```

---

### `html`

HTML formatter and all 16 recommended accessibility rules (`useAltText`, `useButtonType`, `useHtmlLang`, `noAutofocus`, etc.).

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/html"]
}
```

---

### `nestjs`

Extends `base`. Enables TypeScript parameter decorators (`@Injectable`, `@Controller`, etc.) and enforces explicit return types on services and controllers.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/nestjs"]
}
```

---

### `react`

Extends `base` + `html` + `css`. Adds JSX-specific rules: `useSortedClasses` (Tailwind class sorting), `noReactForwardRef` (React 19), `noDangerouslySetInnerHtml`, a11y rules for JSX, and more.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/react"]
}
```

---

### `next`

Extends `react`. Disables `noDefaultExport` (required for Next.js pages and layouts) and adds `noNextAsyncClientComponent`.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/next"]
}
```

---

### `vue`

Extends `base` + `html` + `css`. Adds all Vue-specific correctness rules (`noVueReservedProps`, `noVueDuplicateKeys`, `noVueSetupPropsReactivityLoss`, etc.) and nursery rules for Vue directives.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/vue"]
}
```

---

### `angular`

Extends `base` + `html` + `css`. Enables TypeScript parameter decorators (`@Component`, `@Injectable`, etc.) and enforces explicit return types.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/angular"]
}
```

---

### `react-native`

Extends `react`. Adds React Native-specific rules: `noReactNativeDeepImports`, `noReactNativeLiteralColors`, `noReactNativeRawText`, and `useReactNativePlatformComponents`.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/react-native"]
}
```

---

### `ignore`

A standalone list of commonly ignored paths (build outputs, caches, editor folders, AI tool directories, generated files, etc.). Does not extend `base`.

```jsonc
// biome.json
{
  "extends": ["@nedcloarbr/biome-config/ignore"]
}
```

You can combine it with any other config:

```jsonc
// biome.json
{
  "extends": [
    "@nedcloarbr/biome-config/react",
    "@nedcloarbr/biome-config/ignore"
  ]
}
```
