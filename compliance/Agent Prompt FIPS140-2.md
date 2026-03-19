Audit framework: FIPS 140-2 (Security Requirements for Cryptographic Modules)
Source document: compliance/Source Docs/text/NIST.FIPS.140-2.md
Scope: All documents in compliance/business-documents/PDFs/

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order. Do not skip any step or merge them.

### Step 1 — Read the source document
Read compliance/Source Docs/text/NIST.FIPS.140-2.md and list the applicable requirements for each of the 11 requirement areas:
1. Cryptographic Module Specification
2. Cryptographic Module Ports and Interfaces
3. Roles, Services, and Authentication
4. Finite State Model
5. Physical Security
6. Operational Environment
7. Cryptographic Key Management
8. EMI/EMC
9. Self-Tests
10. Design Assurance
11. Mitigation of Other Attacks

For each area, note the requirements at each security level (Level 1–4) where differentiation applies.

### Step 2 — Read the output templates
Read these files and output their raw structure verbatim:
1. compliance/audit-templates/FIPS140-2/controls/fips-140-2-requirements.md — the requirement register
2. compliance/audit-templates/FIPS140-2/controls/security-level-and-scope.md — module scope and security level

### Step 3 — Determine module scope
Review business documents for cryptographic module indicators. Fill compliance/audit-templates/FIPS140-2/controls/security-level-and-scope.md with:
- Named module(s) in scope (if identifiable)
- Target FIPS security level
- Module type (software/firmware/hardware/hybrid)
- Operational environment type

If the module cannot be identified from available documents, state this explicitly and assess at a policy-readiness level only. Note that FIPS 140-2 is module-specific — without a defined module, the assessment is limited to organizational readiness for validation.

### Step 4 — Fill the requirement register
For each of the 11 requirement areas, update compliance/audit-templates/FIPS140-2/controls/fips-140-2-requirements.md with status, owner, evidence, and notes based on what can be determined from the business documents.

### Step 5 — Cite the source document on every finding
Every finding must include:
```
Source: compliance/Source Docs/text/NIST.FIPS.140-2.md — [Section X / Requirement area]
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

**Module-specific standard:** FIPS 140-2 is a module validation standard, not an organizational certification. Many requirements cannot be assessed without a defined cryptographic module boundary. Where a specific module is not identified:
- Assess organizational policies that support FIPS readiness (encryption, key management, change management, access control)
- Clearly mark module-specific requirements as "Cannot be assessed — no module boundary defined"
- Do not treat policy coverage as equivalent to module-level conformity

**No readiness scores:** Do not produce an overall readiness score. Use per-area status from the register instead.

**No effort estimates:** Do not produce effort estimates in days or weeks.

**No invented structure:** Update the existing register template — do not invent a new output structure.

**Status vocabulary — register:**
- `Implemented`
- `In Progress`
- `Planned`
- `Not Applicable`

---

## Output Files

Create a dated output folder and place all deliverables inside it:

**Output folder:** `compliance/outputs/fips140-2-audit-[DATE]/`

1. `compliance/outputs/fips140-2-audit-[DATE]/security-level-and-scope.md` — completed module scope
2. `compliance/outputs/fips140-2-audit-[DATE]/fips-140-2-requirements.md` — updated requirement register
3. `compliance/outputs/fips140-2-audit-[DATE]/executive-summary.md` — overall findings summary: which areas have organizational policy support, which require module-specific evidence, and which are fully unaddressed
4. `compliance/outputs/fips140-2-audit-[DATE]/evidence-requests.md` — consolidated MISSING evidence list

---

## Supporting Templates (read before assessing)

- Security level and scope → compliance/audit-templates/FIPS140-2/controls/security-level-and-scope.md
- Requirement register → compliance/audit-templates/FIPS140-2/controls/fips-140-2-requirements.md
- Crypto module security policy → compliance/audit-templates/FIPS140-2/policies/cryptographic-module-security-policy.md
- Module spec → compliance/audit-templates/FIPS140-2/templates/module-spec-template.md
- Ports and interfaces → compliance/audit-templates/FIPS140-2/templates/ports-and-interfaces-template.md
- Roles and services → compliance/audit-templates/FIPS140-2/templates/roles-services-table.md
- Finite state model → compliance/audit-templates/FIPS140-2/templates/finite-state-model.md
- Physical security → compliance/audit-templates/FIPS140-2/templates/physical-security-template.md
- Operational environment → compliance/audit-templates/FIPS140-2/templates/operational-environment-template.md
- Key and CSP inventory → compliance/audit-templates/FIPS140-2/templates/key-and-csp-inventory.md
- Self-test log → compliance/audit-templates/FIPS140-2/templates/self-test-log.md
- Change record → compliance/audit-templates/FIPS140-2/templates/change-record.md
- Configuration management → compliance/audit-templates/FIPS140-2/procedures/configuration-management-procedure.md
- Key management → compliance/audit-templates/FIPS140-2/procedures/key-management-procedure.md
- Self-tests procedure → compliance/audit-templates/FIPS140-2/procedures/self-tests-procedure.md
