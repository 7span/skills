---
name: reactjs
description: "React.js and Next.js rules for 7Span web projects: understand the project first, ask before big changes or new packages, reuse code, hooks, TypeScript, App Router. Use when writing or reviewing React or Next.js code."
---

# React.js and Next.js

These rules apply to both React.js and Next.js projects.

## Before You Start

1. Read the existing project before making changes.
2. Follow its folder structure, conventions and architecture. Don't introduce a new one or restructure files without a clear reason.
3. If the requirement or the code is unclear, ask. Don't assume.

## Ask Before Implementing

1. For a new feature, refactor, optimization or any significant change, first suggest the simplest suitable approach and briefly explain why.
2. Wait for the user's approval before implementing it.
3. For small changes, keep the explanation short.

## Optimization and Bug Fixes

1. Understand the existing code and find the actual problem before changing anything.
2. Don't change unrelated code.
3. Don't add an optimization without a clear benefit.
4. If the target is unclear, ask which file or component to optimize and what matters most (performance, readability or re-renders).

## Hooks

1. Don't add `useMemo`, `useCallback`, `useReducer`, `useEffect` or `useRef` by default. Use them only when they solve a real need.
2. Prefer plain JavaScript and React patterns when they are enough.

## Packages

1. Before adding an npm package, check whether an existing dependency or a native JavaScript, React or Next.js feature can do the job.
2. If a new package is really needed, explain why and wait for the user's approval. Never install one automatically.

## Files and Reusability

1. Keep files under about 500 lines. Split by responsibility only when it improves readability, not just to hit the number.
2. Reuse existing components, hooks, utilities, constants and types before creating new ones.
3. Don't duplicate logic. Use props to make a component work for similar screens.

## TypeScript

1. Use simple, explicit types and reuse the existing ones.
2. Avoid `any` and unnecessary type assertions.
3. Avoid complicated generics and utility types unless required.

## React

1. Use functional components, each with a single responsibility.
2. Avoid unnecessary state and prop drilling.

## Next.js

1. Check the Next.js version and whether the project uses the App Router or the Pages Router before making changes.
2. In the App Router, use Server Components by default. Add `"use client"` only when a component needs browser interactivity or client-side hooks.
3. Use the built-in Next.js features for images, data fetching, caching and revalidation where they fit.
4. Follow the existing middleware and authentication patterns.

## Final Check

1. Review the changed files and make sure nothing unrelated was touched.
2. Run the available lint, type-check, test or build commands. Never say they passed without running them.
3. List the files you changed and mention any check you could not run.
