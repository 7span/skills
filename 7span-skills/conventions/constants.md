# Constants

## Purpose

Keep static values in one place so they are never repeated across the application.

## Rules

1. Always create a `constants` folder and put all static configuration in it.
2. Do not repeat static values across the application. Define them once in `constants` and import them.
3. If a constant is generic and does not belong to any group, put it in `constants/index.js`.
4. If there are multiple constants for the same group, create a file named after the group. For example, [icons.md](icons.md) exports icon constants from `constants/icons.js`.

## Structure

```
constants
├── index.js     generic constants that do not belong to a group
└── icons.js     one file per group of related constants
```
