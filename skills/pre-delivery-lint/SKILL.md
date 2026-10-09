---
name: pre-delivery-lint
description: "Deterministic pre-delivery check: dates past the evidence cutoff, mixed languages, numbers without adjacent source, unhedged risk claims, missing 'not verified' section. Use before handing over any deliverable. Executable: bin/pre_delivery_lint.py. Do not use on quick informal messages."
---

# Pre-Delivery Lint

A deterministic, zero-cost linter that catches the most expensive mistakes
**before** anyone sees the deliverable. The linter flags; the human decides.
A deliverable that fails the lint does not ship without correction or written
justification.

## Workflow

```bash
python3 bin/pre_delivery_lint.py <file> [--cutoff YYYY-MM-DD]
```

- Exit 0 + "OK" → the deliverable passes the mechanical check.
- Exit 1 + warnings → fix each flagged point, or justify in writing why it is acceptable.
- `--cutoff` = the deliverable's evidence cutoff date. Without it, the date check is skipped.

## The 5 checks

1. **DATE > CUTOFF** — no date past the evidence cutoff. Catches accidental future
   dates and stale baselines.
2. **MIXED LANGUAGE** — one deliverable = one language. Heuristic: a document that
   is mostly English but contains >25% typical French markers gets flagged
   (bilingual EN/FR detection; extend the marker lists for other pairs).
3. **"NOT VERIFIED" SECTION PRESENT** — the deliverable must declare its limits
   ("not verified", "did NOT verify"). Absent = ⚠. A deliverable with no declared
   limits pretends to know everything.
4. **RISK CLAIMS WITHOUT HEDGING** — trigger words (`famine`, `massacre`,
   `predict*`, `will collapse|fall`). Each is read with ±120 chars of context:
   without a nearby caution marker (`risk`, `alleged`, `reported`, `estimate`,
   `according to`, `unconfirmed`, `scenario`), it's a ⚠.
5. **NUMBERS WITHOUT ADJACENT SOURCE** — every aggregate like `12 500` is read
   with ±100 chars: without a nearby reference (`source`, `per`, `reported`,
   `estimate`, `according to`, recognized outlet), it's a ⚠ for manual check.
   Golden rule: **every aggregate states its base/denominator**.

## Operating rules

- The lint is **mechanical, not intelligent**: it flags candidates, it does not
  judge. False positives happen (a number with its source outside the window) —
  the human decides, fast.
- **No contradictory false alarms**: when the lint flags two figures, verify they
  measure the same thing before concluding.
- One outlet ≠ public proof. Several sites repeating the same press release ≠
  independent triangulation.
- The lint does not replace proofreading: it runs **before** the adversarial
  pass and the human review, not instead of them.
- Extend the marker lists (risk words, recognized sources) in
  `bin/pre_delivery_lint.py` only when a real case demands it — a rule without
  a real example is not added.
