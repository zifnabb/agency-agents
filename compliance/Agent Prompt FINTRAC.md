Audit framework: FINTRAC Compliance Program Requirements
Source document: compliance/Source Docs/text/FINTRAC requirements.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 0 — Read universal instructions and conduct intake
Read `agency-agents/compliance/agent-prompt-instructions.md` in full. This file contains:
- The **intake questionnaire** you MUST present to the user before any assessment work
- **Universal rules** for source fidelity, rating calibration, and evidence classification
- **Phased workflow** with human-in-the-loop checkpoints (you must pause at each checkpoint)
- **Framework-specific guardrails** for FINTRAC that supplement the rules below
- **Shared templates** you must reference during and after assessment

**Do not proceed to Step 1 until you have:**
1. Asked the user ALL intake questions (universal + FINTRAC-specific)
2. Received and recorded the user's answers
3. Completed **CHECKPOINT 1** (scope approval) and received user confirmation

### Step 1 — Read the source document
Read compliance/Source Docs/text/FINTRAC requirements.md and list the applicable requirements for each of:

**A. Compliance Program (Required Elements):**
- A1: Appoint a Compliance Officer
- A2: Written Compliance Policies and Procedures
- A3: Risk Assessment (ML/TF and Related Risk Factors)
- A4: Enhanced Measures for High-Risk Areas
- A5: Ongoing Compliance Training Program
- A6: Two-Year Effectiveness Review

**B. Know Your Client (KYC) and Related Obligations:**
- Client identification and verification (individuals and entities)
- Beneficial ownership determination
- Third-party determination
- Politically Exposed Persons (PEP) and Heads of International Organizations (HIO) screening
- Ongoing monitoring

**C. Transaction Reporting:**
- Suspicious Transaction Reports (STR)
- Large Cash Transaction Reports (LCTR)
- Electronic Funds Transfer Reports (EFTR)
- Terrorist Property Reports (TPR)

**D. Recordkeeping:**
- Record creation, retention, and disposal requirements

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/fintrac/templates/control-assessment-record.md — the per-requirement assessment template
2. compliance/audit-templates/fintrac/controls/fintrac-requirements.md — the requirements register
3. compliance/audit-templates/fintrac/controls/scope-and-entity-profile.md — entity and scope profile

### Step 3 — Determine applicability
Review business documents for indicators of reporting entity status (MSB, bank, securities dealer, etc.). Fill compliance/audit-templates/fintrac/controls/scope-and-entity-profile.md. If reporting entity type cannot be determined, state this and note that FINTRAC applicability must be confirmed before this assessment can be considered authoritative.

### Step 4 — Fill the assessment records
For each requirement area (A1–A6 at minimum, plus applicable KYC/reporting/recordkeeping obligations), fill one control-assessment-record.md verbatim. Same sections, same labels, same order.

Also update compliance/audit-templates/fintrac/controls/fintrac-requirements.md with status, owner, evidence, and notes.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/FINTRAC requirements.md — [Requirement area / Section heading]
```

### Step 6 — CHECKPOINT 2: Present assessment findings
Before writing final output files, present the assessment summary to the user following the CHECKPOINT 2 format in `agent-prompt-instructions.md`. Wait for user confirmation before proceeding.

### Step 7 — Generate shared deliverables
After user confirmation at CHECKPOINT 2:
1. Generate remediation tracker entries for all Partial/Fail findings using `compliance/audit-templates/shared/remediation-tracker.md`
2. Check `compliance/audit-templates/shared/cross-framework-control-mapping.md` for cross-framework impact on each finding
3. If prior audit outputs exist in `compliance/outputs/`, compare findings and note trends
4. Present the executive summary for final approval at **CHECKPOINT 3**
5. Write all output files only after final user confirmation

### Step 8 — Cite evidence on every finding
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

**Applicability first:** FINTRAC obligations depend on reporting entity type. If applicability cannot be confirmed, all findings must be qualified with: "Subject to confirmation of reporting entity status."

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

**Output folder:** `compliance/outputs/fintrac-audit-[DATE]/`

1. `compliance/outputs/fintrac-audit-[DATE]/scope-and-entity-profile.md` — completed entity profile
2. `compliance/outputs/fintrac-audit-[DATE]/fintrac-requirements.md` — updated requirements register
3. `compliance/outputs/fintrac-audit-[DATE]/requirement-assessments/` — one assessment per requirement area
4. `compliance/outputs/fintrac-audit-[DATE]/executive-summary.md` — overall findings summary with finding counts by result
5. `compliance/outputs/fintrac-audit-[DATE]/evidence-requests.md` — consolidated MISSING evidence list
6. `compliance/outputs/fintrac-audit-[DATE]/remediation-tracker.md` — finding-level remediation entries with cross-framework impact

---

## Supporting Templates (read before assessing)

- Entity profile → compliance/audit-templates/fintrac/controls/scope-and-entity-profile.md
- Requirements register → compliance/audit-templates/fintrac/controls/fintrac-requirements.md
- Assessment record → compliance/audit-templates/fintrac/templates/control-assessment-record.md
- AML/ATF policy → compliance/audit-templates/fintrac/policies/aml-atf-compliance-policy.md
- Risk assessment → compliance/audit-templates/fintrac/templates/risk-assessment.md
- Training plan → compliance/audit-templates/fintrac/templates/training-plan.md
- Effectiveness review → compliance/audit-templates/fintrac/templates/effectiveness-review-report.md
- STR case file → compliance/audit-templates/fintrac/templates/str-case-file.md
- Exception record → compliance/audit-templates/fintrac/templates/exception-record.md
