# Agent Training Methodology

**A field-tested system for making AI agents reliable in production.**
12 executable skills · 1 rules framework · 1 lessons log · 1 deterministic linter (Python).

*By Jean Cyrille Dahani — built over months of daily production use.*

## BLUF

Most AI agents fail the same way: they narrate instead of executing, claim without
proof, and treat good intentions as mechanisms. This methodology is the opposite —
it was built the hard way, over months of daily production use, by turning every
real failure into a **mechanism** (a script, a gate, a checklist, a register), never
into a note of intent.

What you get here:

- **`skills/`** — 12 self-contained, executable agent skills. Each one was distilled
  from at least 3 real observed executions, ships with triggers, a procedure, an
  output contract, and anti-patterns. No advice without a mechanism.
- **`rules-framework.md`** — the 7 generic rules that govern everything: proof before
  claim, typed evidence, mandatory adversarial review, a mechanical gate before any
  consequential outbound action, and a multi-model decision pipeline.
- **`lessons.md`** — the transferable lessons, one line each. Every lesson was paid
  for by a real mistake.
- **`skills/pre-delivery-lint/bin/pre_delivery_lint.py`** — a deterministic,
  zero-cost pre-delivery linter (dates, language mix, unsourced numbers, unhedged
  risk claims, missing "not verified" section). The doctrine as an executable.

## How it was built

1. **Observe** — a practice that works, on real cases, at least 3 times.
2. **Distill** — extract triggers, sequence, decision rules, anti-patterns
   (see `skills/cognitive-distillation/SKILL.md` for the method itself).
3. **Mechanize** — turn it into a gate, a linter, or a checklist. A rule without
   an execution mechanism is worthless.
4. **Lock** — a rule can only be changed by explicit order of the operator, never
   by the agent itself.

## Design principles

- **Proof before claim.** "Done / sent / fixed" does not exist without a pasted
  proof: the command, its exit code, a machine timestamp, the file.
- **Typed evidence.** Every statement is labeled ESTABLISHED (dated source),
  ASSESSMENT (judgment), or UNCERTAIN (to verify). An untyped list is not a diagnosis.
- **The pilot is never their own examiner.** Every important deliverable passes an
  independent adversarial review before it ships.
- **Failure becomes infrastructure.** One line of admission, immediate correction,
  and the lesson is locked as a rule or a script the same day.
- **Never refuse on assumption.** Verify first; declare a limit only on proven failure.

## Sanitization note

This is a **public, sanitized** version prepared for portfolio use. Internal
employer references, colleague names, operational figures, internal documents,
and personal identifiers have been removed or generalized. The mechanisms are
intact; the context is not. Nothing here was pushed anywhere — publication is
the author's explicit decision.

## Structure

```
portfolio-methodologie/
├── README.md
├── rules-framework.md      # the 7 generic rules
├── lessons.md              # transferable lessons, one line each
└── skills/
    ├── pre-delivery-lint/          # deterministic pre-delivery linter + script
    ├── zero-failure-doctrine/      # never say "impossible" before exhaustion
    ├── evidence-first-reasoning/   # execute first, timestamped proof, typed honesty
    ├── agent-handoff/              # the pivot block for inter-agent context passing
    ├── external-skill-vetting/     # 6-gate vetting grid for external skills/prompts
    ├── inbox-triage/               # watermark-based triage of message streams
    ├── auto-meeting-prep/          # 3-tier automatic meeting preparation
    ├── scored-evaluation/          # 10-axis scored evaluation, proof per score
    ├── cognitive-distillation/     # turn real practice into executable skills
    ├── outbound-gate/              # 5-lock pipeline before any outbound action
    ├── multi-lens-review/          # stress-test decisions with distinct lenses
    └── solution-first-posture/     # direct solution + 2 alternatives + limits
```

## Status

DRAFT — prepared for review. Not published.
