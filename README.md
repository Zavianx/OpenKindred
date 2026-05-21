# OpenKindred

> An open-source emotional memory layer that helps AI agents understand the human behind the prompt.

OpenKindred is a local-first personal context compiler for AI agents.

It turns a person's digital life, with explicit consent, into an auditable startup profile that any agent can use before a conversation begins.

The goal is simple:

> Every agent should start as someone who knows you, not as a stranger with a search box.

## Why

Most AI agents start from zero.

Even if you have talked to them for months, they often miss the things a close friend would remember:

- what kind of comfort actually helps you
- what topics are sensitive
- what projects matter right now
- how you make decisions
- who is important in your life
- what patterns keep showing up in your work and relationships

Existing memory systems are usually built around retrieval: store facts, search chunks, inject context.

OpenKindred is built around understanding:

- What can be safely inferred about this person?
- What evidence supports that inference?
- Should the user approve, edit, or delete it?
- How should an agent use it with care?

## The Core Idea

OpenKindred compiles personal data into a structured, reviewable user model.

```text
personal sources
  local files, notes, Gmail, Notion, calendar, chats, browser history, repos
        |
        v
consent and privacy layer
  source permissions, redaction, deny lists, local processing
        |
        v
evidence store
  timestamped facts with source, quote, confidence, and retention policy
        |
        v
profile compiler
  stable traits, current projects, emotional patterns, preferences, boundaries
        |
        v
agent startup context
  a compact, user-approved profile that agents can read before responding
```

## Example

When a user says:

> I just went through a breakup.

A generic assistant may respond with generic comfort.

An OpenKindred-aware agent should be able to respond with context and restraint:

> I remember that sudden distance is especially painful for you, and that you usually do not want advice too early. I will stay with the feeling first. We do not have to explain the whole relationship tonight.

The agent should not expose private evidence casually.

It should understand without performing surveillance.

## What OpenKindred Stores

OpenKindred is designed around evidence-backed profile entries.

A profile entry is not just a sentence. It should include:

- the inferred memory
- the source that supports it
- the confidence level
- when it was last updated
- whether it is stable or temporary
- whether it requires user approval
- whether it should expire
- how agents are allowed to use it

Example categories:

- identity and language
- communication style
- active projects
- relationships and collaborators
- emotional needs
- comfort preferences
- recurring pain patterns
- working style
- decision style
- boundaries and forbidden inferences

## Principles

### 1. Consent before comprehension

OpenKindred should never assume that access equals permission.

Every data source should be opt-in. Sensitive sources should be scoped, revocable, and easy to inspect.

### 2. Evidence over vibes

The system should not quietly invent a user profile.

Every important inference should be connected to evidence. If the evidence is weak, the profile should say so.

### 3. The user owns the model

Users must be able to approve, edit, reject, export, and delete profile entries.

An AI system that claims to understand a person must also let that person correct the understanding.

### 4. Emotional memory needs boundaries

OpenKindred should help agents respond with care, not diagnose users, manipulate them, or make high-stakes claims about their mental health.

Some inferences should be blocked by default.

### 5. Agents should know quietly

A good friend does not recite your diary back to you.

Agents should use the profile to adjust tone, timing, and support, while avoiding unnecessary exposure of private details.

## Non-Goals

OpenKindred is not:

- a surveillance tool
- a digital immortality product
- a replacement for therapy
- a black-box personality test
- a generic vector database wrapper
- a single assistant app that tries to own the whole experience

OpenKindred should be infrastructure that many agents can use.

## Planned Surface

The first public version should focus on the profile layer before chasing every connector.

Planned components:

- `profile.json`: structured user model
- `evidence.jsonl`: append-only evidence log
- `wake.md`: compact startup context for agents
- local review UI for approving profile diffs
- MCP server for agent access
- connector adapters for sources such as Gmail, Notion, Calendar, GitHub, local notes, and browser history

## Safety Model

OpenKindred should treat emotional memory as sensitive infrastructure.

Important defaults:

- local-first storage
- read-only connectors by default
- no secret collection
- no silent background profiling
- source-level allow and deny lists
- profile diff review before durable writes
- expiration for temporary emotional states
- explicit "do not infer" categories

## Project Status

OpenKindred is currently at the concept and repository initialization stage.

The initial milestone is to define the profile schema, evidence model, privacy rules, and agent startup format before implementing connectors.

## Name

Kindred means close, familiar, and related.

OpenKindred is about making AI agents less like strangers and more like careful, consent-aware companions that remember the person behind the prompt.

## License

License to be decided.
