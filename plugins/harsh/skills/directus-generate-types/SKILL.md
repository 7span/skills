---
name: directus-generate-types
description: Generate strict TypeScript types from the Directus API for frontend and backend development using directus-sdk-typegen. Use when setting up or regenerating Directus types.
---

# Directus Generate Types

## Purpose

Generate TypeScript types from the Directus API for frontend and backend development. This enforces strict type validation with TypeScript across the app.

## Package

Uses the [`directus-sdk-typegen`](https://www.npmjs.com/package/directus-sdk-typegen) npm package.

## Fixed locations (never change)

| What                 | Path                                 |
| -------------------- | ------------------------------------ |
| Generation script    | `scripts/generate-directus-types.ts` |
| Generated types file | `app/types/directus-schema.ts`       |
| npm script name      | `generate:types`                     |

The generated file is always written to the same path, regardless of framework.

## Rules

1. Always use `generateDirectusTypes` from `directus-sdk-typegen` in the script at `scripts/generate-directus-types.ts`.
2. Always set `outputPath` to `app/types/directus-schema.ts`.
3. Always add the `generate:types` npm script exactly as given in the package script snippet.
4. Read the Directus URL and token from env. Put the token in `.env.local`, never commit it.
5. Exit with an error if either env var is missing.

## Framework adaptation

The snippet is written for Directus + Nuxt. Use the same pattern for other frameworks: keep the script path, output path and npm script identical, and only change the env var name that holds the Directus URL to match the framework's convention.

| Framework | Directus URL env var                                                         |
| --------- | ---------------------------------------------------------------------------- |
| Nuxt      | `NUXT_PUBLIC_API_BASE_URL`                                                   |
| Others    | The framework's equivalent for the API base URL (e.g. its public-env prefix) |

`DIRECTUS_TOKEN` stays the same everywhere.

## Snippets

- Script: [snippets/script.ts](snippets/script.ts)
- npm script: [snippets/package.json](snippets/package.json)
