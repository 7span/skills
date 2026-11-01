# Skills

A Claude Code marketplace (`7span`) with two plugins:

- `7span-skills`: opinionated coding patterns, technology rules, code snippets and NPM packages for developing web applications.
- `shadcn-design`: skills for shadcndesign.com Pro Blocks (Next.js) and the shadcn/ui kit for Figma.

## Install

```
/plugin marketplace add 7span/skills
/plugin install 7span-skills@7span
/plugin install shadcn-design@7span
```

With [skills.sh](https://skills.sh):

```
npx skills add 7span/skills
```

## Structure

```
.claude-plugin/
  marketplace.json                   Marketplace listing and plugin definitions
7span-skills/
  <technology>/                      One skill per technology (css, directus, html, javascript, tailwind)
    SKILL.md                         Rules, a section per use case
    snippets/<use-case>/             Snippets as real files, next to the skill that uses them
  patterns/
    SKILL.md                         Maps all pattern files
    <pattern>.md                     Cross-cutting patterns
```

Each skill is invoked as `/7span-skills:<skill>` (for example `/7span-skills:tailwind`).

## Contents

| Skill | Covers |
| --- | --- |
| [css](7span-skills/css/SKILL.md) | Plain CSS (stub) |
| [tailwind](7span-skills/tailwind/SKILL.md) | Setup, classes and spacing, colors |
| [directus](7span-skills/directus/SKILL.md) | Generate types (with script and npm script snippets), table creation, table naming, junction table naming, field naming |
| [html](7span-skills/html/SKILL.md) | Wrapper divs |
| [javascript](7span-skills/javascript/SKILL.md) | Null checks, reusable functions, NPM packages, readable code |
| [patterns](7span-skills/patterns/SKILL.md) | List pages development, icons, fonts, file naming, comments |

## Adding to this repository

1. Technology rule: add a section to `7span-skills/<technology>/SKILL.md`. For a new technology, create the folder with a `SKILL.md` and add it to the `skills` list of `7span-skills` in `.claude-plugin/marketplace.json`.
2. Cross-cutting pattern: add `7span-skills/patterns/<name>.md` and map it in `7span-skills/patterns/SKILL.md`.
3. Code snippet: add it as a real file under `7span-skills/<technology>/snippets/<use-case>/` and link it from the `SKILL.md` that uses it.
4. Bump the plugin's `version` in `.claude-plugin/marketplace.json`.

Naming rules:

- Each coding pattern and code snippet is its own file.
- Use `kebab-case` for all file names.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited. Licensed under MIT.
