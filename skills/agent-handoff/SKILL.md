---
name: agent-handoff
description: "Standardize context passing between agents and sub-agents via the pivot block: objective, established facts with dated sources, critical unknowns, immediate action, stop condition. Use when delegating context to a sub-agent or resuming another agent's work. Not for simple information passing without expected action."
---

# Agent Handoff — the Pivot Block

Principle: facts verified upstream are neither re-requested nor re-analyzed.

## Purpose

Pass complete, actionable context from one agent to another in a single block,
without loss and without rework. A good handoff lets the recipient act
**without rereading the whole history**.

## The pivot block

Every context pass (delegation to a sub-agent, resuming another agent's work,
multi-module pipeline) uses this block, in this order:

```
[Objective | Established facts (dated sources) | Critical unknowns | Immediate action | Stop condition]
```

1. **Objective** — one sentence: what the recipient must produce or decide.
   Not the general context — the target.
2. **Established facts (dated sources)** — verified only, each with source and
   date. Example: "The board vote is on 2026-10-08 at 15:00 GMT (exchange
   notice, 2026-10-07)".
3. **Critical unknowns** — what is unknown AND changes the decision. Not a
   curiosity list.
4. **Immediate action** — the first concrete action expected, with its scope
   (read / write / do not touch).
5. **Stop condition** — when to stop: deliverable handed over, proven blockage
   (with proof), or contradiction with the objective.

## Output contract

The recipient acknowledges in one line (objective understood / blocking
question), then acts. At the end: result summary + any deviations from the
established facts.

## Operating rules

- **Verified upstream facts = acquired**: the recipient neither re-asks nor
  re-analyzes what is established. If it doubts a fact, it flags it instead of
  silently redoing it.
- **Explicit scope**: stating what is forbidden matters as much as stating what
  is asked (e.g. "read-only", "do not touch existing skills").
- **Dated sources or nothing**: a fact without source or date is a disguised
  unknown → classify it as a critical unknown.
- **One handoff = one objective**: two objectives → two handoffs. No stacking.
- **Failure = report**: if the recipient cannot finish, it reports what is done,
  what is missing, and why — never silence, never invention to "finish anyway".
- **Budget + provenance**: every delegation states a budget (time or max calls)
  and the provenance of transmitted facts. No unbounded loops.
- **Explicit plan**: multi-step mission → the recipient writes its plan in 3–5
  lines BEFORE executing; the plan is inspectable and correctable.
- The pivot block travels **with** every needed file or path: the recipient must
  not guess paths.
