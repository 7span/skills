# Skills

A Claude Code marketplace (`7span`) with one plugin, `dev-skills`: opinionated coding patterns, technology rules, code snippets and NPM packages for developing web applications.

## Install

```
/plugin marketplace add 7span/claude-marketplace
/plugin install dev-skills@7span
```

## Structure

```
.claude-plugin/
  marketplace.json                   Marketplace listing
  plugin.json                        Plugin manifest
skills/
  SKILL.md                           Entry point: maps every file below
  technologies/
    index.md                         Maps all technology files
    <technology>.md                  One file per technology, a section per use case
  patterns/
    index.md                         Maps all pattern files
    <pattern>.md                     Cross-cutting patterns
  snippets/
    index.md                         Maps all snippets
    <technology>/<use-case>/         Snippets as real files
```

Claude loads `SKILL.md`, then reads the index and linked file that match the task.

## Contents

| Area | Files |
| --- | --- |
| [Technologies](skills/technologies/index.md) | CSS, Tailwind CSS (setup, classes, colors), Directus (generate types, table creation, table naming, field naming), HTML (wrapper divs), JavaScript (null checks, reusable functions, NPM packages, readable code) |
| [Patterns](skills/patterns/index.md) | List pages development, icons, file naming |
| [Snippets](skills/snippets/index.md) | Directus types generation script and npm script |

## Adding to this repository

1. Technology rule: add a section to `technologies/<technology>.md` (create the file if the technology is new). One file per technology, one section per use case.
2. Cross-cutting pattern: add `patterns/<name>.md`.
3. Code snippet: add it as a real file under `snippets/<technology>/<use-case>/` and link it from the file that uses it.
4. Map the new file in its folder's `index.md` and in `skills/SKILL.md`.
5. Bump `version` in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`.

Naming rules:

- Each coding pattern and code snippet is its own file.
- Use `kebab-case` for all file names.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited. Licensed under MIT.
