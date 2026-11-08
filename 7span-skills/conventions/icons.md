# Icons

## Purpose

Use icons consistently while building the frontend.

## Library

Always use [Iconify](https://iconify.design/). It provides framework-specific npm packages:

| Framework   | Package          |
| ----------- | ---------------- |
| Next, React | `@iconify/react` |
| Nuxt, Vue   | `@iconify/vue`   |

## Rules

1. Always use the `mdi` icon set for consistency.
2. Always use the outline version of `mdi` icons (names ending in `-outline`, e.g. `mdi:home-outline`).
3. Prefer basic, easy to remember icons over complex ones.
4. Do not use icon names directly in components. Create a file called `icons.js` and export icon constants from there; components import the constants.
5. Name each exported constant after what the icon means in the host application, not after the icon itself.
   - **Why:** it keeps icon usage consistent across the app and documents where each icon is used.

```js
export const WORK = 'mdi:briefcase-variant-outline'
```

## Finding icons

- Browse the `mdi` collection: https://icones.netlify.app/collection/mdi
- To find an icon through APIs, see the Iconify API query docs: https://iconify.design/docs/api/queries.html
