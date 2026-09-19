---
name: claude-code-101
description: Reference for effective day-to-day use of Claude Code in this repo — task framing, plan mode, permission modes, and CLAUDE.md conventions. Use when the user asks how to work with Claude Code more effectively, how to structure a CLAUDE.md, when to use plan mode, or how permissions/hooks affect a task.
---

# Claude Code 101 — working effectively

Based on Anthropic Academy's "Claude Code 101" course. Practical rules for getting
good results out of Claude Code sessions in this repository.

## Framing a task

- Give Claude Code a concrete, scoped task rather than an open-ended one. "Fix the
  null-pointer in `parseConfig`" beats "make the code better."
- State the acceptance criteria up front (tests must pass, no new lint warnings,
  a specific file must not change) so Claude can self-check before finishing.
- For anything with real ambiguity — architecture choices, destructive operations,
  unclear requirements — let Claude ask rather than guess.

## CLAUDE.md

- Keep a `CLAUDE.md` at the repo root with: build/test/lint commands, directory
  layout notes a newcomer wouldn't guess, and any house conventions (naming,
  commit style, review checklist).
- Don't restate anything discoverable by reading the code (e.g. "we use React").
  Only put in facts that save Claude a search — non-obvious constraints and
  workflows.
- Update it when a convention changes; a stale CLAUDE.md is worse than none.

## Plan mode

- Use plan mode for multi-file or architecturally significant changes: it forces
  a reviewable plan before any edit lands, which is cheaper to correct than a
  half-finished implementation.
- Skip plan mode for small, obviously-scoped fixes — the overhead isn't worth it.

## Permissions

- Claude Code's permission modes gate which tool calls run without asking
  (file edits, shell commands, network calls). Tighter permissions are safer by
  default; loosen them deliberately for a trusted, repetitive workflow, not as a
  blanket setting.
- Irreversible or wide-blast-radius actions (force-push, `rm -rf`, dropping a DB
  table) should stay behind a confirmation even in an otherwise permissive mode.

## Iterating

- Prefer several small, verifiable steps (edit → run tests → next edit) over one
  large diff — it's easier to localize a regression.
- When a change touches UI behavior, actually run the app and exercise the
  golden path before calling the task done; passing tests are not the same as a
  working feature.
