---
description: Run a cybersecurity, due diligence, privacy, protection-of-persons, investigation, or criminology consulting engagement through the firm's intake, routing, and reporting workflow.
allowed-tools: ["Read", "Grep", "Glob", "WebSearch", "WebFetch", "Write"]
---

# /consulting-engagement

Run an engagement through the solo-operated practice built in
`skills/cybersecurity-consulting-engagement`: a one-line intake check,
routing to the right specialist agent(s), and an assembled final report.

## Usage

```
/consulting-engagement                                   # Prompt for intake interactively
/consulting-engagement [service-line] [brief]             # Start an engagement directly
/consulting-engagement status                              # Show the firm's org chart and lifecycle
```

## Service Lines

```
/consulting-engagement due-diligence [brief]   # Corporate/counterparty/KYC screening
/consulting-engagement privacy [brief]         # GDPR/privacy program work
/consulting-engagement protection [brief]      # Personal/executive protection risk planning
/consulting-engagement investigation [brief]   # Lawful OSINT investigation
/consulting-engagement forensics [brief]       # Digital forensics / evidence handling
/consulting-engagement criminology [brief]     # Geographic profiling, terrain/LIDAR search support
/consulting-engagement pentest [brief]         # Penetration test / offensive security
/consulting-engagement tooling [brief]         # New tool evaluation for the firm's stack
/consulting-engagement marketing [brief]       # Proposals, case studies, one-pagers
```

## What It Does

1. **Intake** — `engagement-secretary` confirms subject, purpose, and
   scope, one line each. No specialist agent runs before this routes.
2. **Routing** — `managing-partner` assigns the scope to the named
   service-line agent(s), sequencing multi-line engagements.
3. **Execution** — the specialist agent produces its findings in its
   documented output format, staying inside scope and its own hard bans
   (no unauthorized access, no surveillance without a stated purpose, no
   ROE-less pentesting — these don't loosen for a solo operator).
4. **Assembly** — `managing-partner` compiles the final report, including
   a data-retention/destruction note when personal data was touched.

## Brief Template

```markdown
Subject: [organization / system / named individual(s)]
Purpose: [why, in a sentence]
Scope — in: [...]
Scope — out: [...]
```

`pentest-engagement-lead` still needs a signed ROE before testing begins
— that's proof of authorization to test a specific system, not client
paperwork, and it doesn't go away.

## Examples

```
/consulting-engagement due-diligence Pre-investment screening of a French target company.
```

```
/consulting-engagement status
```

## Agent Delegation

This command invokes:

- `engagement-secretary` — intake and authorization gate
- `managing-partner` — routing, sequencing, and final assembly
- `due-diligence-analyst`, `privacy-compliance-consultant`,
  `close-protection-risk-analyst`, `osint-investigation-agent`,
  `digital-forensics-examiner`, `criminology-analyst`,
  `pentest-engagement-lead` — service-line specialists
- `security-consulting-rd-engineer` — tooling mode
- `consulting-marketing-lead` — marketing mode

## Related Commands

- `/plan` — strategic planning before a multi-line engagement
- `/marketing-campaign` — full campaign execution once
  `consulting-marketing-lead` has cleared the confidentiality gate

---

*Part of [Everything Claude Code](https://github.com/affaan-m/everything-claude-code)*
