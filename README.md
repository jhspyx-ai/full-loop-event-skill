# B2B Event Agent

An end-to-end event marketing system for companies, built as a single skill. It runs **11 specialised agents in sequence within one conversation** — from collecting the event brief to producing the post-event ROI report — passing information forward automatically so nothing is asked twice.

One conversation takes a single event from "we're doing a thing" to a complete, on-brand campaign: brief, campaign naming, deliverables checklist, event page copy, design briefs, email sequence, social pack, registration setup, content review, and ROI tracking.

---

## What it does

| # | Agent | Output |
|---|---|---|
| 01 | Event Brief | Structured 9-section brief + reusable Event Context block |
| 02 | Campaign Name | CRM campaign name, variants, and UTM parameter table |
| 07 | Deliverables Checklist | 5-phase task tracker with dependencies and risk flags |
| 04 | Event Page Copy | Full registration-page copy, section by section |
| 05 | Design Brief | One spec block per asset, with exact dimensions and copy |
| 03 | Email Sequence | Full invite-to-follow-up sequence using a 5-type email system |
| 06 | Social Media Pack | LinkedIn + X posts across 6 event stages |
| 08 | Registration Setup | A ready-to-configure event-platform setup spec |
| 09 | Content Review | A 7-check quality gate with a clear verdict on any asset |
| 10 | Dashboard & ROI | Pre-event tracking setup and a post-event ROI report |
| 11 | Sponsorship Sales Brief | A sales-team briefing for sponsored third-party conferences |

Agents 07 and 09 stay live throughout — you can update the checklist or ask for a review of any asset at any point in the conversation.

**Running order:**

```
[Company Setup] → 01 → 02 → 07 → 04 → 05 → 03 → 06 → 08 → 09 → 10 (pre) → [event] → 10 (post)
```

For sponsored third-party events, Agent 11 also runs after Agent 02.

---

## The key idea: Company Context

Everything brand-specific lives in **one Company Context block** that the agent collects once at the start of the conversation. Every downstream agent reads from it silently. To use this skill for your company, you fill this in once:

- Company name, what you do, and your approved "About" boilerplate
- Products / solutions you position at events
- Industry and your real audience segments
- Brand colours, typography, logo rules, voice, and tagline
- Languages (English only, or English plus a secondary language)
- Your tool stack: CRM, email platform (ESP), and event platform
- Your social handles

No code or prompt-editing required to adapt it to a new company — the agent asks for these details or reads them from a brand guide you provide.

---

## How to use it

This is a Claude Agent Skill. There are two common ways to run it:

**As a skill.** Place the `b2b-event-agent` folder (containing `SKILL.md`) into your Claude skills directory, or upload it wherever your Claude environment accepts skills. Then start a conversation and say something like "plan an event" or "set up an event brief" — the skill triggers automatically.

**As project instructions.** In Claude.ai, create a Project, open *Project instructions*, and paste the body of `SKILL.md` (everything below the YAML frontmatter). Upload your brand guide and any past event materials as knowledge files. Start a new chat in that project for each event.

Either way: start a new conversation per event. Answer the brief questions in batches, and the system carries your answers all the way through to the ROI report.

---

## What's reusable vs. what you customise

**Reusable across any B2B company (built in):**
- The voice and copy rules — no hype words, no em dashes, peer-to-peer tone
- The 5-type email system (straight invite, value/content, conference/booth, recap, follow-up)
- The LinkedIn and X post-type system
- Tone calibration for receptions vs. seminars vs. sponsored conferences
- The 7-check content review, the 5-phase checklist, and the two-mode ROI report

**You customise (via Company Context):**
- Brand identity, products, boilerplate, tool stack, and languages

---

## Repository structure

```
b2b-event-agent/
└── SKILL.md      # the full system — frontmatter + all 11 agents
README.md         # this file
```

---

## Notes

- The skill never invents facts. Missing speaker credentials, partner stats, or attendance figures are left as placeholders rather than fabricated.
- If your company is English-only, all secondary-language output is skipped automatically.
- One event per conversation. For a conference week with a booth, a reception, and a panel, run each as its own conversation.

---

## License

Add your preferred license here (e.g. MIT) or mark the repository private if it contains internal brand information.
