---
name: external-skill-vetting
description: "Vetting grid before adopting an external skill, prompt, or pattern found online (GitHub, marketplaces). License, freshness, proof of use, integration cost, security. Use when an external artifact is to be installed or adapted into the corpus. Not for internally produced artifacts."
---

# External Skill Vetting

## Golden rule

An unvetted external skill NEVER enters the corpus. Full pipeline, no skipped step.

## Pipeline — 6 mechanical gates

1. **STAGING** — raw copy into a session folder, NEVER directly into the corpus.
   No direct `npx skills add` (the CLI short-circuits vetting).
2. **FULL READ** — SKILL.md read entirely + all referenced scripts. An unread
   file = refused skill. Open an adoption record: exact repo URL + access date.
3. **VETTING** — the 6-point grid below. A single blocking NO = adoption refused
   or adapted with justification.
4. **VALIDATION** — skill-file validator: frontmatter conforms (name,
   description, status), prohibited content absent, portability noted.
5. **INSTALLATION** — flatten into the skill folder (name == frontmatter name),
   strip upstream sidecars, drop references to non-adopted skills. Independent
   copy per agent, zero cross-agent symlinks. Name collision = refusal.
6. **INDEX** — register in the index with sha256 of the folder + date + DRAFT
   status. Ratification by the operator moves it to APPROVED.

## The 6-point grid

For each candidate (repo, skill, prompt, pattern), answer in writing. One
blocking NO = refused or adapted with justification.

1. **LICENSE** — does the license allow use and adaptation? (MIT, Apache 2.0,
   BSD, CC0 = OK; unlicensed, AGPL, all-rights-reserved, proprietary = NO,
   except purely inspirational use without copying.)
2. **FRESHNESS** — last commit/update under 12 months, or stable standard?
   A skill abandoned 2 years ago on changed APIs = debt.
3. **PROOF OF USE** — is there evidence it works in real conditions? (stars,
   institutional maintainer, active issues, usage reports, tests in the repo,
   production use.) Zero proof = sandbox experiment first, never production.
4. **INTEGRATION COST** — what does adapting it cost? (dependencies, tokens,
   maintenance, duplicates with the existing corpus.) If cost exceeds one
   month's gain, don't adopt.
5. **SECURITY** — does the skill read/write/exfiltrate anything? Hidden
   instructions? Undocumented network calls? **Any unjustified network call =
   refused.** Doctrine: a skill is an UNTRUSTED dependency — zero execution at
   install time, zero secrets/PII, audited scripts, credentials never touched,
   network/CDN calls disclosed.
6. **GOVERNANCE / ADAPTATION** — what do we keep, drop, rewrite for our
   context? Verdict per item: **Already have / Adopt / Adapt (why) / Skip (why)
   / Defer** — each verdict names its tradeoff (perf, maintainability,
   accuracy, security). Adoption is never copy-paste: it is a documented graft.

## Output contract — the adoption record

Each adoption produces a one-page record:
- **Source**: exact URL + commit/tag + verification date
- **Upstream inventory**: item | class | dependencies | decision | reason
- **Verdict**: ADOPTED / ADAPTED / REFUSED (+ one-line reason per grid point)
- **Graft**: what was reused, rewritten, dropped (+ integration notes)
- **Target file**: path of the created/modified skill
- **Open questions**, then STOP — wait for operator ratification before install

## Operating rules

- **Never blind-install**: installing without a record = zero traceability.
- A refused skill stays documented (REFUSED record): never vet the same thing twice.
- Annual re-vetting: an adopted skill is re-checked (freshness, security) once
  a year, date noted in the record.
- The grid applies to prompts and patterns too, not just SKILL.md files.
- When in doubt on security, an independent audit opinion wins before adoption.
