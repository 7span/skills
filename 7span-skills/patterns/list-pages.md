# List Pages

## Purpose

Define how list pages look and behave. A list page represents the rows of one database table. For the implementation, see the [list pages convention](../conventions/list-pages.md); for where the files live, see the [directory structure convention](../conventions/directory-structure.md).

## Rules

1. Use the table format by default.
2. Render the table with `@shilp.dev/react-list` (React, Next) or `@shilp.dev/vue-list` (Vue, Nuxt) by default.
3. Each table row represents one item (one row) of the database table.
4. Do not add row actions such as `delete` or `view` by default.
5. Rows are always clickable for more actions. Clicking a row opens its ITEM page.
6. If the ITEM page has related data, it gets a sidebar (see [item-pages.md](item-pages.md)).

## Related

- [app.md](app.md)
- [routes.md](routes.md)
- [item-pages.md](item-pages.md)
