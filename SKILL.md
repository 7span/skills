---
name: theharsh
description: This skill contains an opiniated Coding Patterns, Code Snippets and NPM Pacakges to be used while developing web applications.
author: Harsh Kansagara
email: harsh@7span.com
copyright: 7Span Internet Private Limited
---

# Index

Each coding pattern and code snippet lives in its own file and is mapped here. Read the linked file when the task matches.

## Coding Patterns

| Pattern                 | File                                                                       | Use when                                                                          |
| ----------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Directus Generate Types | [patterns/directus-generate-types.md](patterns/directus-generate-types.md) | Generating strict TypeScript types from the Directus API for frontend and backend |
| List Pages Development  | [patterns/list-pages-development.md](patterns/list-pages-development.md)   | Building list pages in Nuxt, Vue, Next or React                                   |
| File Naming             | [patterns/file-naming.md](patterns/file-naming.md)                         | Creating any new file                                                             |
| Icons                   | [patterns/icons.md](patterns/icons.md)                                     | Using icons while building the frontend                                           |
| CSS                     | [patterns/css.md](patterns/css.md)                                         | Styling the frontend with Tailwind CSS                                            |
| JavaScript              | [patterns/javascript.md](patterns/javascript.md)                           | Writing JavaScript or TypeScript logic                                            |
| HTML                    | [patterns/html.md](patterns/html.md)                                       | Writing markup while building UIs                                                 |

## Code Snippets

| Snippet                          | File                                                                                           | Used by                 |
| -------------------------------- | ---------------------------------------------------------------------------------------------- | ----------------------- |
| Directus types generation script | [snippets/directus-generate-types/script.ts](snippets/directus-generate-types/script.ts)       | Directus Generate Types |
| `generate:types` npm script      | [snippets/directus-generate-types/package.json](snippets/directus-generate-types/package.json) | Directus Generate Types |

## NPM Packages

| Package                           | Used by                 |
| --------------------------------- | ----------------------- |
| `directus-sdk-typegen`            | Directus Generate Types |
| `@7span/vue-list` (Nuxt, Vue)     | List Pages Development  |
| `@7span/react-list` (Next, React) | List Pages Development  |
| `@iconify/react` (Next, React)    | Icons                   |
| `@iconify/vue` (Nuxt, Vue)        | Icons                   |
| `tailwindcss` (v4 or above)       | CSS                     |
