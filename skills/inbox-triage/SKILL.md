---
name: inbox-triage
description: "Triage and surveillance protocol for message streams (inbox/sentinel): watermarks, high/medium/low triage, BLUF, draft-only replies, anti-duplicates, hard time budgets, outbound cross-check. Use for any recurring mailbox or chat reading. Never use to send or modify messages (strict read-only)."
---

# Inbox Triage & Surveillance

## Principle

Monitor, triage, draft. Never send (see `outbound-gate`). Passive surveillance
(reading, triaging, logging) is always allowed; every outbound action needs
explicit item-by-item approval.

## Watermarks (the "already seen" reference)

- `last_seen` timestamps (ISO) per stream: only process what is newer.
- **Never a gap**: advance the watermark only over what was actually read.
  Total read failure → watermark unchanged, next run catches up.

## Triage (verified content only)

- **HIGH**: action expected from the operator, close deadline, operational
  risk, senior stakeholder. → notify + draft reply.
- **MEDIUM**: useful for the operator's work, not urgent. → notify during
  working hours, else queue for the morning batch.
- **LOW**: FYI, newsletters, copies. → never notify, morning batch.
- One-sentence reason, in the operator's language. **Never triage without
  verified message text**: without content, the item is "unverified" — neither
  triaged nor notified.

## Analysis and draft

- BLUF 1–3 lines: what it is about, what is expected of the operator,
  deadline/risk.
- Replies follow the operator's templates. **DRAFT ONLY**, never send.
- Never invent a fact (name, date, figure, attachment): missing → `[TO COMPLETE]`.

## Outbound cross-check

For every message the operator sent, check consistency with their announcements.
Any **GAP** ("I just sent it" with no matching sent item within 30 min,
incoherent recipient/thread, announced action never executed) = **HIGH
priority**, format: 🔴 GAP + factual description + what to verify. Normal
outbounds → logged only, never notified. Doubt → "to verify", not a gap.

## Anti-duplicates

Daily JSONL journal (one JSON line per item: run timestamp, source, id, from,
subject, message date, triage). Never re-report an item or gap already logged
(check today + yesterday).

## Read hygiene

- **Strict serialization**: never two browser reads in parallel on a shared
  profile — they sabotage each other.
- Before each read task: verify none is already running; if busy, wait once,
  then skip the source for this run (watermark unchanged).
- **Hard budgets**: e.g. 10 min inbox / 8 min chat. At budget end: immediate
  partial return, never a silent timeout.
- Retry: exactly one retry after 90s on immediate failure; 2nd failure →
  abandon the source for this run.
- If a task's result never arrives: re-read its activity log before concluding
  failure.

## Operating rules

- Working hours defined once (operator's timezone); outside hours, medium/low
  queue for the morning batch.
- Nothing new → total silence (minimal timestamped line only if the protocol
  requires it).
- Source unavailable: at most 1 notification per day, then silence.
