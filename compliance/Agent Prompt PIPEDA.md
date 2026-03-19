Audit framework: PIPEDA (Personal Information Protection and Electronic Documents Act)
Source document: compliance/Source Docs/text/pipeda_sa_tool_200807_e.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 1 — Read the source document
Read compliance/Source Docs/text/pipeda_sa_tool_200807_e.md and list the applicable requirements for each of the 10 Fair Information Principles:
- Principle 1: Accountability
- Principle 2: Identifying Purposes
- Principle 3: Consent
- Principle 4: Limiting Collection
- Principle 5: Limiting Use, Disclosure, and Retention
- Principle 6: Accuracy
- Principle 7: Safeguards
- Principle 8: Openness
- Principle 9: Individual Access
- Principle 10: Challenging Compliance

For each principle, identify the specific checklist items from the OPC self-assessment tool.

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/pipeda/templates/control-assessment-record.md — the per-principle assessment template
2. compliance/audit-templates/pipeda/controls/pipeda-principles.md — the principle register
3. compliance/audit-templates/pipeda/controls/scope-and-personal-information.md — PI scope

### Step 3 — Complete the scope document
Fill compliance/audit-templates/pipeda/controls/scope-and-personal-information.md based on evidence found in business documents. Identify personal information types, purposes, systems, and data flows from Privacy-Policy.pdf, Data-Classification-and-Handling-Policy.pdf, and other relevant documents.

### Step 4 — Fill the assessment records
For each of the 10 principles, fill one control-assessment-record.md verbatim. Same sections, same labels, same order.

Also update compliance/audit-templates/pipeda/controls/pipeda-principles.md with status, owner, evidence, and notes for all 10 principles.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/pipeda_sa_tool_200807_e.md — [Principle X / Checklist item]
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

**No readiness scores:** Do not produce an overall readiness score. Use per-principle Pass/Partial/Fail results from the template instead.

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

**Output folder:** `compliance/outputs/pipeda-audit-[DATE]/`

1. `compliance/outputs/pipeda-audit-[DATE]/scope-and-personal-information.md` — completed PI scope
2. `compliance/outputs/pipeda-audit-[DATE]/pipeda-principles.md` — updated principle register
3. `compliance/outputs/pipeda-audit-[DATE]/principle-[1-10]-assessment.md` — one assessment per principle
4. `compliance/outputs/pipeda-audit-[DATE]/executive-summary.md` — overall findings summary with finding counts by result
5. `compliance/outputs/pipeda-audit-[DATE]/evidence-requests.md` — consolidated MISSING evidence list

---

## Supporting Templates (read before assessing)

- PI scope → compliance/audit-templates/pipeda/controls/scope-and-personal-information.md
- Principle register → compliance/audit-templates/pipeda/controls/pipeda-principles.md
- Assessment record → compliance/audit-templates/pipeda/templates/control-assessment-record.md
- Privacy governance policy → compliance/audit-templates/pipeda/policies/privacy-governance-policy.md
- PI management policy → compliance/audit-templates/pipeda/policies/personal-information-management-policy.md
- PI inventory → compliance/audit-templates/pipeda/templates/personal-information-inventory.md
- Access request log → compliance/audit-templates/pipeda/templates/access-request-log.md
- Complaint log → compliance/audit-templates/pipeda/templates/privacy-complaint-log.md
- Incident record → compliance/audit-templates/pipeda/templates/privacy-incident-record.md
- Exception record → compliance/audit-templates/pipeda/templates/exception-record.md
