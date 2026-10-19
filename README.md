# Skills

A Claude Code marketplace (`7span`) where each person publishes their skills as their own plugin, named after their username. Pick the plugin you want and install only that.

## Install

```
/plugin marketplace add 7span/claude-marketplace
/plugin install harsh@7span
/plugin install kashyap@7span
```

## Plugins

| Plugin | Author | Skills |
| --- | --- | --- |
| [harsh](plugins/harsh) | Harsh Kansagara | Opinionated coding patterns, code snippets and NPM packages for web development |
| [kashyap](plugins/kashyap) | Kashyap | None yet |

### harsh

| Skill | Use when | NPM packages |
| --- | --- | --- |
| [directus-generate-types](plugins/harsh/skills/directus-generate-types/SKILL.md) | Generating strict TypeScript types from the Directus API | `directus-sdk-typegen` |
| [list-pages-development](plugins/harsh/skills/list-pages-development/SKILL.md) | Building list pages in Nuxt, Vue, Next or React | `@7span/vue-list`, `@7span/react-list` |
| [file-naming](plugins/harsh/skills/file-naming/SKILL.md) | Creating any new file | |
| [icons](plugins/harsh/skills/icons/SKILL.md) | Using icons while building the frontend | `@iconify/vue`, `@iconify/react` |
| [css](plugins/harsh/skills/css/SKILL.md) | Styling the frontend with Tailwind CSS | `tailwindcss` (v4 or above) |
| [javascript](plugins/harsh/skills/javascript/SKILL.md) | Writing JavaScript or TypeScript logic | |
| [html](plugins/harsh/skills/html/SKILL.md) | Writing markup while building UIs | |

## Structure

```
.claude-plugin/marketplace.json     Marketplace listing of all plugins
plugins/<username>/
  .claude-plugin/plugin.json        Plugin manifest
  skills/<skill-name>/SKILL.md      One skill per file, with optional snippets/
```

## Adding your plugin

1. Create `plugins/<username>/` with `.claude-plugin/plugin.json` (`name` is your username) and a `skills/` folder.
2. List the plugin in [.claude-plugin/marketplace.json](.claude-plugin/marketplace.json) with `"source": "./plugins/<username>"`.
3. Add the plugin to the table above.

## Adding a skill to a plugin

1. Create `plugins/<username>/skills/<name>/SKILL.md` with `name` and `description` front-matter, then the purpose and rules.
2. Add code snippets as separate files in `plugins/<username>/skills/<name>/snippets/` and link them from the `SKILL.md`.
3. Add the skill to the plugin's table above.
4. Bump `version` in the plugin's `plugin.json` and its entry in `marketplace.json`.

Naming rules:

- Each coding pattern and code snippet is its own file.
- Start a skill name with its framework, e.g. `directus-<>`, `nuxt-<>`, `next-<>`.
- Skills that span multiple frameworks or are not framework-specific are named by purpose, e.g. `list-pages-development`, `file-naming`.
- Use `kebab-case` for all file names.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited. Licensed under MIT.
