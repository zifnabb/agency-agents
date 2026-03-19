Audit framework: Retail Payment Activities Act (RPAA) and Regulations
Source documents:
- compliance/Source Docs/PDFs/RPAA/SOR-2023-229.pdf (Retail Payment Activities Regulations)
- compliance/Source Docs/PDFs/RPAA/R-7.36.pdf (Retail Payment Activities Act)
- compliance/Source Docs/PDFs/RPAA/operational-risk-and-incident-response.pdf (Bank of Canada guidance)
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 1 — Read the source documents
Read all three RPAA source documents and list the applicable requirements for each of:

**A. Operational Risk Management Framework:**
- A1: Operational risk management policy and governance
- A2: Risk identification and assessment (ongoing)
- A3: Risk mitigation controls (preventive/detective/corrective)
- A4: Third-party and outsourcing operational risk
- A5: Review, testing, and continuous improvement

**B. Incident Response and Notifications:**
- B1: Incident response procedure (detection, triage, containment, recovery)
- B2: Notice of incident to the Bank of Canada
- B3: Notice of incident to affected persons
- B4: Incident record and evidence management

**C. Registration and Reporting:**
- C1: PSP registration (if applicable)
- C2: Annual report preparation and submission
- C3: Notification of material changes

**D. Recordkeeping:**
- D1: Record creation, retention, and retrieval
- D2: Regulatory access and examination support

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/rpaa/templates/control-assessment-record.md — the per-requirement assessment template
2. compliance/audit-templates/rpaa/controls/rpaa-requirements.md — the requirements register
3. compliance/audit-templates/rpaa/controls/scope-and-psp-profile.md — PSP scope and profile

### Step 3 — Determine applicability
Review business documents for indicators of payment service provider (PSP) status. Fill compliance/audit-templates/rpaa/controls/scope-and-psp-profile.md. If PSP status cannot be confirmed, state this and note that RPAA applicability must be confirmed before this assessment can be considered authoritative.

### Step 4 — Fill the assessment records
For each requirement area (A1–A5, B1–B4, C1–C3, D1–D2), fill one control-assessment-record.md verbatim. Same sections, same labels, same order.

Also update compliance/audit-templates/rpaa/controls/rpaa-requirements.md with status, owner, evidence, and notes.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/PDFs/RPAA/[filename] — [Section / Requirement area]
```

### Step 6 — Cite evidence on every finding
Every finding must include either:
```
Evidence: compliance/business-documents/PDFs/[filename]
```
or:
```
Evidence: MISSING — evidence request raised
```

---

## Mandatory Rules

**Applicability first:** RPAA obligations depend on PSP status. If PSP status cannot be confirmed, all findings must be qualified with: "Subject to confirmation of PSP status under the Retail Payment Activities Act."

**Bank of Canada notification requirements:** Pay particular attention to incident notification triggers, timelines, and approval requirements. These are time-sensitive obligations with regulatory consequences.

**No readiness scores:** Do not produce an overall readiness score. Use per-requirement Pass/Partial/Fail results from the template instead.

**No effort estimates:** Do not produce effort estimates in days or weeks.

**No invented structure:** Your output must match the control-assessment-record.md section-for-section.

**Status vocabulary — register:**
- `Implemented`
- `In Progress`
- `Planned`
- `Not Applicable`

**Status vocabulary — assessment:**
- `Pass`
- `Partial`
- `Fail`

---

## Output Files

Create a dated output folder and place all deliverables inside it:

**Output folder:** `compliance/outputs/rpaa-audit-[DATE]/`

1. `compliance/outputs/rpaa-audit-[DATE]/scope-and-psp-profile.md` — completed PSP profile
2. `compliance/outputs/rpaa-audit-[DATE]/rpaa-requirements.md` — updated requirements register
3. `compliance/outputs/rpaa-audit-[DATE]/requirement-assessments/` — one assessment per requirement area
4. `compliance/outputs/rpaa-audit-[DATE]/executive-summary.md` — overall findings summary with finding counts by result
5. `compliance/outputs/rpaa-audit-[DATE]/evidence-requests.md` — consolidated MISSING evidence list

---

## Supporting Templates (read before assessing)

- PSP profile → compliance/audit-templates/rpaa/controls/scope-and-psp-profile.md
- Requirements register → compliance/audit-templates/rpaa/controls/rpaa-requirements.md
- Assessment record → compliance/audit-templates/rpaa/templates/control-assessment-record.md
- Operational risk policy → compliance/audit-templates/rpaa/policies/operational-risk-and-incident-response-policy.md
- Incident notification checklist → compliance/audit-templates/rpaa/templates/incident-notification-checklist.md
- Incident record → compliance/audit-templates/rpaa/templates/incident-record.md
- Operational risk register → compliance/audit-templates/rpaa/templates/operational-risk-register.md
- Operational risk assessment → compliance/audit-templates/rpaa/templates/operational-risk-assessment.md
- Annual report → compliance/audit-templates/rpaa/templates/annual-report-template.md
- Exception record → compliance/audit-templates/rpaa/templates/exception-record.md
