---
name: auto-meeting-prep
description: "Standard 3-tier automatic prep for every upcoming meeting: T-2d object/expectation analysis, T-1d full brief + talking points, T-2h takeaways + 'say this' cheat sheet. Use whenever a new meeting with a known date is learned. Not for ad-hoc briefs outside the protocol, nor for undated meetings."
---

# Auto Meeting Prep — 3-Tier Protocol

Every upcoming meeting with a known date automatically receives the 3-tier
protocol. No meeting is prepared on reflex.

## The 3 tiers

| Tier | When | Delivered |
|---|---|---|
| **T-2d** | ~08:00, 2 days before (flexible) | Reminder + ANALYSIS: the meeting's real object, what others expect from it, recommended positioning (2–3 lines) |
| **T-1d** | ~08:00, the day before (flexible) | Full brief + TALKING POINTS: draft of what to say (opening, key points, questions, close) |
| **T-2h** | exactly 2h before (exact time) | Final cheat sheet, phone-readable: target TAKEAWAYS (2–3) + "SAY THIS": exact sentences (opening, points, closer) |

## Implementation

1. **Tracked item**: one per meeting (title, date/time, stakes). The 3 scheduled
   reminders are owned by it.
2. **3 one-shot schedules**: `T-2d`, `T-1d`, `T-2h`, in the operator's timezone.
3. **Delivery**: concise, in chat. The full brief lives in a dated file.
4. **T-2h**: condense the previous day's brief, never contradict it. If the file
   is missing, rebuild from memory and flag it.
5. Each run logs an activity entry on the tracked item.

## Rules

- Meeting times: from calendar/memory only, never invented. Verify the weekday
  mechanically.
- Never invent: facts, expectations, dynamics. Mark the uncertain.
- Tone of talking points matches the channel (chat = warm/conversational;
  formal review = factual, confident, non-defensive).
- If a meeting is cancelled or moved: update or delete the 3 schedules the same
  day, and close/adapt the tracked item.
- New meeting learned → apply this protocol immediately.
