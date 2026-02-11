---
name: blueprint
description: How to approach any code change — from quick features to large architecture. Activates whenever planning, implementing, or structuring work. Scales rigor to task size.
user-invocable: true
disable-model-invocation: false
---

# Blueprint

This is how you approach work. Not a ceremony — a disposition. These instincts apply to every change, scaled to fit.

## Rules (always active)

- **Ask relentlessly.** If something is even slightly ambiguous, ask. If you think you know the answer but aren't 100% sure, ask. Err on the side of annoying me over assuming wrong. The only dumb question is the one you didn't ask that led to a wrong assumption. Once I've answered, that answer is settled.
- **Delegate via subagents.** Break work into discrete tasks and hand them to subagents wherever possible to preserve context window quality. Each subagent task should be self-contained with clear inputs and expected outputs.
- **Scale to the task.** A one-file feature doesn't need a formal 5-phase document. But it still needs the same thinking: understand first, know what "done" looks like, sanity-check yourself, then confirm before building. Use your judgment on how much structure to surface vs. internalize.

## The Phases

### 1 — Discovery

Understand before you act.

- **Background:** What exists today? Gather the relevant context.
- **Problem:** What's broken, missing, or insufficient? One clear paragraph.

For small tasks this can be a few sentences. For large ones, be thorough.

### 2 — Requirements

The "done" checklist. What must be true for this work to ship? These are your acceptance criteria — every decision traces back to one of these. Nothing more, nothing less.

For a quick feature, this might be 2-3 bullets. For a system redesign, it's a full list.

### 3 — Proposed Solution

The plan. Structured so anyone handed it cold could execute with zero guesswork:

- Ordered steps with explicit inputs, outputs, and dependencies
- File paths, function signatures, and data shapes where relevant
- No implicit knowledge or assumed context

For small changes, this can be a brief outline. For large ones, be precise.

### 4 — Self-Critique

Pressure-test before presenting:

- Is every step **in scope**? Cut anything not tied to a requirement.
- Is the ordering **logically sound**? Would any step fail because a dependency hasn't been met?
- Are there **gaps**? Steps where a reader would need to fill in unstated details?

Revise based on findings. For small tasks, do this internally. For large ones, show your work.

### 5 — Sync

Quick conversational check-in. A few sentences on what you think we're building and why. "Making sure we're on the same page" not "presenting a document." Ask if anything's off. Don't start building until I confirm.

This step always happens out loud, regardless of task size.
