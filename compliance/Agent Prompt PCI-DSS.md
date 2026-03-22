Audit framework: PCI DSS v4.0.1
Source document: compliance/Source Docs/text/PCI-DSS-v4_0_1.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 0 — Read universal instructions and conduct intake
Read `agency-agents/compliance/agent-prompt-instructions.md` in full. This file contains:
- The **intake questionnaire** you MUST present to the user before any assessment work
- **Universal rules** for source fidelity, rating calibration, and evidence classification
- **Phased workflow** with human-in-the-loop checkpoints (you must pause at each checkpoint)
- **Framework-specific guardrails** for PCI-DSS that supplement the rules below
- **Shared templates** you must reference during and after assessment

**Do not proceed to Step 1 until you have:**
1. Asked the user ALL intake questions (universal + PCI-DSS-specific)
2. Received and recorded the user's answers
3. Completed **CHECKPOINT 1** (scope approval) and received user confirmation

### Step 1 — Read the source document
Read compliance/Source Docs/text/PCI-DSS-v4_0_1.md and list the applicable requirements for each of:
- Requirement 1: Install and Maintain Network Security Controls
- Requirement 2: Apply Secure Configurations to All System Components
- Requirement 3: Protect Stored Account Data
- Requirement 4: Protect Cardholder Data with Strong Cryptography During Transmission
- Requirement 5: Protect All Systems and Networks from Malicious Software
- Requirement 6: Develop and Maintain Secure Systems and Software
- Requirement 7: Restrict Access to System Components and Cardholder Data by Business Need to Know
- Requirement 8: Identify Users and Authenticate Access to System Components
- Requirement 9: Restrict Physical Access to Cardholder Data
- Requirement 10: Log and Monitor All Access to System Components and Cardholder Data
- Requirement 11: Test Security of Systems and Networks Regularly
- Requirement 12: Support Information Security with Organizational Policies and Programs

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/pci-dss/templates/requirement-assessment-record.md — the per-requirement assessment template
2. compliance/audit-templates/pci-dss/controls/pci-dss-requirements.md — the requirement register
3. compliance/audit-templates/pci-dss/controls/scope-and-cde.md — the CDE scope definition

### Step 3 — Complete the scope document
Fill compliance/audit-templates/pci-dss/controls/scope-and-cde.md based on evidence found in business documents. If CDE scope cannot be determined from available documents, state this explicitly and assess requirements at a policy-documentation level only.

### Step 4 — Fill the assessment records
For each of the 12 principal requirements, fill one requirement-assessment-record.md verbatim. Same sections, same labels, same order. Do not add, remove, or rename sections.

Also update compliance/audit-templates/pci-dss/controls/pci-dss-requirements.md with status, owner, evidence, and notes for all 12 requirements.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/PCI-DSS-v4_0_1.md — [Requirement X / Section heading]
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

**No readiness scores:** Do not produce an overall readiness score (e.g. "85/100"). Use Per-requirement Pass/Partial/Fail results from the template instead.

**No effort estimates:** Do not produce effort estimates in days or weeks.

**No invented structure:** Your output must match the requirement-assessment-record.md section-for-section. If your output structure does not match the template file, rewrite it.

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

**Output folder:** `compliance/outputs/pci-dss-audit-[DATE]/`

1. `compliance/outputs/pci-dss-audit-[DATE]/scope-and-cde.md` — completed CDE scope
2. `compliance/outputs/pci-dss-audit-[DATE]/pci-dss-requirements.md` — updated requirement register
3. `compliance/outputs/pci-dss-audit-[DATE]/requirement-[1-12]-assessment.md` — one assessment record per requirement
4. `compliance/outputs/pci-dss-audit-[DATE]/executive-summary.md` — overall findings summary with finding counts by result
5. `compliance/outputs/pci-dss-audit-[DATE]/evidence-requests.md` — consolidated list of all MISSING evidence items
6. `compliance/outputs/pci-dss-audit-[DATE]/remediation-tracker.md` — finding-level remediation entries with cross-framework impact

---

## Supporting Templates (read before assessing)

- CDE scope → compliance/audit-templates/pci-dss/controls/scope-and-cde.md
- Requirement register → compliance/audit-templates/pci-dss/controls/pci-dss-requirements.md
- Assessment record → compliance/audit-templates/pci-dss/templates/requirement-assessment-record.md
