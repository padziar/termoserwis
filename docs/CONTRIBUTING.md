# Contribution guidelines

This document describes how we work on TermoSerwis. The rules are short
on purpose, so they are easy to follow.

## 1. Core rule

Nothing goes directly to `main`. Every change goes through its own
branch and a Pull Request (PR).

## 2. Branch names

Format: `type/short-lowercase-description`

| Type       | Use it for                       | Example                   |
|------------|----------------------------------|---------------------------|
| `feat`     | a new feature                    | `feat/employee-model`     |
| `fix`      | a bug fix                        | `fix/csrf-token-missing`  |
| `docs`     | documentation only               | `docs/contributing-guide` |
| `chore`    | housekeeping, configuration      | `chore/docker-compose`    |
| `test`     | tests only                       | `test/rbac-permissions`   |
| `refactor` | code change without new behavior | `refactor/ticket-service` |
| `ci`       | CI pipeline                      | `ci/run-tests-on-pr`      |

Rules:
- one branch = one feature or one task,
- description in English, words separated by hyphens,
- always create a branch from the up-to-date `main`.