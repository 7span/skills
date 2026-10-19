# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Claude Code marketplace (`7span`) where each person publishes their skills as their own plugin, named after their username. The `harsh` plugin holds opinionated coding patterns, code snippets and NPM packages for web development. It is documentation only: there is no build, lint or test tooling, and the snippets are reference files, not a runnable project.

Marketplace owner: Harsh Kansagara (harsh@7span.com). Copyright: 7Span Internet Private Limited. License: MIT. Published from GitHub `7span/claude-marketplace`.

## Structure

- `.claude-plugin/marketplace.json` lists every plugin, each with `"source": "./plugins/<username>"`. There is no plugin at the repo root.
- `plugins/<username>/.claude-plugin/plugin.json` is that user's plugin manifest. Its `name` is the username.
- `plugins/<username>/skills/<skill-name>/SKILL.md` is one skill per coding pattern: front-matter (`name`, `description`), purpose, rules, and links to its snippets. The `name` must match the folder name.
- `plugins/<username>/skills/<skill-name>/snippets/` holds that skill's code snippets, one file each, as real files (`.ts`, `.json`, ...), not code pasted into markdown. Link them with paths relative to the skill's `SKILL.md`.

Install: `/plugin marketplace add 7span/claude-marketplace`, then `/plugin install <username>@7span`.

When adding a plugin, list it in `marketplace.json` and in the README plugins table. When adding a skill, also list it under its plugin in the README. When changing a plugin's contents, bump `version` in that plugin's `plugin.json` and its `marketplace.json` entry. Only touch the plugin you were asked to change; each plugin belongs to its user.

## Conventions

- Each coding pattern and code snippet is its own file; never merge several into one.
- Always start a skill name with the framework, e.g. `directus-<>`, `nuxt-<>`, `next-<>`. This applies to the skill folder and its `name`. Exception: a skill that spans multiple frameworks is named by purpose instead (e.g. `list-pages-development`). The same applies to skills that are not framework-specific at all (e.g. `file-naming`).
- Skill `description` must say what the skill does and when to use it, since it decides when Claude loads the skill.
- Skills define fixed paths and names (e.g. script location, generated output path, npm script name) that must stay identical across projects and frameworks. Preserve them verbatim when editing; only the framework-specific parts (like env var names) vary.
- Snippets are stored exactly as the author supplied them. Do not reformat or "improve" them without being asked.
