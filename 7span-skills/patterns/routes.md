# Routes

## Purpose

Define the route structure for pages. Every list, item and tab gets its own URL, so the URL always says where the user is.

## Rules

1. Prefer a unique route for each page over a modal or drawer UI that holds no state in the route.
2. If there are tabs, create a route for each tab and switch routes. Never show and hide tab content.
3. A `LIST` route always has the model (table) name.
4. An `ITEM` route has a dynamic row ID after the list route.
5. Creating a new item uses `+` in place of the ID.
6. Nested lists and items follow the same pattern, under the parent item's route.
7. The code reads the dynamic IDs from the URL and uses them to render the specific item.

## Examples

| Page                 | Route                                                         |
| -------------------- | ------------------------------------------------------------- |
| Product list         | `app.example.com/products`                                    |
| Product item         | `app.example.com/products/<product-id>`                       |
| New product          | `app.example.com/products/+`                                  |
| Product variant list | `app.example.com/products/<product-id>/variants`              |
| Product variant item | `app.example.com/products/<product-id>/variants/<variant-id>` |
| New product variant  | `app.example.com/products/<product-id>/variants/+`            |

## Why

- State is kept in the URL, and every action has its own unique URL.
- Users can refresh the page and land on the same page they were working on.
- Each route component holds its own state and data-fetching logic.

## Related

- [app.md](app.md)
- [list-pages.md](list-pages.md)
- [item-pages.md](item-pages.md)
