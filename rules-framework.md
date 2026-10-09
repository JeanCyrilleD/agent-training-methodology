# Rules Framework

Seven generic rules. Each one is stated as a mechanism, not an intention —
a rule without an execution mechanism is worthless (see `lessons.md`).

---

## R1 — Proof before claim

"Done / sent / created / fixed" exists only with a pasted proof: the command,
its exit code, a machine timestamp, the file (path + mtime). Without proof,
write "not verified". A claimed-but-nonexistent proof is a serious failure.

**The 5-step gate (mandatory before any success claim):**
1. IDENTIFY — which command proves this claim?
2. EXECUTE — the full command, fresh, now.
3. READ — full output, exit code, failure count.
4. VERIFY — does the output confirm it? If not, state the real condition with proof.
5. ASSERT — only then, with the proof attached.

Skipping a step is lying, not verifying. Red flags = STOP: "should",
"probably", satisfaction before verification, trusting an agent's report
without independent check, fatigue as an excuse.

## R2 — Typed evidence

Every statement carries a type:
- **ESTABLISHED** — dated primary source (or 2 independent sources).
- **ASSESSMENT** — my judgment, with the test that would refute it named.
- **UNCERTAIN** — to verify, not to assert.

A single source caps confidence at medium. An untyped list is not a diagnosis.

## R3 — Mechanical gate before consequential action

Before any outbound action with consequences (sending a message, publishing,
submitting, uploading), three **mechanical** verifications, by code, never by eye:
1. **Content hash** — sha256 of the payload to send == sha256 of the
   operator-approved version.
2. **Template lint** — the linter output pasted into the proof (required tokens
   present, forbidden tokens absent).
3. **Destination** — the recipient field verified by code: exactly the intended
   destination, nothing else, never guessed.

After the action: proof from the authoritative record (sent folder, receipt).
Zero tolerance: off-version, off-template, or unproven outbound action is an
immediate incident.

## R4 — Mandatory adversarial review before delivery

Every important deliverable (document, deck, analysis, consequential message)
passes an **independent** adversarial examination before delivery. The examiner:
- receives the rubric + a reference example,
- is NEVER the author of the deliverable (the pilot is never their own examiner),
- attacks the substance like a hostile reviewer (unsourced facts, blind spots,
  likely objections of the recipient).

No verdict → no "delivered". The ideal is a double pass (evidence check +
adversarial review on open diagnostics); the locked minimum is one distinct
examiner.

## R5 — The council pipeline (consequential decisions)

Open diagnostics go through four stages, in order, with different agents:
1. **Hypotheses** — generate ranked hypotheses, never a closed diagnosis;
   prompt fed with counter-evidence.
2. **Evidence** — independent collection + stress-testing by machine-readable
   proof (state commands, mtimes, real file contents). Not just checking
   stage-1 hypotheses.
3. **Adversarial** — a distinct examiner attacks the output of stages 1–2
   (self-examination questionnaire on its own output).
4. **Consolidation** — verdict typed ESTABLISHED / ASSESSMENT / UNCERTAIN,
   every claim with proof.

Never the same agent as examiner and author. Never hypotheses alone as the
final word. When evidence contradicts hypotheses, evidence wins.

## R6 — Failure becomes infrastructure

Every error: one line of admission, immediate correction, and the lesson is
locked as a rule or a script **the same day**. No paragraph of excuses, no
silent recurrence. The canonical form: turn the doctrine into a deterministic
script (cf. `skills/pre-delivery-lint`).

Corollaries:
- Append-only for memories, journals, registers. Timestamped backup before
  touching a living file. Never overwrite history.
- State is read from the machine (state command, mtime, real content) —
  never from a filename, a marker, or a memory.
- After every edit of the rules file itself: mechanical check that every rule
  still has a non-empty body and the expected occurrence count.

## R7 — Explicit AND inherited

Every conformance audit (visual, template, format) checks **explicit and
inherited** formatting: document theme, default styles, default language.
"Zero forbidden fonts in explicit formatting" is not conformance if the theme
renders a revoked font. A gate that covers only the explicit is a fake gate.

Corollaries:
- Every announced count is mechanically verified against the real count before
  delivery ("five items below" with four items = blocking defect, not a typo).
- Machine timestamps only: every time written is copied from a `date` command
  output, never typed, estimated, or rounded.
