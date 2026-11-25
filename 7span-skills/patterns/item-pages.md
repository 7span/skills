# Item Pages

## Purpose

Define how pages for a single record look and behave: create, edit and view, and how their forms are laid out.

## Rules

1. By default a single component and route handles the create, update and view actions.
2. If the create and update flows differ in a complex form, create a separate create component and route. It asks the user for the minimum data needed to create a new row. Once the row exists, the user continues on the item page, where the additional data operations are enabled.
3. When creating a new ITEM (route ending in `+`, see [routes.md](routes.md)), do not show the ITEM sidebar, since the item does not exist yet. This applies to both `item/index.tsx` and `item/create.tsx`.

For where these files live, see the [directory structure convention](../conventions/directory-structure.md).

## Sidebar

When an ITEM has related data, its page gets a sidebar. Each entry is a display block, the item itself, or a related list. Each entry that is a page has its own route (see [routes.md](routes.md)).

Example, a Product ITEM page:

| Sidebar entry | Type            |
| ------------- | --------------- |
| Product Photo | Display         |
| Product Name  | Display         |
| About         | Nav Item (ITEM) |
| Variants      | Nav Item (LIST) |
| Images        | Nav Item (LIST) |
| Orders        | Nav Item (LIST) |

A related LIST follows the same rules as any list page, and clicking one of its rows opens another ITEM page.
