# Rules of Engagement (ROE) Template

Copy this template for every penetration test / offensive security engagement.
`pentest-engagement-lead` will not scope, plan, or discuss technique for a
target until a version of this document is signed by an authorized
representative of the client. Fill every bracketed field — do not leave a
field blank and do not infer a value that was not explicitly confirmed by
the client.

---

## Rules of Engagement

**Engagement reference:** `[e.g. ROE-2026-0142]`
**Prepared by:** `[consultant name / firm]`
**Prepared for:** `[client legal name]`
**Date:** `[date]`

### 1. Parties and Authorization

| Field | Value |
|---|---|
| Client legal name | `[...]` |
| Authorized signatory | `[name, title]` |
| Signatory's authority to bind the client | `[confirmed how — e.g. board resolution, employment title]` |
| Testing provider | `[firm / consultant name]` |
| Lead tester(s) | `[name(s)]` |

This document constitutes the sole authorization for the testing described
below. Testing outside its scope, window, or methods is **not** authorized
by this document, regardless of verbal instructions received during the
engagement.

### 2. Scope

**In-scope assets** (be specific — IP ranges, domains, application URLs,
physical addresses, named accounts):

- `[...]`
- `[...]`

**Explicitly out of scope** (name it even if it seems obviously excluded —
shared/third-party-hosted infrastructure, production payment systems,
anything the client does not itself own or control):

- `[...]`
- `[...]`

**Ownership confirmation:** the client confirms it owns or has documented
authority to authorize testing of every in-scope asset above.
`[ ] Confirmed`

### 3. Testing Types and Methodology

`[ ] Network infrastructure` `[ ] Web application` `[ ] API`
`[ ] Social engineering` `[ ] Physical` `[ ] Wireless` `[ ] Other: ___`

**Methodology / standard followed:** `[e.g. OWASP Testing Guide / ASVS for
web applications, PTES or NIST SP 800-115 for network engagements]`

### 4. Testing Window

| Field | Value |
|---|---|
| Start date/time | `[...]` |
| End date/time | `[...]` |
| Blackout periods (no testing) | `[dates/times, or "none"]` |
| Time zone | `[...]` |

Testing must not begin before the start time or continue past the end
time without a signed amendment to this document.

### 5. Rules and Limits

| Rule | Value |
|---|---|
| Denial-of-service / availability-impacting testing authorized | `[ ] Yes  [ ] No (default: No)` |
| Social engineering of employees authorized | `[ ] Yes  [ ] No` — if yes, list authorized pretexts/targets: `[...]` |
| Production data may be viewed but not exfiltrated, modified, or deleted | `[ ] Confirmed` |
| Discovered credentials/access will not be used beyond confirming the finding | `[ ] Confirmed` |
| Testing tools/techniques excluded by the client | `[list, or "none"]` |

### 6. Communication and Stop-Work

| Field | Value |
|---|---|
| Client emergency contact | `[name, phone, available hours]` |
| Testing team emergency contact | `[name, phone, available hours]` |
| Status check-in cadence | `[e.g. daily email summary]` |
| Stop-work authority | Either party may halt testing immediately by contacting the emergency contact above; testing resumes only after both parties confirm in writing. |

**Critical-finding escalation:** any finding indicating active compromise
by a third party (not the test team) is reported to the client emergency
contact immediately, not held for the final report.

### 7. Data Handling

| Field | Value |
|---|---|
| Data accessed during testing | Treated as confidential; not copied outside the engagement's secure storage. |
| Retention period after engagement close | `[...]` |
| Destruction method and confirmation | `[...]` |
| Report distribution list | `[names / roles authorized to receive the final report]` |

### 8. Safe Harbor

The client authorizes the testing described in this document and agrees
that, for activity conducted strictly within this scope and window, the
testing team will not be pursued for civil or criminal action under
computer-crime, unauthorized-access, or similar law. This authorization
does not extend to any activity outside the scope, methods, or window
defined above.

### 9. Signatures

| | Name | Title | Signature | Date |
|---|---|---|---|---|
| Client | `[...]` | `[...]` | `[...]` | `[...]` |
| Testing provider | `[...]` | `[...]` | `[...]` | `[...]` |

---

## Internal Checklist Before Testing Begins

- [ ] Both signatures obtained and dated
- [ ] Scope confirmed against assets the client can actually demonstrate ownership of
- [ ] Testing window does not overlap a client-declared blackout period
- [ ] Emergency contacts tested reachable before day one
- [ ] `engagement-secretary` has this ROE on file for the mandate reference
- [ ] Report distribution list matches the signatories' authorization
