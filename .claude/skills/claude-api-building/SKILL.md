---
name: claude-api-building
description: Reference for integrating the Claude API (Messages API) in application code — model selection, system prompts, structured/JSON output, streaming, and prompt caching. Use when the user is writing code that calls the Anthropic API directly (not through Claude Code itself), debugging API errors, or choosing between models/parameters.
---

# Building with the Claude API

Based on Anthropic Academy's "Building with the Claude API" course. Practical
notes for application code that calls the Messages API directly.

## Model selection

- Default to the latest, most capable model family for new integrations unless
  there's a measured latency/cost reason to downgrade — capability regressions
  from picking an older model are easy to miss until they show up as bad output.
- Route cheap/high-volume subtasks (classification, short extraction) to a
  smaller/faster model and reserve the larger model for the step that needs
  real reasoning; don't default everything to the biggest model.

## System prompts

- Put role, constraints, and output format in the system prompt; put the
  task-specific content in user messages. This keeps the same system prompt
  reusable across many calls.
- Be explicit about what NOT to do (e.g. "do not include markdown fences around
  the JSON") — Claude follows explicit negative constraints better than implied
  ones.

## Structured / JSON output

- Ask for a specific schema in the system prompt and validate the response
  against it in code; don't trust free-form text parsing for anything a
  downstream system depends on.
- For tool-use-style structured extraction, prefer the API's tool-calling
  mechanism over asking the model to hand-write JSON in prose — it gets
  schema-constrained output instead of a string to re-parse.

## Streaming

- Use streaming for any user-facing response over ~1-2 seconds of latency; it
  changes perceived responsiveness even when total completion time is the same.
- Streaming responses still need the same downstream validation once fully
  assembled — don't skip schema checks just because chunks arrived incrementally.

## Prompt caching

- Cache the large, stable part of a prompt (system instructions, reference
  documents, few-shot examples) and put the varying part (the actual user
  query) after it — cache hits require an exact-prefix match.
- Caching pays off once the same prefix is reused across multiple calls in a
  short window; for a single one-off call it adds no benefit.

## Error handling

- Distinguish retryable errors (rate limits, transient 5xx) from non-retryable
  ones (bad request, auth failure) and only retry the former, with backoff.
- Surface API errors to logs with enough context (request id, model, truncated
  prompt) to debug later — don't swallow them silently.
