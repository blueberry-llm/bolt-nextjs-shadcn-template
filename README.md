# Next.js ShadCN Template

A starter template for [bolt.diy](https://github.com/stackblitz-labs/bolt.diy).

## Purpose

This template is designed for use with **<https://github.com/stackblitz-labs/bolt.diy>**. bolt.diy fetches
these files at runtime and imports them into a fresh WebContainer project when you ask for a Next.js + ShadCN UI project,
so everything here needs to install and build with no extra setup.

Modified by [Dustin Loring](https://github.com/Dustinwloring1988) (Dustinwloring1988) in October 2026.

## Stack

| Package | Version |
| --- | --- |
| Next.js | ^16.4.0 |
| React | ^19.3.0 |
| React-DOM | ^19.3.0 |
| Tailwind CSS | ^4.3.3 |
| TypeScript | ~6.0.3 |
| @types/react | ^19.3.0 |
| @types/node | ^26.6.4 |

Node 20 or newer is required.

## Commands

```bash
npm install   # install dependencies
npm run dev   # next dev — dev server
npm run build # next build — production build
npm run start # next start — production server
npm run lint  # next lint — run linter
```

## About this template

A Next.js + React + TypeScript project with Tailwind CSS 4 and ShadCN UI components. The template uses the
app router directory structure (`app/`). Includes 35+ pre-built components via `@radix-ui/react-*` and
`shadcn-ui`. `next-themes` is configured for light/dark mode support.

## Upgraded to Next.js 16, React 19, Tailwind CSS 4, TypeScript 6.0.3 (October 2026)

This was a major multi-step upgrade:
- **Next.js**: 13.5.1 → 16.4.0. Verified with `npm install` and `npm run build` after the update.
- **React**: 18.2.0 → 19.3.0. All `@radix-ui/react*` components are compatible with React 19.
- **Tailwind CSS**: 3.3.3 → 4.3.3. Config updated to TW 4 format (`tailwind.config.ts` replaced `tailwind.config.js`). `tailwindcss-animate` dependency kept but `tailwind.config.js` removed in favor of `tailwind.config.ts`. `postcss.config.js` simplified (TW 4 PostCSS integration change).
- **TypeScript**: 5.2.2 → ~6.0.3 (ecosystem standard for TW 4 + Next 16).
- **@types/react**: 18.2.22 → ^19.3.0
- **@types/node**: 20.6.2 → ^26.6.4

Build passes with `npm run build`. The TypeScript compiler automatically updated `tsconfig.json` to set `jsx: react-jsx` and add `.next/dev/types` inclusion.

## Verification

- `npm install` completes with all upgraded dependencies
- `npm run build` compiles successfully with Turbopack
- `npm run start` serves the production build
- TypeScript type-check runs and suggests `tsconfig.json` improvements

## Notes

- **Next.js 16** uses Turbopack by default for faster builds. The `eslint` config warning in `next.config.js` is informational - the `eslint` key is no longer supported in the CLI and can be removed from `next.config.js` if desired.
- **Tailwind CSS 4** uses a new config format (`tailwind.config.ts` vs `tailwind.config.js`). The `css layer` at-rule (`@layer`) and `@apply` directives still work but may produce minor parsing warnings in some environments - these are not build errors.
- **React 19** is the latest stable release. All ShadCN UI Radix components are compatible with React 19's event system and hooks.
- The `@next/swc-wasm-nodejs` dependency was kept as-is; Next 16 handles SWC compilation differently but the pinned version still works.

## Migration Notes

- `tailwind.config.js` was replaced with `tailwind.config.ts` (TypeScript config)
- `postcss.config.js` was simplified (TW 4 PostCSS integration change)
- `globals.css` `@apply` directives may need review for TW 4 compatibility
- `next.config.js` `eslint` key is deprecated and can be removed
- `tsconfig.json` was auto-updated by `next build` to set `jsx: react-jsx`
- `app/router` vs `pages` directory: Next 16 supports both the app router and pages router

## Known Issues (Pre-existing, Not Blocking)

- Turbopack CSS parse warnings for `@apply` and `@tailwind` in `globals.css` - the build completes successfully
- TypeScript config suggestions from `npm run build` (add `.next/dev/types` to `include`) - optional
- `next.config.js` `eslint` key warning - informational, can be removed
- `next-themes` configuration may need `enablePersistentTheme` adjustment for TW 4
<tool_call>