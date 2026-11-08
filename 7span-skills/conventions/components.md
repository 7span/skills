# Components

## Purpose

Describe when to create components, where they live and how they take props, so the same UI is never built twice.

## Rules

1. Always create a component for any visual representation of UI that is repeated across the app.
2. If a component is used across different pages, place its file in the global `components` folder.
3. If a component is used only under one specific page, create a local `components` folder in that page's folder and place the file there. Follow the framework's file and folder naming for local components.
4. Do not flatten props when they belong to a specific type. If a `User` type exists and a `<User>` component is created, pass the `user` object as a prop instead of `firstName`, `lastName` and so on.
   - **Why:** it prevents declaring the same props again in every component that shows the type.
5. Create atomic components for specific elements repeated across pages. If a "+ Add" button appears on multiple pages, create an `AddButton` component with its icon and label defined inside it. Accept only the overrides, in this case the page URL.

## Example

```tsx
// Don't: flattened props
<User firstName={user.firstName} lastName={user.lastName} avatar={user.avatar} />

// Do: pass the typed object
<User user={user} />

// Atomic component: icon and label live inside, the page passes only the URL
<AddButton to="/products/create" />
```
