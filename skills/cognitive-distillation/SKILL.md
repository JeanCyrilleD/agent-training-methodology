---
name: cognitive-distillation
description: "Turn a real agent or expert practice into a SKILL.md that another agent can execute alone. Use when a working method exists only in someone's head or history (decision pipeline, triage protocol, review loop) and must become a transferable mechanism. Not for documenting a tool, nor for generic advice without observed real executions."
---

# Cognitive Distillation — from real practice to SKILL.md

## Purpose

Take a practice that works (observed on at least 3 documented real executions)
and convert it into a SKILL.md that another agent can execute alone, without
the source agent. A transfer only counts as a file, a gate, or an executable
ritual — never as an intention. Final test: the executor produces the expected
deliverable following the skill alone, without contacting the author.

## Workflow

### Phase 1 — Capture (the raw material)

1. Identify the practice: name, who executes it, on which real cases (cite the
   3 minimum executions: dates, objects, verifiable results).
2. For each execution, note: the actually-followed step sequence, tools/commands
   used, corrections made mid-course, observed input/output formats.
3. Cite the source and its date (primary URL or path adjacent to the claim).
4. Mark EMPTY anything not observed — never distill what was not seen.

### Phase 2 — Extract (4 layers, no more, no less)

1. **Triggers** — when the method applies, and especially when it does NOT.
   Format: "Use when… / Do not use for…".
2. **Sequence** — ordered steps, each with its action verb and the condition to
   move to the next.
3. **Decision rules** — 3 to 8 rules as: "When [situation], prefer [action] over
   [alternative] because [principle]." Include trade-offs (fast vs rigorous).
   One rule = one imperative sentence.
4. **Anti-patterns + limits** — what the method forbids (even when tempting),
   and its bounds: pass cost, scope, what it does not decide. Never distill a
   competence requiring a tool absent from the target environment (mark the
   dependency).

### Phase 2b — Sort into 3 classes

Each extracted element is classified: (a) **PROCEDURE** (how to do it) ·
(b) **GATE** (how to verify it was done right) · (c) **RITUAL** (when to do
it). A skill with no gate or ritual stays an intention — back to Phase 2.

### Phase 3 — Validate (double test + trial on the past, before calling it ready)

1. **Directional test** — apply the distilled method to 1 already-handled case:
   does it reproduce the same decision (directionally, not word-for-word)? If
   not, back to Phase 2.
2. **Uncertainty test** — submit it to 1 out-of-scope case: does it declare its
   limits instead of inventing an answer? A skill that sounds confident out of
   scope is overfitted: back to Phase 2.
3. **Trial on the past** — replay ≥ 3 real past cases: would the skill have
   produced the right result? Fix until yes, three times.

### Phase 4 — Build

Assemble as SKILL.md: frontmatter (`name` = folder name, `description` ≤ 1024
chars with explicit triggers, `version`, `date`, `status`, `portability`,
`prohibited_content`), then Triggers / Procedure (numbered steps) / Expected
proof (command, file, timestamp) / Limits. Budget: body < 4,000 tokens,
essentials first (truncation cuts from the end). Bulky material goes in
`references/`.

### Phase 5 — Validation gate

Run the SKILL.md validator before any handover: conforming frontmatter,
prohibitions respected, status present. Zero errors before handover; the
validator output is pasted into the proof.

### Phase 6 — Ratification

Status DRAFT → APPROVED only by the operator's explicit signature in a direct
session, then registration in the index with sha256. Without ratification, the
skill stays an internal draft.

## Output contract

Each distillation produces:
- `EXTRACTION_REPORT.md` — candidates (rules, steps) with ADMITTED/REJECTED
  status and reason.
- `SKILL.md` — the loadable, versioned, dated skill.
- `VERIFICATION_LOG.md` — test transcripts with verdicts.

## Operating rules

- **Never without 3 observed real executions.** A method told once is an
  anecdote, not a practice.
- **Never paraphrase away precision.** The practice's distinctive terms are
  kept as-is.
- **Declared limits mandatory.** A skill without bounds is a liability, not
  an asset.
- **Counter-example per rule.** Any decision rule without a case where it
  would be wrong is an untested claim.
- **Never duplicates an existing mechanical gate** — it may invoke it, never
  copy it.
- **Versioned and dated.** Practices evolve; the skill declares its time bounds.

## Demonstration — distilled real method: the council pipeline

- **Triggers**: use when a consequential decision needs several independent
  angles (diagnosis, arbitration, scored evaluation). Not for micro-decisions
  (a heavy gate on a fast action will be bypassed) nor when one angle suffices.
- **Sequence**: (1) generate RANKED hypotheses, never a closed diagnosis,
  prompt fed with counter-evidence; (2) verify with machine-readable proof
  (state commands, mtimes, real file contents); (3) distinct examiner runs
  adversarial review on stages 1–2; (4) consolidate: verdict typed
  ESTABLISHED / ASSESSMENT / UNCERTAIN, every claim with proof.
- **Decision rules**: "When evidence contradicts hypotheses, prefer evidence and
  requalify the hypotheses, because state is read from the machine, not from
  memory." / "When two examiners converge and one diverges strongly, audit the
  divergence on the criteria before averaging, because the average of an
  outlier is not an arbitration." / "When the author is also the executor,
  impose a distinct examiner, because the pilot is never their own examiner."
- **Anti-patterns**: hypotheses alone as final word; mechanically averaging
  divergent scores; the deliverable's author as adversarial examiner.
- **Bounds**: 4 passes = high cost, reserved for decisions that justify it;
  no arbitration without all contributions ("arbitration impossible", not an
  invented average).
