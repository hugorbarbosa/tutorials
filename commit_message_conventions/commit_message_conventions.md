# Commit message conventions

## Table of contents

- [General recommendations](#general-recommendations)
- [Conventions](#conventions)
    - [Common commit types](#common-commit-types)
    - [Using scopes](#using-scopes)
- [Summary](#summary)

## General recommendations

A well-written commit message helps developers understand the purpose of a change without having to inspect the code. Clear and consistent commit messages improve collaboration, simplify code reviews, and make it easier to track the history of a project.

When writing commit messages, consider the following best practices:

- Keep the subject line concise (typically 50–72 characters).
- Use the imperative mood (e.g., "Add", "Fix", "Update" instead of "Added", "Fixed", or "Updates").
- Describe **what** the commit does rather than **how** it does it.
- Keep each commit focused on a single logical change.
- If necessary, provide additional details in the commit body, separated from the subject by a blank line.

For example:

```text
feat: Add command-line option for verbose logging

Introduce the --verbose option to enable detailed logging output
during program execution. This option is useful for debugging and
troubleshooting.
```

## Conventions

Many software projects adopt the **Conventional Commits** specification to provide a standardized structure for commit messages. This convention improves readability and enables tools to automatically generate changelogs, determine semantic version changes, and automate releases.

The general format is:

```text
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Example of commit messages:

```text
feat(parser): Add support for hexadecimal literals
fix(logging): Prevent null pointer dereference
docs: Update installation guide
build(cmake): Add support for Clang 19
test: Add unit tests for configuration parser
```

Example of a commit message including all the optional parts:

```text
feat(parser): Add support for hexadecimal literals

The parser now recognizes hexadecimal integer literals prefixed with
'0x' or '0X'. This change also refactors the tokenizer to simplify
numeric literal parsing.

BREAKING CHANGE: Decimal literals with leading zeros are no longer
accepted, as they are now interpreted according to the new parsing rules.

Issue: #42
```

### Common commit types

Although the specification only formally defines the `feat` and `fix` types, many projects adopt additional types by convention.

| Type | Description |
| :---: | --- |
| `feat` | Introduce a new feature. |
| `fix` | Fix a bug. |
| `docs` | Documentation-only changes. |
| `style` | Formatting or style changes that do not affect program behavior. |
| `refactor` | Restructure existing code without changing its behavior. |
| `perf` | Improve performance. |
| `test` | Add or modify tests. |
| `build` | Update the build system or project dependencies. |
| `ci` | Modify Continuous Integration (CI) configuration. |
| `chore` | Perform maintenance tasks that do not fit another category. |
| `revert` | Revert a previous commit. |

### Using scopes

An optional scope may be added to indicate the component affected by the change.

Examples:

```text
feat(parser): Support hexadecimal literals
fix(network): Handle connection timeout
docs(api): Document authentication endpoints
build(cmake): Add install target
```

Scopes are particularly useful in medium and large projects, where they help identify the affected subsystem at a glance.

## Summary

Adopting consistent commit messages makes a project's history easier to read and maintain. Following the Conventional Commits specification provides a simple and widely adopted structure that improves communication among developers and integrates well with modern development tools and release automation.
