# App

## Purpose

Describe how 7Span admin panels, dashboards and CRUD systems are structured. Applies when the application is mostly about managing records: listing them, creating them, and reading, updating and deleting a single one.

## Mental model

Always think in terms of LIST and ITEM.

- **List**: a set of rows from a database table.
- **Item**: one specific row of a database table, identified by its ID.

Every screen is either a list or an item. This applies both when designing the UI and when writing the code: design screens, routes, components and files as a composition of lists and items.

## How it works

1. A list page shows items as a table, grid, list or Kanban view.
2. A list page has a CREATE button.
3. Clicking a list item opens its item page, where users can READ, UPDATE and DELETE it.
4. An item page can have related items (for example an order's line items). Each relation is again a list, and clicking one of its rows opens another item page. The nesting can go as deep as the data model.

```
List (table A)
 ├─ CREATE → Item (new row in A)
 └─ click row → Item (row of A)
                 ├─ READ / UPDATE / DELETE
                 └─ related List (table B, filtered by this item)
                      ├─ CREATE → Item (new row in B)
                      └─ click row → Item (row of B) → ...
```

## Rules

1. Map every database table that users manage to one list and one item.
2. A list always represents rows of a single table. An item always represents one row, by ID.
3. Reuse the same list and item design at every level of nesting. A related list behaves like a top-level list, and a related item like a top-level item.

## Related

- [list-pages.md](list-pages.md)
- [item-pages.md](item-pages.md)
- [routes.md](routes.md)
