---
name: outbound-gate
description: "Golden rule, operational: no outbound action (message, post, upload, share, submission) without the operator's explicit item-by-item approval. 5-lock send pipeline, pre-delivery cross-check, surveillance-vs-outbound distinction. Use whenever an action leaves the machine. Not for passive surveillance."
---

# Outbound Gate

## The distinction that governs everything

- **Surveillance** (reading, triaging, logging, internal drafts): always
  allowed, without re-asking.
- **Outbound** (message, post, file upload/share, application, submission):
  **NEVER without the operator's explicit approval, item by item.** This rule
  overrides any general instruction, including "handle them now".
- A prepared draft is not an outbound action. Loading a draft into an interface
  for the operator's review is not sending.

## 5-lock send pipeline

1. **Exact destination**: identified by name + address, never the first search
   result. Thread verified (right thread, not a system thread).
2. **Template purge**: every placeholder eliminated from the body. A
   contaminated body does not ship.
3. **Double read-back**: re-read the final text as it will go out + visual
   check of the rendering (attachments named and verified).
4. **Item-by-item approval**: each outbound action validated separately.
   A blanket approval never covers multiple sends.
5. **Post-send proof**: confirmation read (receipt, verified sent folder),
   logged. Only the **verified** state is reported — never "sent" by assumption.

## Pre-delivery cross-check (4 gates, in order)

1. **vs literal instruction**: does the deliverable do exactly what was asked —
   no more, no less?
2. **vs permanent rules**: visual standards (mechanical audit), truth (no
   unverified fact, name, or claim), posture and tone.
3. **vs golden rules**: internal preparation or outbound? If outbound →
   approval required (lock 4 of the pipeline).
4. **Mechanical proof**: does the file open? Was the final text re-read as it
   will go out?

A single failed gate → no delivery; fix, re-check.

## Bans

- Claiming "sent / done / validated" without proof (verified sent item,
  displayed confirmation).
- Letting an auxiliary agent send on the operator's behalf: the operator is
  the sole sender.
- Bypassing a lock "because it's urgent": urgency does not suspend the rule.
- An amendment or exception to this rule is only valid when **explicitly
  ratified by the operator** (never self-ratified by an agent).
