Audit framework: SOC 2 (AICPA Trust Services Criteria)
Source document: compliance/Source Docs/text/SOC 2.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 1 — Read the source document
Read compliance/Source Docs/text/SOC 2.md and list the applicable criteria for each of:
- CC1 Control Environment (governance, integrity, oversight)
- CC2 Communication and Information
- CC3 Risk Assessment
- CC4 Monitoring Activities
- CC5 Control Activities (policies, technology, deployment)
- CC6 Logical and Physical Access Controls
- CC7 System Operations (change detection, incident, recovery)
- CC8 Change Management
- CC9 Risk Mitigation (vendor, business disruption)
- Additional criteria for categories selected: Availability (A1), Confidentiality (C1), Processing Integrity (PI1), Privacy (P1–P8)

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/soc2/templates/control-assessment-record.md — the per-criterion assessment template
2. compliance/audit-templates/soc2/controls/tsc-control-register.md — the TSC control register
3. compliance/audit-templates/soc2/controls/scope-and-system-description.md — system scope
4. compliance/audit-templates/soc2/controls/trust-services-scope.md — category selection and CUECs

### Step 3 — Complete the scope documents
Fill both scope files based on evidence found in business documents:
- compliance/audit-templates/soc2/controls/scope-and-system-description.md
- compliance/audit-templates/soc2/controls/trust-services-scope.md

If the system description cannot be fully determined, state this explicitly.

### Step 4 — Fill the assessment records
For each CC area (CC1–CC9) and each selected additional category, fill one control-assessment-record.md verbatim. Same sections, same labels, same order.

Also update compliance/audit-templates/soc2/controls/tsc-control-register.md with status, owner, evidence, and notes for all criteria.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/SOC 2.md — [CC area / criterion / section heading]
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

**No readiness scores:** Do not produce an overall readiness score. Use per-criterion Pass/Partial/Fail results from the template instead.

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

**Output folder:** `compliance/outputs/soc2-audit-[DATE]/`

1. `compliance/outputs/soc2-audit-[DATE]/scope-and-system-description.md` — completed system scope
2. `compliance/outputs/soc2-audit-[DATE]/trust-services-scope.md` — category selection and CUECs
3. `compliance/outputs/soc2-audit-[DATE]/tsc-control-register.md` — updated control register
4. `compliance/outputs/soc2-audit-[DATE]/cc[1-9]-assessment.md` — one assessment per CC area
5. `compliance/outputs/soc2-audit-[DATE]/executive-summary.md` — overall findings summary with finding counts by result
6. `compliance/outputs/soc2-audit-[DATE]/evidence-requests.md` — consolidated MISSING evidence list

---

## Supporting Templates (read before assessing)

- System description → compliance/audit-templates/soc2/controls/scope-and-system-description.md
- Trust services scope → compliance/audit-templates/soc2/controls/trust-services-scope.md
- Control register → compliance/audit-templates/soc2/controls/tsc-control-register.md
- Assessment record → compliance/audit-templates/soc2/templates/control-assessment-record.md
- Readiness review → compliance/audit-templates/soc2/templates/readiness-review-report.md
- Findings log → compliance/audit-templates/soc2/templates/findings-log.md
- Evidence index → compliance/audit-templates/soc2/templates/evidence-index.md
- Exception record → compliance/audit-templates/soc2/templates/exception-record.md
