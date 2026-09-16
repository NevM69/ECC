---
description: Run a cybersecurity, due diligence, privacy, protection-of-persons, investigation, or criminology consulting engagement through the firm's intake, routing, and reporting workflow.
allowed-tools: ["Read", "Grep", "Glob", "WebSearch", "WebFetch", "Write"]
---

# /consulting-engagement

Run a client engagement through the practice built in
`skills/cybersecurity-consulting-engagement`: intake and authorization
check, routing to the right specialist agent(s), and an assembled final
report.

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

1. **Intake** — `engagement-secretary` verifies the requesting party,
   subject, lawful basis/mandate, conflicts of interest, and scope
   boundaries. No specialist agent runs before this returns a `ROUTE`
   decision.
2. **Routing** — `managing-partner` assigns the authorized scope to the
   named service-line agent(s), sequencing multi-line engagements.
3. **Execution** — the specialist agent produces its findings in its
   documented output format, staying inside the authorized scope.
4. **Assembly** — `managing-partner` compiles the final client-facing
   report, including a data-retention/destruction note.

## Brief Template

```markdown
Requesting party: [who is asking, on whose behalf]
Subject: [organization / system / named individual(s)]
Lawful basis: [engagement letter | ROE | consent | legal obligation]
Scope — in: [...]
Scope — out: [...]
Timeline: [start / end date]
```

If the lawful basis or scope is missing, the command returns an
engagement-letter or ROE draft instead of proceeding — this is expected
behavior, not a failure.

## Examples

```
/consulting-engagement due-diligence Pre-investment screening of a French target company, signed engagement letter EL-2026-014 attached.
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
