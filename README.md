# @n1hron/tsconfig

Personal, opinionated TypeScript config, shipped as composable presets.

## Install

```sh
npm install -D @n1hron/tsconfig typescript
```

Requires TypeScript 5.8+ (needed for the `erasableSyntaxOnly` option).

## Usage

None of the presets extend one another internally. This is intentional: it keeps every preset predictable and safe to combine in any order.

The one rule that follows from that: always list the base config (`@n1hron/tsconfig`) first. Everything after it is optional and order-independent.

```jsonc
// Plain Node.js / library project
{
  "extends": "@n1hron/tsconfig"
}
```

```jsonc
// Node.js project that wants @types/node globals
{
  "extends": ["@n1hron/tsconfig", "@n1hron/tsconfig/node"]
}
```

```jsonc
// Browser app bundled by Vite / esbuild / webpack
{
  "extends": ["@n1hron/tsconfig", "@n1hron/tsconfig/bundler", "@n1hron/tsconfig/web"]
}
```

```jsonc
// Web Worker / Service Worker script, bundled
{
  "extends": ["@n1hron/tsconfig", "@n1hron/tsconfig/bundler", "@n1hron/tsconfig/webworker"]
}
```
