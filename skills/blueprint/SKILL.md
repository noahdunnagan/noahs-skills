---
name: blueprint
description: Structured planning workflow. Runs discovery, requirements, solution design, self-critique, and sync before any code gets written.
metadata:
  trigger: Planning features, designing implementations, architecting changes
  author: Noah Dunnagan (https://github.com/noahdunnagan)
---

# /blueprint

Follow these phases in order before writing any code.

## Rules (always active)

- **Ask relentlessly.** If something is even slightly ambiguous, ask. If you think you know the answer but aren't 100% sure, ask. Use the question tool aggressively — err on the side of annoying me over assuming wrong. Nothing should be left to chance. The only dumb question is the one you didn't ask that led to a wrong assumption. Once I've answered, that answer is settled and you don't need to re-ask.
- **Delegate via subagents.** Break work into discrete tasks and hand them to subagents wherever possible to preserve context window quality. Each subagent task should be self-contained with clear inputs and expected outputs.

## Phase 1 — Discovery

- **Background:** Gather and state the relevant context. What exists today? What's the current state of things?
- **Problem:** Distill the core issue into a single clear paragraph. What's broken, missing, or insufficient?

## Phase 2 — Requirements

The "done" checklist. A flat list of what must be true for this work to ship. These are your acceptance criteria — every subsequent decision should trace back to one of these. Nothing more, nothing less.

## Phase 3 — Proposed Solution

The implementation plan. Structured so any developer handed it cold could execute with zero guesswork:

- Ordered steps with explicit inputs, outputs, and dependencies
- File paths, function signatures, and data shapes specified where relevant
- No implicit knowledge or assumed context

## Phase 4 — Self-Critique

Pressure-test the plan before presenting it:

- Is every step **in scope**? Cut anything not required by a requirement.
- Is the ordering **logically sound**? Would any step fail because a dependency hasn't been met?
- Are there **gaps**? Steps where a reader would need to fill in unstated details?

Revise based on findings.

## Phase 5 — Sync

Give me the quick version — a casual, conversational summary of what you think we're building and why. Think "making sure we're on the same page" not "presenting a document." A few sentences max. Ask if anything's off. Don't start building until I confirm.
