---
name: mcp-fundamentals
description: Reference for Model Context Protocol (MCP) concepts — tools, resources, and prompts — and how to design or debug an MCP server/client. Use when the user is building an MCP server, wiring an MCP client into Claude Code or another app, or asking what MCP tools/resources/prompts are for.
---

# Model Context Protocol (MCP) fundamentals

Based on Anthropic Academy's "Introduction to Model Context Protocol" course.
MCP is the protocol that lets a host application (like Claude Code) connect to
external servers exposing capabilities in three primitives.

## The three primitives

- **Tools** — actions the model can invoke (call an API, run a query, send a
  message). Model-controlled: the model decides when to call them based on the
  conversation. Design tool names and descriptions the same way you'd design a
  skill description — they're the only thing the model sees before deciding to
  call it.
- **Resources** — data the host can read and hand to the model as context
  (files, records, query results). Application-controlled: the host decides
  when to fetch and attach them, not the model mid-conversation.
- **Prompts** — reusable, parameterized prompt templates a server exposes so
  a host/user can invoke a known-good prompt instead of writing one from
  scratch each time. User-controlled: typically surfaced as an explicit
  command the user picks.

Getting the primitive right matters: putting a read-only data fetch behind a
"tool" when it should be a "resource" (or vice versa) leads to the model
either over-calling something meant to be host-managed, or missing context it
should have had automatically.

## Building a server (typical shape)

1. Define the primitives (tools/resources/prompts) the server exposes, with
   tight, unambiguous descriptions and input schemas.
2. Implement each handler to do exactly what its description promises — the
   model trusts the description, not the implementation, when deciding to call
   it.
3. Return errors as structured tool-call failures the model can react to
   (e.g. "not found", "permission denied"), not as unhandled exceptions that
   kill the connection.

## Building/using a client

- A client (host) discovers a server's available tools/resources/prompts at
  connection time; don't hardcode assumptions about what a server offers —
  query its capabilities.
- Scope trust per-server: a tool from an unverified/third-party MCP server
  should be treated as untrusted input in its outputs, same as any other
  external data source.

## Debugging checklist

- Tool not being called when expected → tighten the tool's `description` with
  concrete trigger scenarios, the same fix as an unfiring Claude Code skill.
- Tool called with wrong arguments → the input schema is probably underspecified
  or the description doesn't clarify parameter semantics.
- Server connection drops → check that handlers return protocol-level error
  responses instead of throwing raw exceptions.
