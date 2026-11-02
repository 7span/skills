# List Pages Development

> Status: stub. Patterns and snippets to be added.

## Purpose

Build list pages (data listing with pagination, search, filters, sorting) using 7Span's list packages.

## Packages by framework

| Framework   | Package                 | Source Code                                     |
| ----------- | ----------------------- | ----------------------------------------------- |
| Nuxt, Vue   | `@shilp.dev/vue-list`   | https://github.com/shilpdev/list/packages/vue   |
| Next, React | `@shilp.dev/react-list` | https://github.com/shilpdev/list/pacakges/react |

Pick the package from the project's framework. Never mix them.

## Rules

1. Always create a wrapper component that implements `@shilp.dev/vue-list` or `@shilp.dev/react-list` by importing all of the package's components.
2. Let the user customise how the list binds with the UI (e.g. via slots in Vue, render props or children in React).
3. The wrapper component exposes props as required.
4. Always reuse the wrapper component at all instances. Never use the package's components directly in pages.

## Snippets

_To be added._
