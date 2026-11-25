# 7Span Skills

The way we build software at 7Span, written down so your AI agent can follow it too.

## Introduction

Every team builds up its own way of doing things: how files are named, how list pages behave, which packages to use, how a Directus table is modelled. Most of it lives in people's heads and in code reviews.

This repository collects those opinionated patterns and conventions across technologies, software development and design, and packages them as skills. Once installed, your agent (Claude, Cursor, Copilot and others) picks the relevant skill up on its own and writes code the 7Span way, without you repeating the same instructions in every prompt.

For example, ask your agent to "create a users list page" and it will follow our routes, list page behaviour and file naming instead of inventing its own.

## How to use

### Any editor or agent

Skills are distributed with [skills.sh](https://skills.sh) by Vercel, which works with a variety of code editors, models and agents. From the root of your project, run:

```bash
npx skills add 7span/skills
```

That's it. The skills are added to your project and your agent loads them when the task matches.

### Claude

In Claude, go to **Settings > Customize > Plugins**, search for **7Span Skills** and install it.

In Claude Code, you can also install it from the terminal:

```
/plugin marketplace add 7span/skills
/plugin install 7span-skills@7span
```

Skills load automatically, or you can call one directly, for example `/7span-skills:tailwind`.

## Plugins

### 7span-skills

The core plugin: the opinionated patterns we follow at 7Span. Each skill covers one of:

- **Technology**: rules for a specific tool, such as Tailwind CSS, Directus or JavaScript.
- **Use case**: a specific task within a technology, such as generating Directus types.
- **Convention**: how code is written, such as file naming, comments or icons.
- **Pattern**: how the application works, such as routes, list pages and item pages.
- **Code snippets**: ready-to-use files, such as scripts and config, that a skill points to.

### shadcn-design

Only relevant if you use [shadcndesign.com](https://shadcndesign.com/) Pro Blocks in React (Next.js) or their shadcn/ui kit for Figma. It helps your agent set up, pick, build and brand Pro Blocks pages, and move designs between Figma and code. Skip it otherwise.

## How to contribute

Contributions are welcome through pull requests. A good skill captures a decision your team has already made, so the agent stops guessing.

In your PR, explain:

1. **The problem**: what goes wrong or stays inconsistent today.
2. **Why it's needed**: why this approach over the alternatives.
3. **How it helps**: what changes once the agent follows it.
4. **A small example**: the code or behaviour before and after.

### Be specific, not generic

Agents already know general best practices. A skill is only useful when it states a concrete, opinionated choice.

| Avoid (generic) | Prefer (specific) |
| --- | --- |
| Use a consistent color scheme across the project. | Create `primary` and `secondary` color variants in Tailwind and use them in classes (`bg-primary-500`, not `bg-blue-500`). |
| Avoid duplicate code. | If the same logic is used more than 2 times, move it to a function and import it everywhere it's used. |
| Name database tables properly. | Name Directus tables in plural `snake_case` without a `master_` prefix (`countries`, not `master_countries`). |

If a rule could apply to any team in the world, it probably doesn't belong here.

## Author

Harsh Kansagara ([harsh@7span.com](mailto:harsh@7span.com))

Copyright 7Span Internet Private Limited. Licensed under MIT.
