---
name: cybersecurity-consulting-engagement
description: >-
  Use when standing up or running engagements for a solo-operated
  cybersecurity, due diligence, privacy, protection-of-persons,
  investigation, and criminology practice. Covers the firm's org chart
  (secretary through specialist agents, marketing, and R&D), the
  intake-first engagement lifecycle, the internal tool catalog mapped to
  the workspace's OSINT and forensics repositories, and the deliverable
  templates each service line produces. Invoke via /consulting-engagement
  or when routing a request across more than one specialist agent.
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

- Standing up this practice for the first time in a project workspace.
- A request spans more than one service line and needs routing across
  specialist agents.
- Onboarding a new tool into the firm's stack.
- Anyone asks "how does this firm work" or wants the full org chart.

## Org Chart

This is a solo-operated practice — one operator, no external clients. The
front desk exists to make sure a specialist knows what it's doing and why
before it starts, not to manage a client roster.

| Role | Agent | Function |
|---|---|---|
| Secretary / front desk | `engagement-secretary` | Subject, purpose, scope — one line each |
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

Nobody reaches a specialist without going through the front desk first,
and the managing partner — not any individual specialist — owns what
actually goes into the final report. That structure exists for one
reason: to make sure a specific real subject, purpose, and scope are on
record before an agent starts researching or acting on a real person or
system. It's not about paperwork, and it doesn't loosen just because
there's only one operator.

## Engagement Lifecycle

1. **Intake** — every request starts at `engagement-secretary`, which
   confirms subject, purpose, and scope in one line each and either
   routes or asks the one missing thing.
2. **Assignment** — `managing-partner` dispatches the request to the
   right specialist(s), sequencing rather than parallelizing when
   workstreams touch the same subject.
3. **Execution** — each specialist works strictly inside its stated scope
   and reports findings with explicit confidence levels (Confirmed /
   Reported / Unconfirmed — used consistently across
   `due-diligence-analyst` and `osint-investigation-agent`). Each
   specialist's own hard bans (no unauthorized access, no surveillance of
   a private individual without a stated legitimate purpose, no targeting
   protected characteristics, no ROE-less pentesting) are fixed — intake
   being lightweight doesn't touch them.
4. **Quality gate** — `managing-partner` checks every output stayed
   inside the stated scope before it is included in a deliverable.
5. **Delivery** — a single assembled report per the format in
   `agents/managing-partner.md`.
6. **Close-out** — if personal data was touched, note a sensible
   retention/destruction point in the final deliverable.

## Fast Intake, Fixed Limits

The practice moved away from client-firm bureaucracy (signed engagement
letters, cross-client conflict checks) — there's one operator, and that
paperwork didn't fit. What stayed, and stays non-negotiable regardless of
firm size, is each specialist's own hard bans: no unauthorized access, no
surveillance of a private individual without a stated legitimate purpose,
no targeting protected characteristics, no pentesting without a signed
ROE, no presenting profiling as proof. `engagement-secretary` needs one
line of purpose before routing — not because the operator needs
supervising, but because a specialist can't tell "research with a reason"
from "surveillance because you're curious" without being told which one
it is.

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
needs an R&D-approved SOP and a stated purpose/scope from
`engagement-secretary` before use.

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

`managing-partner` assembles these into the final report.

## Examples

```
/consulting-engagement due-diligence "Pre-investment screening of Acme SAS, France"
/consulting-engagement privacy "DPIA for a new customer-analytics feature"
/consulting-engagement protection "Executive travel risk assessment, Q4 conference circuit"
/consulting-engagement investigation "Trace public digital footprint of a suspected fraud counterparty"
/consulting-engagement criminology "Prioritize a search zone from 4 related incident sites, coordinating with local law enforcement"
/consulting-engagement pentest "External web app pentest, signed ROE attached"
```

## Anti-Patterns

- **Skipping intake entirely** — even one line of subject/purpose/scope
  matters; routing on nothing means a specialist can't tell a legitimate
  request from surveillance dressed up as one.
- **Turning intake back into paperwork** — a signed document, a
  cross-client conflict check — for a solo operator that's friction with
  no safety benefit; keep it to one line each.
- **Running specialists in parallel on the same subject** without
  sequencing — this hides scope creep that would be visible at a handoff.
- **Treating a tool in the catalog as pre-authorized** for any use —
  catalog membership and a stated purpose/scope are separate gates.
- **Publishing marketing material** with real subject detail that has not
  cleared `consulting-marketing-lead`'s confidentiality gate.

## Related Skills

- `market-research`, `brand-voice`, `content-engine` — for
  `consulting-marketing-lead` campaign execution.
- `configure-ecc` — for installing this practice's agents alongside the
  rest of the ECC plugin.
