---
name: code-gate
description: "Automatically validate code quality, tests, builds, and security before committing or pushing changes. Use whenever code changes are ready to commit or push."
---

# Code Gate

## Checks

Run available checks in this order:

1. Formatting — Prettier
2. Linting — ESLint
3. Type checking — TypeScript
4. Tests — project test suite
5. Build — production build
6. Security — dependency vulnerabilities and exposed secrets

## Workflow

- Detect the package manager from the lockfile.
- Inspect `package.json` scripts before executing checks.
- Run only checks supported by the project.
- Prefer targeted checks first, followed by full checks before pushing.
- Never silently skip failed checks.
- Never modify unrelated files to make checks pass.

## Failure Rules

If any check fails:

- Block the push.
- Report the failing check and relevant error.
- Fix the issue if it is within the current task.
- Re-run failed checks after fixing.
- Never bypass checks using `--no-verify` or similar bypasses.

## Security

- Check for exposed secrets.
- Review suspicious dependency changes.
- Check dependency vulnerabilities when tooling is available.
- Never execute untrusted scripts without inspection.
- Never expose secrets in logs or output.

## Final Report

Before pushing, report:

- Formatting: PASS / FAIL / SKIPPED
- Lint: PASS / FAIL / SKIPPED
- Types: PASS / FAIL / SKIPPED
- Tests: PASS / FAIL / SKIPPED
- Build: PASS / FAIL / SKIPPED
- Security: PASS / FAIL / SKIPPED

Allow pushing only when all applicable checks pass.

If a check is unavailable, clearly state that it was skipped and why.
