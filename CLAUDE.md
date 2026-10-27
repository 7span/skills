# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Claude Code marketplace (`7span`) with a single plugin (`dev-skills`) holding opinionated coding patterns, technology rules, code snippets and NPM packages for web development. It is documentation only: there is no build, lint or test tooling, and the snippets are reference files, not a runnable project.

Marketplace owner: Harsh Kansagara (harsh@7span.com). Copyright: 7Span Internet Private Limited. License: MIT. Published from GitHub `7span/claude-marketplace`.

## Structure

- `.claude-plugin/marketplace.json` lists the plugin with `"source": "./"`; `.claude-plugin/plugin.json` is its manifest.
- `skills/SKILL.md` is the only skill Claude Code discovers. It is an index that maps every other file; the other files are plain markdown read on demand.
- `skills/technologies/<technology>.md`: technology-specific rules. One file per technology, with a section per use case.
- `skills/patterns/<name>.md`: cross-cutting patterns that span technologies or frameworks.
- `skills/snippets/<technology>/<use-case>/`: code snippets as real files (`.ts`, `.json`, ...), not pasted into markdown. Link them with relative paths from the file that uses them.
- `technologies/index.md`, `patterns/index.md` and `snippets/index.md` map the files in their folder.

Install: `/plugin marketplace add 7span/claude-marketplace`, then `/plugin install dev-skills@7span`.

Every new file must be mapped in its folder's `index.md` and in `SKILL.md` (including NPM packages in its packages table). When changing contents, bump `version` in both `plugin.json` and `marketplace.json`.

## Conventions

- Each technology, coding pattern and code snippet is its own file; never merge several into one. Use cases are sections inside the technology file.
- Use `kebab-case` for all file names.
- Technology files are named after the technology (`css.md`, `tailwind.md`, `directus.md`, `html.md`, `javascript.md`).
- The `SKILL.md` `description` must say what the skill covers and when to use it, since it decides when Claude loads the skill.
- Files define fixed paths and names (e.g. script location, generated output path, npm script name) that must stay identical across projects and frameworks. Preserve them verbatim when editing; only the framework-specific parts (like env var names) vary.
- Snippets are stored exactly as the author supplied them. Do not reformat or "improve" them without being asked.
