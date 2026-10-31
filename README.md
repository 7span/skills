# Skills

A Claude Code marketplace (`7span`) with two plugins:

- `dev-skills`: opinionated coding patterns, technology rules, code snippets and NPM packages for developing web applications.
- `shadcn-design`: skills for shadcndesign.com Pro Blocks (Next.js) and the shadcn/ui kit for Figma.

## Install

```
/plugin marketplace add 7span/skills
/plugin install dev-skills@7span
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
dev-skills/
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
| [Technologies](dev-skills/technologies/index.md) | CSS, Tailwind CSS (setup, classes, colors), Directus (generate types, table creation, table naming, junction table naming, field naming), HTML (wrapper divs), JavaScript (null checks, reusable functions, NPM packages, readable code) |
| [Patterns](dev-skills/patterns/index.md) | List pages development, icons, file naming |
| [Snippets](dev-skills/snippets/index.md) | Directus types generation script and npm script |

## Adding to this repository

1. Technology rule: add a section to `technologies/<technology>.md` (create the file if the technology is new). One file per technology, one section per use case.
2. Cross-cutting pattern: add `patterns/<name>.md`.
3. Code snippet: add it as a real file under `snippets/<technology>/<use-case>/` and link it from the file that uses it.
4. Map the new file in its folder's `index.md` and in `dev-skills/SKILL.md`.
5. Bump the plugin's `version` in `.claude-plugin/marketplace.json`.

Naming rules:

- Each coding pattern and code snippet is its own file.
- Use `kebab-case` for all file names.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited. Licensed under MIT.
