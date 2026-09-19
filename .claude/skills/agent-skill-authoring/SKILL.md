---
name: agent-skill-authoring
description: Guide for writing, configuring, and sharing new Claude Code skills in this repo. Use when the user wants to create a new skill, edit an existing SKILL.md, decide whether something should be a skill vs. a CLAUDE.md note, or troubleshoot a skill that isn't triggering.
---

# Authoring Agent Skills

Based on Anthropic Academy's "Introduction to Agent Skills" course. A skill is a
packaged, reusable instruction set that Claude Code loads automatically when a
task matches its description — think of it as a saved playbook for a recurring
kind of work.

## When something should be a skill

Make it a skill when:
- The same multi-step procedure will recur (a release checklist, a review
  standard, a repo-specific deploy flow).
- The instructions are long or detailed enough that repeating them inline every
  time would be wasteful.

Don't make it a skill when:
- It's a one-off fact — put that in `CLAUDE.md` instead.
- It's a single command someone can just run — a comment or a doc line is enough.

## Anatomy of a SKILL.md

```
---
name: kebab-case-name
description: One or two sentences — WHEN to use this skill, in language that
  matches how a user or task would phrase the trigger. This field is what
  Claude matches against, so be specific about triggers, not just topic.
---

# Body: the actual instructions, written as directives Claude should follow.
```

- `name` must be kebab-case and match the directory name under
  `.claude/skills/<name>/SKILL.md`.
- `description` is the single most important field: it's the only thing Claude
  sees before deciding to load the skill. Front-load concrete trigger phrases
  and situations, not just a topic label.
- Keep the body scoped to one responsibility. A skill that tries to cover
  "testing AND deployment AND code review" is harder to trigger correctly and
  harder to maintain than three focused skills.

## Configuring and scoping

- Skills placed at `.claude/skills/` in a repo apply to anyone working in that
  repo through Claude Code.
- A skill under a subdirectory (e.g. `apps/web/.claude/skills/...`) scopes to
  that directory; when both a scoped and unscoped skill share a name, the more
  specific one wins.
- Reference supporting files (checklists, templates) from the skill body by
  relative path so Claude reads them on demand instead of inlining everything
  into the description.

## Sharing across a team

- Skills committed to the repo are shared automatically — no separate
  distribution step. Treat `SKILL.md` changes like any other code change: review
  them, and keep the description accurate so it keeps triggering correctly as
  the repo evolves.

## Troubleshooting a skill that won't trigger

1. Check the `description` — if it doesn't mention the words/phrasing a real
   request would use, Claude won't match it. Rewrite it to include concrete
   trigger phrases, not just a category name.
2. Confirm the file is at the exact expected path (`.claude/skills/<name>/SKILL.md`)
   and the frontmatter is valid YAML.
3. If two skills' descriptions overlap heavily, narrow both — an ambiguous match
   can cause the wrong one (or neither) to load.
