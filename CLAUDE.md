# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Claude Code marketplace (`7span`) with two plugins:

- `dev-skills`: opinionated coding patterns, technology rules, code snippets and NPM packages for web development. It is documentation only: there is no build, lint or test tooling, and the snippets are reference files, not a runnable project.
- `shadcn-design`: skills for shadcndesign.com Pro Blocks (Next.js) and the shadcn/ui kit for Figma.

Marketplace owner: Harsh Kansagara (harsh@7span.com). Copyright: 7Span Internet Private Limited. License: MIT. Published from GitHub `7span/skills`.

## Structure

- `.claude-plugin/marketplace.json` lists both plugins; it is the only manifest: both plugins are defined there with `"strict": false` and no `plugin.json` (`dev-skills` uses `"source": "./"`, `"skills": ["./dev-skills"]`).
- `dev-skills/SKILL.md` is the only skill in `dev-skills`. It is an index that maps every other file; the other files are plain markdown read on demand.
- `dev-skills/technologies/<technology>.md`: technology-specific rules. One file per technology, with a section per use case.
- `dev-skills/patterns/<name>.md`: cross-cutting patterns that span technologies or frameworks.
- `dev-skills/snippets/<technology>/<use-case>/`: code snippets as real files (`.ts`, `.json`, ...), not pasted into markdown. Link them with relative paths from the file that uses them.
- `dev-skills/technologies/index.md`, `patterns/index.md` and `snippets/index.md` map the files in their folder.
- `shadcn-design/` is the second plugin (`"source": "./shadcn-design"`) defined only by its `marketplace.json` entry. Each subfolder is a standalone skill with a `SKILL.md` (`pro-blocks-*`, `shadcn-design-*`).

Install: `/plugin marketplace add 7span/skills`, then `/plugin install dev-skills@7span` or `/plugin install shadcn-design@7span`. skills.sh: `npx skills add 7span/skills`.

Every new `dev-skills` file must be mapped in its folder's `index.md` and in `dev-skills/SKILL.md` (including NPM packages in its packages table). A new `shadcn-design` skill must be added to the `skills` list of its entry in `marketplace.json`, since skills.sh only discovers it that way. Quote `description` and `argument-hint` in `SKILL.md` frontmatter; unquoted colons break YAML parsing and the skill disappears from skills.sh. When changing contents, bump the plugin's `version` in its `marketplace.json` entry.

## Conventions

- Each technology, coding pattern and code snippet is its own file; never merge several into one. Use cases are sections inside the technology file.
- Use `kebab-case` for all file names.
- Technology files are named after the technology (`css.md`, `tailwind.md`, `directus.md`, `html.md`, `javascript.md`).
- The `SKILL.md` `description` must say what the skill covers and when to use it, since it decides when Claude loads the skill.
- Files define fixed paths and names (e.g. script location, generated output path, npm script name) that must stay identical across projects and frameworks. Preserve them verbatim when editing; only the framework-specific parts (like env var names) vary.
- Snippets are stored exactly as the author supplied them. Do not reformat or "improve" them without being asked.
