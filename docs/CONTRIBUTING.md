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


## 3. Commit messages

We use [Conventional Commits](https://www.conventionalcommits.org/).

Format: `type(scope): short description`

```text
feat(auth): add TOTP-based two-factor login

Explain WHY the change is needed, not only what changed.
```

Rules:
- write in English, in the imperative mood ("add", not "added"),
- subject line up to about 72 characters, no period at the end,
- `scope` is the part of the system, e.g. `auth`, `tickets`, `docker`,
- the body explains the reason for the change,
- one commit = one logical change.

Types are the same as for branches, plus `style`, `build`, `perf`
and `security`.


## 4. Pull Requests

Every PR must have a description with three parts:

1. **What** changed.
2. **Why** it changed.
3. **How to test** it (a screenshot, if the change is visual).

Workflow:
1. Push the branch and open a PR to `main`.
2. Review your own diff before merging (read it as a stranger would).
3. Merge the PR, then delete the branch.
4. Update local `main`: `git switch main && git pull`.

## 5. Secrets

Never commit secrets: passwords, tokens, API keys, `.env` files or real
personal data. All data in this project is fictional.
If a secret is committed by accident, revoke it immediately. Removing
it from the history is not enough, because it may already be copied.