# Directory Structure

## Purpose

Keep the files of list and item pages in the same place in every project. One folder per model (table), with a `list` and an `item` folder inside. See the [app](../patterns/app.md) and [list pages](../patterns/list-pages.md) patterns for how these pages behave.

## Structure

```
app
└── pages
    └── products
        ├── index.tsx        access logic (permissions and guards for child pages)
        ├── list
        │   ├── index.tsx
        │   ├── columns.ts
        │   └── filters.ts
        └── item
            ├── index.tsx
            ├── api.ts       exports CREATE, UPDATE, DELETE functions
            └── create.tsx   only if create and update forms are different
```

## Rules

1. One folder per model under `pages`, named after the model in plural `kebab-case` (see [file-naming.md](file-naming.md)).
2. `index.tsx` at the model folder holds the access logic: permission and guard checks that run before any of its child pages (list and item) render.
3. `list/index.tsx` is the list page. Its columns go in `columns.ts` and its filters in `filters.ts`.
4. `item/index.tsx` is the item page. Its CREATE, UPDATE and DELETE functions are exported from `api.ts`.
5. Add `item/create.tsx` only when the create and update forms differ. Otherwise `item/index.tsx` handles both.
6. In Vue and Nuxt, use `.vue` for the component files (`index.vue`, `create.vue`); the folder structure stays the same.
7. Nested models (for example product variants) repeat this structure inside the parent's folder.
