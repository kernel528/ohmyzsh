# Agent Instructions

Primary project knowledge lives at:

~/Projects/Engineering/projects/shell-tools/ohmyzsh

Read:
- project-profile.md
- current-work.md
- ai-handoff.md
- roadmap.md
- decisions.md

Keep code changes focused.
Do not make broad refactors without asking.
At session close, update the Engineering `ai-handoff.md`.

## Core Rules

- Never commit directly to main.
- Use branch-per-change.
- Keep committed content safe to publish.
- Keep commits focused and small.
- Never commit real secrets, API keys, tokens, or private hostnames.
- Always ask to confirm commits before committing, include a suggested commit message.
- Prefer cross-platform defaults (macOS + Linux Mint).
- Put machine-specific differences in local override files, not in tracked baselines.
- Open PRs with concise summary and rationale.
- Do not merge PRs unless specifically directed to do so.

## Fork Model

- This repository is a personal fork of upstream `ohmyzsh/ohmyzsh`.
- Keep the fork close to upstream and avoid broad framework rewrites.
- Put personal themes, plugins, and settings under `custom/` by default.
- Avoid editing upstream-owned `lib/`, `plugins/`, `themes/`, `tools/`, and `templates/` unless explicitly requested.
- Keep upstream sync work separate from customization work.

## Upstream Sync Rules

- Use dedicated `sync/...` branches for upstream syncs.
- Do not mix upstream sync commits with custom theme/plugin changes.
- Prefer upstream versions when resolving conflicts in files that were not intentionally customized.
- After syncing, test shell startup before proposing a commit.

## Contribution Workflow

- Prefer additive, non-breaking changes.

## Local Files

- Do not commit generated `cache/` or `log/` files unless explicitly intended.
- Do not commit secrets, private hostnames, tokens, or machine-only paths.
- Put machine-specific differences in local override files, not tracked baselines.

## Validation Expectations

- For zsh changes, run syntax checks on touched files.
- For broader framework changes, run the upstream-style syntax check from `project-profile.md`.
- For startup behavior, run `zsh -i -c exit` or an equivalent fresh-session smoke test.
- Validate that missing optional tools do not break shell startup.
