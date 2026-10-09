---
name: scored-evaluation
description: "Scored evaluation of any deliverable or application by a multi-examiner council with mandatory proof: 10-axis rubric, examiner split, absolute ban on scoring without evidence. Mandatory before declaring work 'delivered' or 'done'. Includes the consolidation protocol and archiving criteria."
---

# Scored Evaluation — Council Review

## 10-axis rubric (0–10 each, total /100)

1. Connection reliability (data sources, bridges, integrations)
2. Displayed content (real content, zero raw text or garbage glyphs)
3. Perceived speed (real measured response time, not estimated)
4. Design & visual standards (mechanical token audit)
5. Interactions (clicks, keyboard, loading states, error states)
6. Chat/analysis quality (relevance, grounding, language)
7. Draft quality (sharp, anchored in real history)
8. Robustness (errors, timeouts, degraded modes, recovery)
9. System autonomy (watchers, self-heal, protocols)
10. Trust & safety (operator as sole decider, locks, validation)

## Calibration

3/10 = usable with notable defects · 7/10 = solid and coherent ·
10/10 = excellent, verified on edge cases and real usage.

## Step-by-step

1. **Split the axes**: worker pool (one axis each, code provided) + chief
   examiner (architecture & rework) + external reference (UX standards) +
   **operator review (decisive)**.
2. **Proof per score**: shell measurement, screenshot, reproducible test.
   A score without proof = invalid score.
3. **Examiner honesty**: insufficient access → say so and request access,
   NEVER extrapolate.
4. **Consolidate**: top 3 severe defects + P0 (today) / P1 (week) / P2 (later)
   plan — each item: what, why, concrete how, estimated effort.
5. **Execute P0s then RE-SCORE** the affected axes with new tests. A score never
   drops without proof of a regression.
6. **Archive**: dated report + copies from all examiners in the council folder.

## Bans

Scores without proof · complacency · scoring an obsolete version · mixing
versions between examiners · uncontested self-evaluation.
