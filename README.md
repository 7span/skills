# Skills

An opinionated skill (`theharsh`) with coding patterns, code snippets and NPM packages for developing web applications. It is written for Claude, so it can follow the same conventions across projects.

## Structure

| Path | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Entry point and index. Maps every pattern, snippet and NPM package. |
| [patterns/](patterns) | One coding pattern per file: purpose, rules and links to its snippets. |
| [snippets/](snippets) | Code snippets as real files, grouped in one folder per pattern. |
| [CLAUDE.md](CLAUDE.md) | Guidance for Claude Code when editing this repository. |

See [SKILL.md](SKILL.md) for the full list of patterns, snippets and packages.

## Adding to this repository

1. Add the pattern as `patterns/<name>.md`.
2. Add its code snippets as separate files in `snippets/<name>/`.
3. Map the pattern, snippets and any NPM packages in the tables in [SKILL.md](SKILL.md).

Naming rules:

- Each coding pattern and code snippet is its own file.
- Start a skill name with its framework, e.g. `directus-<>`, `nuxt-<>`, `next-<>`.
- Skills that span multiple frameworks or are not framework-specific are named by purpose, e.g. `list-pages-development`, `file-naming`.
- Use `kebab-case` for all file names.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited
