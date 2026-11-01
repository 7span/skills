# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Claude Code marketplace (`7span`) with two plugins:

- `7span-skills`: opinionated coding patterns, technology rules, code snippets and NPM packages for web development. It is documentation only: there is no build, lint or test tooling, and the snippets are reference files, not a runnable project.
- `shadcn-design`: skills for shadcndesign.com Pro Blocks (Next.js) and the shadcn/ui kit for Figma.

Marketplace owner: Harsh Kansagara (harsh@7span.com). Copyright: 7Span Internet Private Limited. License: MIT. Published from GitHub `7span/skills`.

## Structure

- `.claude-plugin/marketplace.json` lists both plugins; it is the only manifest: both plugins are defined there with `"strict": false` and no `plugin.json` (each plugin sets `"source"` to its folder and lists its skill folders in `"skills"` relative to that source, e.g. `"./7span-skills"` with `"./tailwind"`).
- `7span-skills/<technology>/SKILL.md`: one skill per technology (`css`, `directus`, `html`, `javascript`, `tailwind`), invoked as `/7span-skills:<technology>`. Technology-specific rules, with a section per use case.
- `7span-skills/patterns/SKILL.md`: the `patterns` skill. It maps the `<name>.md` pattern files beside it: cross-cutting patterns that span technologies or frameworks, read on demand.
- `7span-skills/<technology>/snippets/<use-case>/`: code snippets as real files (`.ts`, `.json`, ...), not pasted into markdown. Link them with relative paths from the `SKILL.md` that uses them.
- `shadcn-design/` is the second plugin (`"source": "./shadcn-design"`) defined only by its `marketplace.json` entry. Each subfolder is a standalone skill with a `SKILL.md` (`pro-blocks-*`, `shadcn-design-*`).

Install: `/plugin marketplace add 7span/skills`, then `/plugin install 7span-skills@7span` or `/plugin install shadcn-design@7span`. skills.sh: `npx skills add 7span/skills`.

A new skill in either plugin must be added to the `skills` list of its entry in `marketplace.json`, since skills.sh only discovers it that way; a new pattern file must be mapped in `7span-skills/patterns/SKILL.md`. Quote `description` and `argument-hint` in `SKILL.md` frontmatter; unquoted colons break YAML parsing and the skill disappears from skills.sh. When changing contents, bump the plugin's `version` in its `marketplace.json` entry.

## Conventions

- Each technology, coding pattern and code snippet is its own file; never merge several into one. Use cases are sections inside the technology file.
- Use `kebab-case` for all file names.
- Technology skill folders are named after the technology (`css`, `tailwind`, `directus`, `html`, `javascript`) and the `SKILL.md` `name` matches the folder.
- The `SKILL.md` `description` must say what the skill covers and when to use it, since it decides when Claude loads the skill.
- Files define fixed paths and names (e.g. script location, generated output path, npm script name) that must stay identical across projects and frameworks. Preserve them verbatim when editing; only the framework-specific parts (like env var names) vary.
- Snippets are stored exactly as the author supplied them. Do not reformat or "improve" them without being asked.
