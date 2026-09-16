---
name: cybersecurity-consulting-engagement
description: >-
  Use when standing up or running engagements for a cybersecurity, due
  diligence, privacy, protection-of-persons, and investigations consulting
  practice. Covers the firm's org chart (secretary through specialist
  agents, marketing, and R&D), the authorization-first engagement
  lifecycle, the internal tool catalog mapped to the workspace's OSINT and
  forensics repositories, and the deliverable templates each service line
  produces. Invoke via /consulting-engagement or when routing a client
  request across more than one specialist agent.
---

# Cybersecurity Consulting Engagement

This skill is the operating manual for a small consulting practice built
as a set of Claude Code agents, covering six service lines:
**cybersecurity** (offensive security / pentest), **due diligence**,
**privacy**, **protection of persons**, **investigation**, and
**criminology** (geographic profiling, terrain/LIDAR search support) —
plus the support functions that keep the practice running: front-desk
intake, business development, and R&D.

## When to Activate

- Standing up this practice for the first time in a project or client
  workspace.
- A request spans more than one service line and needs routing across
  specialist agents.
- Onboarding a new tool into the firm's stack.
- Anyone asks "how does this firm work" or wants the full org chart.

## Org Chart

| Role | Agent | Function |
|---|---|---|
| Secretary / front desk | `engagement-secretary` | Intake, authorization gate, conflicts, engagement letters |
| Managing partner | `managing-partner` | Routing, sequencing, quality gate, final deliverable |
| Due diligence | `due-diligence-analyst` | Corporate/KYC screening, beneficial ownership |
| Privacy | `privacy-compliance-consultant` | GDPR, DPIA, breach response |
| Protection of persons | `close-protection-risk-analyst` | Threat assessment, travel/venue security planning |
| Investigation | `osint-investigation-agent` | Lawful OSINT field work |
| Cybersecurity (forensics) | `digital-forensics-examiner` | Evidence handling, forensic exams |
| Criminology | `criminology-analyst` | Geographic profiling, terrain/LIDAR search support |
| Cybersecurity (offensive) | `pentest-engagement-lead` | ROE, pentest methodology, findings reports |
| Marketing / BD | `consulting-marketing-lead` | Proposals, case studies, one-pagers |
| R&D | `security-consulting-rd-engineer` | Tool evaluation, internal catalog, SOPs |

This mirrors a real consulting firm end to end: nobody reaches a
specialist without going through the front desk first, and the managing
partner — not any individual specialist — owns what actually goes out
the door to a client.

## Engagement Lifecycle

1. **Intake** — every request starts at `engagement-secretary`. It is the
   only agent authorized to issue a `ROUTE` decision to a specialist.
2. **Authorization gate** — no specialist begins investigative, technical,
   or protective work without a documented lawful basis: a signed
   engagement letter, ROE, consent, or a specific legal/regulatory
   obligation. See each agent file's "Preconditions" or "Pre-Flight
   Check" section.
3. **Assignment** — `managing-partner` dispatches the authorized scope to
   the right specialist(s), sequencing rather than parallelizing when
   workstreams touch the same subject.
4. **Execution** — each specialist works strictly inside its scope and
   reports findings with explicit confidence levels (Confirmed /
   Reported / Unconfirmed — used consistently across
   `due-diligence-analyst` and `osint-investigation-agent`).
5. **Quality gate** — `managing-partner` checks every output stayed
   inside the authorized scope before it is included in a deliverable.
6. **Delivery** — a single assembled report per the format in
   `agents/managing-partner.md`.
7. **Close-out** — retention/destruction date from the engagement letter
   is confirmed and stated in the final deliverable.

## Authorization-First Principle

This is the practice's one non-negotiable rule, repeated in every
specialist agent: **lawful basis and documented scope come before
technique.** A client's confidence that something happened, or a
compelling business reason to know, is not itself a lawful basis. When in
doubt, the correct move is always to route back through
`engagement-secretary` for the missing documentation — never to proceed
on an inferred mandate.

## Internal Tool Catalog

`security-consulting-rd-engineer` owns and extends this catalog. It maps
the firm's tooling to categories of the workspace's OSINT, forensics, and
security repositories:

| Category | Example repos | Consumer |
|---|---|---|
| OSINT collection & methodology | OSINT-Framework, flowsint, Osintgram, TorBot, Threat-Actor-Usernames-Scrape | `osint-investigation-agent` |
| Digital forensics | Autopsy, IPED, forensic-pocket-lab | `digital-forensics-examiner` |
| Attack-surface recon | web-check, glassbox | `pentest-engagement-lead` |
| Physical / RF / geospatial | RF-Secure-Radar, G_Wardrive, NevM69-perimeter-radar | `close-protection-risk-analyst` |
| Criminology / geo-profiling / LIDAR | GEOLIDARIS, PhenoVisio-Forensic (workspace) + PySAL, PDAL, CloudCompare, lidR, WhiteboxTools, leafmap, OpenTopography, Apis Intel (external) | `criminology-analyst` |
| Legal & compliance support | paralegal | `privacy-compliance-consultant`, `engagement-secretary` |
| Reference libraries | Awesome-OSINT-List, Awesome-Pentest, CL4R1T4S | all specialists (read-only reference) |
| Internal agent tooling | agents-cli, codexskills, skills, headroom, goose, pcybox-orbis | practice's own workflow maintenance |

A repository being listed here is a methodology/category reference, not a
standing authorization to run it against a live subject — each tool still
needs an R&D-approved SOP and a specific engagement mandate before use.

## Deliverable Templates

Each specialist agent file carries its own `## Output Format` block:

- Due diligence report — `agents/due-diligence-analyst.md`
- Privacy assessment — `agents/privacy-compliance-consultant.md`
- Protective risk assessment — `agents/close-protection-risk-analyst.md`
- OSINT investigation report — `agents/osint-investigation-agent.md`
- Forensic examination report — `agents/digital-forensics-examiner.md`
- Criminological analysis memo — `agents/criminology-analyst.md`
- Penetration test report — `agents/pentest-engagement-lead.md`

Standing template, maintained by `security-consulting-rd-engineer` per the
firm's own internal-tooling survey (no external ROE generator was found
mature enough to adopt as-is):

- Rules of Engagement — `skills/cybersecurity-consulting-engagement/templates/rules-of-engagement.md`

`managing-partner` assembles these into the final client-facing report.

## Examples

```
/consulting-engagement due-diligence "Pre-investment screening of Acme SAS, France, per signed engagement letter EL-2026-014"
/consulting-engagement privacy "DPIA for a new customer-analytics feature"
/consulting-engagement protection "Executive travel risk assessment, Q4 conference circuit"
/consulting-engagement investigation "Trace public digital footprint of a suspected fraud counterparty per mandate M-2026-07"
/consulting-engagement criminology "Prioritize a search zone from 4 related incident sites, per mandate with local law enforcement"
/consulting-engagement pentest "External web app pentest, signed ROE attached"
```

## Anti-Patterns

- **Skipping the front desk** because the requester "obviously" has
  authorization — verify it in writing every time.
- **Running specialists in parallel on the same subject** without
  sequencing — this hides scope creep that would be visible at a handoff.
- **Treating a tool in the catalog as pre-authorized** for any use —
  catalog membership and per-engagement authorization are separate gates.
- **Publishing marketing material** with real client or subject detail
  that has not cleared `consulting-marketing-lead`'s confidentiality gate.

## Related Skills

- `market-research`, `brand-voice`, `content-engine` — for
  `consulting-marketing-lead` campaign execution.
- `configure-ecc` — for installing this practice's agents alongside the
  rest of the ECC plugin.
