# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single Claude skill (`theharsh`) holding opinionated coding patterns, code snippets and NPM packages for web development. It is documentation only: there is no build, lint or test tooling, and the snippets are reference files, not a runnable project.

Author: Harsh Kansagara (harsh@7span.com). Copyright: 7Span Internet Private Limited. These live in the `SKILL.md` front-matter.

## Structure and mapping rule

- `SKILL.md` is the entry point and the index. Its front-matter (`name`, `description`, `author`, `email`, `copyright`) defines the skill.
- `patterns/<name>.md` holds one coding pattern per file: purpose, rules, and links to its snippets.
- `snippets/<pattern-name>/` holds that pattern's code snippets, one file each, as real files (`.ts`, `.json`, ...), not code pasted into markdown.

Every pattern, snippet and NPM package must be mapped in the matching table in `SKILL.md` (Coding Patterns, Code Snippets, NPM Packages). When adding or renaming a file, update that table and any relative links in the pattern file (snippet links from `patterns/` use `../snippets/...`).

## Conventions

- Each coding pattern and code snippet is its own file; never merge several into one.
- Always start a skill name with the framework, e.g. `directus-<>`, `nuxt-<>`, `next-<>`. This applies to the pattern file name, its snippets folder and its `SKILL.md` entry. Exception: a skill that spans multiple frameworks is named by purpose instead (e.g. `list-pages-development`). The same applies to skills that are not framework-specific at all (e.g. `file-naming`).
- Pattern files define fixed paths and names (e.g. script location, generated output path, npm script name) that must stay identical across projects and frameworks. Preserve them verbatim when editing; only the framework-specific parts (like env var names) vary.
- Snippets are stored exactly as the author supplied them. Do not reformat or "improve" them without being asked.
