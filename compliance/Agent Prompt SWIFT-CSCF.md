Audit framework: SWIFT Customer Security Controls Framework (CSCF) v2026
Source document: compliance/Source Docs/text/CSCF_v2026_20250701_compared_to_v2025.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 1 — Read the source document
Read compliance/Source Docs/text/CSCF_v2026_20250701_compared_to_v2025.md and list the applicable controls organized by:
- Objective 1: Restrict Internet Access and Protect Critical Systems from General IT Environment
- Objective 2: Reduce Attack Surface and Vulnerabilities
- Objective 3: Physically Secure the Environment
- Objective 4: Prevent Compromise of Credentials
- Objective 5: Manage Identities and Segregate Privileges
- Objective 6: Detect Anomalous Activity to Systems or Transaction Records
- Objective 7: Plan for Incident Response and Information Sharing

For each control, note whether it is Mandatory or Advisory and which architecture types it applies to (A1/A2/A3/A4/B).

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/swift-cscf/templates/control-assessment-record.md — the per-control assessment template
2. compliance/audit-templates/swift-cscf/controls/cscf-controls.md — the CSCF control register
3. compliance/audit-templates/swift-cscf/controls/architecture-types.md — architecture type selection

### Step 3 — Determine architecture type
Review business documents for SWIFT environment indicators. Fill compliance/audit-templates/swift-cscf/controls/architecture-types.md with the selected architecture type(s) or state that architecture type cannot be determined from available documents.

### Step 4 — Fill the assessment records
For each CSCF control, fill one control-assessment-record.md verbatim. Same sections, same labels, same order. Include the control type (Mandatory/Advisory) and applicable architecture type.

Also update compliance/audit-templates/swift-cscf/controls/cscf-controls.md with status, owner, evidence, and notes.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/CSCF_v2026_20250701_compared_to_v2025.md — [Control X.X / Section heading]
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

**Architecture-dependent controls:** Do not assess controls that are marked Not Applicable to the selected architecture type. Mark them `Not Applicable` in the register with a justification referencing the architecture-types.md selection.

**Mandatory vs Advisory:** Clearly distinguish Mandatory controls (required for attestation) from Advisory controls (recommended). All Mandatory controls must be assessed. Advisory controls should be assessed but may be marked as Not Applicable with justification.

**No readiness scores:** Do not produce an overall readiness score. Use per-control Pass/Partial/Fail results from the template instead.

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

**Output folder:** `compliance/outputs/swift-cscf-audit-[DATE]/`

1. `compliance/outputs/swift-cscf-audit-[DATE]/architecture-types.md` — completed architecture selection
2. `compliance/outputs/swift-cscf-audit-[DATE]/cscf-controls.md` — updated control register
3. `compliance/outputs/swift-cscf-audit-[DATE]/control-assessments/` — one assessment record per control
4. `compliance/outputs/swift-cscf-audit-[DATE]/executive-summary.md` — overall findings summary with counts by Mandatory/Advisory and Pass/Partial/Fail
5. `compliance/outputs/swift-cscf-audit-[DATE]/evidence-requests.md` — consolidated MISSING evidence list

---

## Supporting Templates (read before assessing)

- Architecture types → compliance/audit-templates/swift-cscf/controls/architecture-types.md
- Control register → compliance/audit-templates/swift-cscf/controls/cscf-controls.md
- Assessment record → compliance/audit-templates/swift-cscf/templates/control-assessment-record.md
- Exception record → compliance/audit-templates/swift-cscf/templates/exception-record.md
- CSCF compliance policy → compliance/audit-templates/swift-cscf/policies/cscf-compliance-policy.md
