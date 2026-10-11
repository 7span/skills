# Skills

`skills` is a Claude Code plugin with opinionated coding patterns, code snippets and NPM packages for developing web applications. It lets Claude follow the same conventions across projects. This repository is both the plugin and its marketplace (`harsh`).

## Install

```
/plugin marketplace add theharshin/skills
/plugin install skills@harsh
```

## Skills

| Skill | Use when | NPM packages |
| --- | --- | --- |
| [directus-generate-types](skills/directus-generate-types/SKILL.md) | Generating strict TypeScript types from the Directus API | `directus-sdk-typegen` |
| [list-pages-development](skills/list-pages-development/SKILL.md) | Building list pages in Nuxt, Vue, Next or React | `@7span/vue-list`, `@7span/react-list` |
| [file-naming](skills/file-naming/SKILL.md) | Creating any new file | |
| [icons](skills/icons/SKILL.md) | Using icons while building the frontend | `@iconify/vue`, `@iconify/react` |
| [css](skills/css/SKILL.md) | Styling the frontend with Tailwind CSS | `tailwindcss` (v4 or above) |
| [javascript](skills/javascript/SKILL.md) | Writing JavaScript or TypeScript logic | |
| [html](skills/html/SKILL.md) | Writing markup while building UIs | |

## Structure

| Path | Purpose |
| --- | --- |
| [.claude-plugin/plugin.json](.claude-plugin/plugin.json) | Plugin manifest |
| [.claude-plugin/marketplace.json](.claude-plugin/marketplace.json) | Marketplace listing for this plugin |
| [skills/](skills) | One folder per skill, each with a `SKILL.md` and optional `snippets/` |
| [CLAUDE.md](CLAUDE.md) | Guidance for Claude Code when editing this repository |

## Adding a skill

1. Create `skills/<name>/SKILL.md` with `name` and `description` front-matter, then the purpose and rules.
2. Add code snippets as separate files in `skills/<name>/snippets/` and link them from the `SKILL.md`.
3. Add the skill to the table above.
4. Bump `version` in `plugin.json` and `marketplace.json`.

Naming rules:

- Each coding pattern and code snippet is its own file.
- Start a skill name with its framework, e.g. `directus-<>`, `nuxt-<>`, `next-<>`.
- Skills that span multiple frameworks or are not framework-specific are named by purpose, e.g. `list-pages-development`, `file-naming`.
- Use `kebab-case` for all file names.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited. Licensed under MIT.
