Audit framework: AS/NZS ISO/IEC 27001:2023 (identical to ISO/IEC 27001:2022 + Amd 1:2024)
Source document: compliance/Source Docs/text/ASNZS-ISOIEC-270012023.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all five steps below in order. Do not skip any step or merge them.

### Step 1 — Read the source document
Read compliance/Source Docs/text/ASNZS-ISOIEC-270012023.md and list the applicable requirements for each of:
- Clauses 4.1, 4.2, 4.3, 4.4
- Clauses 5.1, 5.2, 5.3
- Clauses 6.1.1, 6.1.2, 6.1.3, 6.2, 6.3
- Clauses 7.1, 7.2, 7.3, 7.4, 7.5
- Clauses 8.1, 8.2, 8.3
- Clauses 9.1, 9.2.1, 9.2.2, 9.3.1, 9.3.2, 9.3.3
- Clauses 10.1, 10.2
- Annex A, Table A.1 — all 93 controls (categories A.5, A.6, A.7, A.8 only — this is ISO 27001:2022, not 2013)

### Step 2 — Read the output template
Read compliance/audit-templates/iso27001/audits/audit-report-template.md and output its raw structure verbatim — every section heading and every field label exactly as written.

### Step 3 — Fill the template
Fill the audit-report-template.md structure verbatim. Same sections, same labels, same order. Do not add sections, remove sections, or rename headings.

For Annex A, read and update compliance/audit-templates/iso27001/controls/annex-a-controls.md with findings for all 93 controls.

### Step 4 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/ASNZS-ISOIEC-270012023.md — [Clause X.X or Annex A, Table A.1, [control]]
```

### Step 5 — Cite evidence on every finding
Every finding must include either:
```
Evidence: compliance/business-documents/PDFs/[filename]
```
or:
```
Evidence: MISSING — evidence request raised
```

### Step 6 — Populate the corrective action register
After completing the audit report, populate compliance/audit-templates/iso27001/audits/corrective-action-register.md with one CA entry per Major NC and Minor NC found. Each entry must include: root cause analysis, corrective action, owner, due date, and effectiveness evidence.

---

## Mandatory Rules

**Annex A version:** Use the ISO 27001:2022 Annex A structure only — four categories, 93 controls:
- A.5 Organizational controls (37)
- A.6 People controls (8)
- A.7 Physical controls (14)
- A.8 Technological controls (34)

Do NOT use the old ISO 27001:2013 Annex A (A.5 through A.18, 14 domains). Any output using the 2013 structure is incorrect.

**No readiness scores:** Do not produce an overall readiness score (e.g. "85/100"). This is not part of ISO 27001 or any local template. Use the certification verdict from the template's executive summary instead.

**No effort estimates:** Do not produce effort estimates in days or weeks. These are not part of any local template.

**No invented structure:** Your output must match the audit-report-template.md section-for-section. If your output structure does not match the template file, rewrite it.

**No verbatim standard text:** The source document is a licensed standard. Cite clause numbers and paraphrase. Do not copy substantial blocks of standard text into deliverables.

**Status vocabulary — register:**
- `Implemented`
- `In Progress`
- `Planned`
- `Not Applicable`

**Status vocabulary — assessment:**
- `Conforming`
- `Major NC`
- `Minor NC`
- `Observation`
- `Positive Finding`

---

## Output Files

Create a dated output folder and place all deliverables inside it:

**Output folder:** `compliance/outputs/iso27001-audit-[DATE]/`

Create or update the following files:

1. `compliance/outputs/iso27001-audit-[DATE]/audit-report.md` — filled audit report
2. `compliance/outputs/iso27001-audit-[DATE]/annex-a-controls-assessed.md` — filled Annex A register
3. `compliance/outputs/iso27001-audit-[DATE]/corrective-action-register.md` — populated with all NCs from this audit
4. `compliance/outputs/iso27001-audit-[DATE]/evidence-requests.md` — consolidated list of all MISSING evidence items

---

## Supporting Templates (read before assessing each clause)

- Clause 4.3 scope → compliance/audit-templates/iso27001/templates/isms-scope.md
- Clauses 4.1–4.2 context → compliance/audit-templates/iso27001/templates/context-and-interested-parties.md
- Clauses 6.1.2–6.1.3 risk → compliance/audit-templates/iso27001/templates/risk-register.md
- Clause 6.1.3(d) SoA → compliance/audit-templates/iso27001/templates/statement-of-applicability.md
- Clause 6.2 objectives → compliance/audit-templates/iso27001/templates/information-security-objectives.md
- Clause 7.2–7.3 competence → compliance/audit-templates/iso27001/templates/competence-record.md
- Clause 7.4 communication → compliance/audit-templates/iso27001/templates/communication-plan.md
- Clause 7.5 doc control → compliance/audit-templates/iso27001/templates/documented-information-register.md
- Clause 9.1 metrics → compliance/audit-templates/iso27001/templates/performance-metrics.md
- Clause 9.2 audit plan → compliance/audit-templates/iso27001/audits/audit-plan-template.md
- Clause 9.3 management review → compliance/audit-templates/iso27001/audits/management-review-template.md
- Clause 10.2 corrective actions → compliance/audit-templates/iso27001/audits/corrective-action-register.md
