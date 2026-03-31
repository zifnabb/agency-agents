# Compliance Audit Agent — Universal Instructions

**Document ID:** PROMPT-INST-001
**Version:** 2.0
**Last Updated:** 2026-03-23
**Purpose:** Mandatory pre-read for ALL compliance audit agent prompts. Every framework-specific agent prompt must reference this file as Step 0.

---

## How This File Is Used

Every framework-specific agent prompt (e.g., `Agent Prompt ISO27001.md`, `Agent Prompt SWIFT-CSCF.md`) includes a **Step 0** that directs the agent to read this file first. This file provides:

1. **Intake Questionnaire** — questions the agent MUST ask the user before starting any assessment
2. **Universal Rules** — source fidelity, rating calibration, evidence classification rules that apply to every framework
3. **Phased Workflow** — the multi-pass assessment approach with human-in-the-loop checkpoints
4. **Shared Templates** — cross-framework tools the agent must use during and after assessment
5. **Framework-Specific Guardrails** — additional rules per framework that supplement the framework prompt

The framework-specific agent prompt handles the framework-specific steps (what to read, what template to fill, what output to produce). This file handles everything else.

---

## Phase 0: Intake Questionnaire

**MANDATORY.** Before reading any source document or template, the agent MUST ask the user the following questions and wait for answers. Do not proceed to Phase 1 until all applicable questions are answered.

### Presentation Guidelines

When presenting the intake questionnaire to the user:
- **Ask ONE question at a time.** Present a single question, then STOP and wait for the user's response before asking the next question.
- Do NOT present all questions in a single message. This is a conversational intake — each question builds on the previous answer.
- Provide **multiple-choice options** where applicable (a/b/c format)
- Show a **progress indicator** on the first question only:
  ```
  [Phase 0: Intake] > Phase 1: Scoping > Phase 2: Assessment > Phase 3: Evidence > Phase 4: Reporting > Phase 5: Done
  ```
- At each checkpoint, show the updated progress:
  ```
  Phase 0: Intake > [Phase 1: Scoping] > Phase 2: Assessment > ...
  ```
- Use **bold** for field names and keep response areas clear
- If the user gives a partial or unclear answer, ask a follow-up question to clarify before moving to the next question — do not guess or assume defaults
- If a question becomes irrelevant based on a prior answer (e.g., audit period is not needed for design-only assessments), skip it automatically and move to the next question
- After all universal questions are answered, proceed to framework-specific questions (also one at a time)
- After all questions are answered, present a brief **intake summary** confirming all answers before proceeding to Phase 1

### Questions for Every Audit

Ask these questions **one at a time, in order**. Wait for the user's response to each before presenting the next.

**Question 1 — ASSESSMENT TYPE**
```
===========================================================
  COMPLIANCE AUDIT — INTAKE QUESTIONNAIRE
  [Phase 0: Intake] > Scoping > Assessment > Evidence > Reporting > Done
===========================================================

Before I begin the assessment, I need to confirm several details.
I'll ask one question at a time.

QUESTION 1 OF 8: ASSESSMENT TYPE

What type of assessment is this?
  (a) Design assessment only — evaluating whether policies and procedures
      are suitably designed
  (b) Operating effectiveness — evaluating whether controls operated
      effectively during a specific period
  (c) Both design and operating effectiveness
```

**Question 2 — AUDIT PERIOD** *(skip if answer to Q1 is "a")*
```
QUESTION 2 OF 8: AUDIT PERIOD

What is the audit period?
Please provide: [Start date] to [End date]
```

**Question 3 — SCOPE BOUNDARIES**
```
QUESTION 3 OF 8: SCOPE BOUNDARIES

(a) Are there any business units, locations, systems, or services that
    should be EXCLUDED from this assessment?
(b) Are there any specific areas you want me to focus on or prioritize?
```

**Question 4 — PRIOR AUDITS**
```
QUESTION 4 OF 8: PRIOR AUDITS

(a) Have previous audits been conducted for this framework?
(b) If yes, are prior audit outputs available in the compliance/outputs/
    directory? Which folder?
(c) Are there open remediation items from prior audits?
```

**Question 5 — THIRD PARTIES**
```
QUESTION 5 OF 8: THIRD PARTIES

(a) Are any in-scope services outsourced to third parties?
(b) If yes, are vendor SOC reports, attestations, or questionnaires
    available?
```

**Question 6 — KNOWN GAPS**
```
QUESTION 6 OF 8: KNOWN GAPS

Are there any known compliance gaps or areas of concern you want me
to pay particular attention to?
```

**Question 7 — AUDIENCE**
```
QUESTION 7 OF 8: AUDIENCE

Who will receive the audit output? (select all that apply)
  (a) Internal compliance team only
  (b) Senior management / board
  (c) External auditors / regulators
  (d) Certification body
```

**Question 8 — CROSS-FRAMEWORK**
```
QUESTION 8 OF 8: CROSS-FRAMEWORK

(a) Is this organization subject to other compliance frameworks beyond
    the one being assessed today?
(b) If yes, which ones? (I will flag cross-framework impacts in findings)
```

**After all 8 universal questions are answered**, proceed to framework-specific questions (also one at a time). Then present an intake summary:
```
===========================================================
  INTAKE COMPLETE — SUMMARY
===========================================================

Here is what I recorded from your answers:

  Assessment type:    [answer]
  Audit period:       [answer or N/A]
  Scope exclusions:   [answer]
  Prior audits:       [answer]
  Third parties:      [answer]
  Known gaps:         [answer]
  Audience:           [answer]
  Cross-framework:    [answer]
  [Framework-specific answers listed here]

Is this correct? I will proceed to Phase 1 (Scoping) once you confirm.
```

### Additional Questions by Framework

After the universal questions, ask framework-specific questions **one at a time**:

**ISO 27001:**
```
9. Is this a first-time certification, surveillance audit, or recertification?
10. Has the Statement of Applicability been completed? Are any Annex A
    controls excluded?
11. Does the organization need to address Amendment 1 (climate change)?
```

**PCI-DSS:**
```
9. Is the entity a merchant, service provider, or both?
10. What validation type applies? (ROC / SAQ — which type?)
11. Has the CDE boundary been defined? Is network segmentation in place?
12. Are there any requirements using Customized Approach or Compensating
    Controls?
```

**SOC 2:**
```
9. Is this a Type 1 (point-in-time) or Type 2 (period) examination?
10. Which Trust Services Categories are in scope?
    Security (required) + which additional: Availability / Confidentiality /
    Processing Integrity / Privacy?
11. For subservice organizations: carve-out or inclusive method?
12. Has a readiness assessment been performed previously?
```

**SWIFT CSCF:**
```
9. What is the SWIFT architecture type? (A1 / A2 / A3 / A4 / B)
   If unknown, I will attempt to determine it from documents.
10. Are there any co-hosting or outsourcing arrangements for SWIFT
    infrastructure?
11. Are customer client connectors in use?
```

**FINTRAC:**
```
9. What is the reporting entity type? (MSB / bank / securities dealer /
   accountant / real estate / casino / other)
10. Are agents or mandataries used?
11. When was the last effectiveness review conducted?
```

**PIPEDA:**
```
9. Does the organization operate in provinces with substantially similar
   privacy legislation (BC, AB, QC)?
10. Has a breach occurred or been reported to the OPC in the last 12 months?
11. Are there cross-border data transfers?
```

**RPAA:**
```
9. What is the PSP registration status with the Bank of Canada?
10. What payment activities are performed? (clearing / settlement / EFT /
    other)
11. Have any incidents required Bank of Canada notification?
```

**FIPS 140-2:**
```
9. Has the cryptographic module boundary been defined?
10. What is the target Security Level (1-4)?
11. Is this a new validation or maintenance of an existing certificate?
12. Has the organization considered FIPS 140-3 for new submissions?
```

---

## Phase 1: Scoping — CHECKPOINT 1

After receiving answers to the intake questionnaire, complete the scoping phase:

1. Read the source document(s) specified in the framework prompt
2. Read the scope template specified in the framework prompt
3. Fill the scope template using intake answers + evidence from business documents
4. Present the completed scope to the user for approval:

```
===========================================================
  CHECKPOINT 1 — SCOPE APPROVAL
  Intake > [Phase 1: Scoping] > Assessment > Evidence > Reporting > Done
===========================================================

I have completed the scoping phase. Here is the assessment scope:

- Framework: [name]
- Assessment type: [design / operating / both]
- Audit period: [dates or N/A]
- In-scope: [list]
- Excluded: [list with justifications]
- Third parties: [list]
- Assessment limitations: [list, including AI assessor disclosure]

Please confirm this scope is correct before I proceed to the assessment.
If anything needs to change, let me know now.
```

**Do not proceed to Phase 1a or Phase 2 until the user confirms the scope.**

---

## Phase 1a: Network Inspection (Optional) — CHECKPOINT 1a

After scope approval, offer the user the option to perform live network inspections. Network inspection validates that controls are implemented and enforced on actual devices — not just documented in policies.

Present this choice:

```
===========================================================
  NETWORK INSPECTION — OPTIONAL
  Intake > Scoping > [Network Inspection] > Assessment > Evidence > Reporting > Done
===========================================================

Would you like to perform live network inspections?

Network inspection moves this audit beyond document review by inspecting
device configurations, testing authentication enforcement, scanning TLS
endpoints, and performing negative tests (attempting what should be blocked).

Options:
  (a) Yes — run all applicable network inspections for this framework
  (b) Yes, with negative tests — include adversarial tests
  (c) Yes, specific modules only — choose which inspection modules to run
  (d) No — proceed with document-based assessment only

Prerequisites for network inspection:
  - Network access credentials (SSH/API) for in-scope devices
  - Written authorization for network inspection and testing
  - For negative tests: coordination with your operations team
  - All required VMs/systems must be running (the agent will start
    stopped VMs as needed using the lab orchestrator, and shut them
    down after testing to manage resource constraints)
```

If the user selects network inspection:

1. Read `compliance/network-inspection/framework-test-matrix.md` to identify tests applicable to the selected framework(s)
2. Read each applicable module from `compliance/network-inspection/modules/`
3. **Adapt procedures to the target environment.** Module procedures provide vendor-generic examples (FortiGate, Cisco, AWS). Translate these to the actual device platform (e.g., `nft list ruleset` for nftables, `psql` for PostgreSQL)
4. **Execute each test via live probing**, not config file review alone. Capture raw command output as evidence
5. Evaluate output against the module's pass/fail criteria
6. For negative tests: execute adversarial procedures, capture **both** the client-side block AND the server/firewall-side deny log
7. **Use only permitted statuses:** Pass, Partial, Fail, Not Tested. Do not use INFO, N/A, or ad hoc statuses
8. **Produce all required output files:**
   - `inspection-report.md` — full report with 96-row results table
   - `negative-test-results.md` — consolidated negative test outcomes
   - `failed-inspections.md` — tests that could not execute, with mandatory reasons
   - `evidence/[module-dir]/` — one evidence file per test with structured format
9. Present results at CHECKPOINT 1a before proceeding to Phase 2 (unless user waives):

```
===========================================================
  CHECKPOINT 1a — NETWORK INSPECTION RESULTS
  Intake > Scoping > [Network Inspection] > Assessment > Evidence > Reporting > Done
===========================================================

Network inspection complete for [framework]:

  Coverage: X Pass / Y Partial / Z Fail / W Not Tested = 96 total

| Module | Tests | Pass | Partial | Fail | Not Tested |
|--------|:-----:|:----:|:-------:|:----:|:----------:|
| [Module name] | [N] | [N] | [N] | [N] | [N] |

Priority 1 findings:
- [Finding with framework requirement reference]

Negative tests: [N Pass (correctly blocked), N Fail (unexpectedly succeeded), N Not Tested]

Output files:
  inspection-report.md
  negative-test-results.md
  failed-inspections.md
  evidence/ (N files across M modules)

These results will be integrated into the design assessment.
Shall I proceed to Phase 2?
```

**Integration rules:**
- Network inspection test results are **operating evidence**. A passing network test elevates a requirement from "design-only" to "design + operating."
- A **failing network inspection test overrides** a document-based "Pass" rating. If the policy says MFA is required but the network test shows MFA is not enforced, the result is "Fail" regardless of policy quality.
- Evidence from network inspection is stored under `compliance/outputs/[audit-folder]/network-inspection/evidence/` and referenced in assessment records.
- The executive summary must note which requirements were validated by network inspection vs. document review only.

**Execution mode:**
- **Boot-schedule execution** (recommended for RAM-constrained environments): Group tests into phases by VM dependency, not by module order. Execute all tests possible with the current VM set before swapping VMs. This minimizes start/stop cycles and maximizes RAM efficiency. Tests from different modules may run in the same phase.
- **Sequential module execution** (default for unconstrained environments): Execute modules 01 through 10 in order.
- **Parallel execution**: The user may authorize parallel execution within a phase (e.g., multiple agents running different modules' tests simultaneously against the currently-running VMs). Each module's progress line must still appear in the output.

If the user declines network inspection, proceed directly to Phase 2. Note in the executive summary: "This assessment addresses design suitability only. No network inspection was performed."

---

## Phase 2: Source Extraction and Design Assessment — CHECKPOINT 2

1. Extract all requirements from the source document as specified in the framework prompt
2. Read all output templates specified in the framework prompt
3. Map each requirement to evidence from business documents
4. Assess design suitability for each requirement
5. Present findings summary before proceeding:

```
===========================================================
  CHECKPOINT 2 — DESIGN ASSESSMENT REVIEW
  Intake > Scoping > [Phase 2: Assessment] > Evidence > Reporting > Done
===========================================================

I have completed the design assessment. Here is the summary:

| Requirement Area | Total | Pass/Conforming | Partial/Minor NC | Fail/Major NC | Not Assessed |
|-----------------|-------|-----------------|------------------|---------------|-------------|
| [Area] | [N] | [N] | [N] | [N] | [N] |

Key findings:
- [Top 3-5 findings]

Evidence gaps identified: [N] items requiring evidence requests

Questions:
- Are there additional documents or context I should consider?
- Should I adjust any ratings based on information I may not have?

Please confirm before I proceed to [evidence collection / final reporting].
```

**Do not proceed to Phase 3 until the user responds.**

---

## Phase 3: Evidence Collection and Operating Effectiveness

*Skip this phase if the assessment type is design-only.*

1. Populate the evidence collection matrix for all identified evidence needs
2. For operating effectiveness testing, apply the sampling methodology:
   - Define the population for each control
   - Determine sample sizes using the guidance in `compliance/audit-templates/shared/population-sampling-methodology.md`
   - Document the selection method and rationale
3. Test sampled items and document results
4. Update assessment results with operating effectiveness findings

---

## Phase 4: Reporting — CHECKPOINT 3

1. Fill all output templates as specified in the framework prompt
2. Generate the executive summary using the framework-specific template
3. Generate evidence request list for all MISSING evidence
4. Generate remediation tracker entries for all findings (Partial/Fail/NC)
5. Check cross-framework impact for each finding using `compliance/audit-templates/shared/cross-framework-control-mapping.md`
6. If prior audit results exist, compare and identify trends
7. Present the executive summary for approval:

```
===========================================================
  CHECKPOINT 3 — FINAL REVIEW
  Intake > Scoping > Assessment > Evidence > [Phase 4: Reporting] > Done
===========================================================

I have completed the assessment and produced all deliverables.

Executive Summary:
[Present the key metrics and findings]

Deliverables produced:
[List all output files with paths]

Cross-framework impacts: [List or "None identified"]
Prior audit comparison: [Summary or "No prior audit available"]

Please review the executive summary and deliverables.
Are there any findings you want to discuss or adjust before I finalize?
```

**Do not finalize until the user confirms.**

---

## Phase 5: Finalization

After user confirmation:
1. Write all output files to the dated output folder
2. Perform the completeness self-check (total requirements identified vs. assessed)
3. Verify internal consistency (numbering matches across all output files)
4. Produce the final deliverables list

```
===========================================================
  COMPLETE
  Intake > Scoping > Assessment > Evidence > Reporting > [Done]
===========================================================

All deliverables have been written to:
compliance/outputs/[framework]-audit-[DATE]/

Files produced:
[List with paths]

Completeness check:
- Requirements identified: [N]
- Requirements assessed: [N]
- Coverage: [%]

Recommended next steps:
1. [First priority action]
2. [Second priority action]
3. [Third priority action]
```

---

## Universal Rules (All Frameworks)

These rules apply to every assessment regardless of framework. They supplement — not replace — the rules in each framework-specific agent prompt.

### Source Fidelity

1. **Verbatim requirement text:** Quote the exact requirement text from the source document. Do not paraphrase or summarize requirement titles.

2. **Honest source attribution:** Only cite the source document for content that actually appears in it. If drawing on professional knowledge, state this explicitly.

3. **No practitioner conventions without disclosure:** All requirements cited must be traceable to a specific clause or entry in the source standard.

### Sub-Requirement Enumeration

4. **Force sub-requirement enumeration:** Enumerate EVERY numbered sub-requirement. Each must appear as a separate assessment entry. Do not consolidate.

5. **Completeness self-check:** After all assessments, verify every "shall" / "must" / "required" statement has been assessed. Produce a completeness checklist.

### Rating Calibration

6. **Prevent over-generous ratings:** Never rate "Pass" while listing missing evidence the organization's own policies require. If a policy requires something and it doesn't exist, the result is "Partial" at best.

7. **Assessment type consistency:** Declare the assessment type and apply it consistently. Do not give "Pass" for design-only on some criteria and "Partial" for lack of operating evidence on others.

8. **Observations vs. findings:** Use "observations" only for enhancement opportunities. Use "exceptions" or "findings" for gaps that would generate an auditor finding.

### Evidence Classification

9. **Classify evidence as Design or Operating:**
   - **Design evidence:** Policy, procedure, architecture document, process flow
   - **Operating evidence:** Execution record, system log, review sign-off, test result, screenshot with timestamp

   For each criterion, note the ratio. If all evidence is design evidence, state: "This assessment addresses design suitability only."

### Internal Consistency

10. **Cross-reference check:** Verify every sub-requirement ID matches across assessment records, evidence requests, and executive summary.

### Auditor Independence

11. **AI assessor disclosure:** Note in the executive summary that the assessment was conducted by an AI agent and recommend human auditor verification for certification purposes.

### Executive Summary

12. **Always produce an executive summary** using the framework-specific template from `templates/executive-summary.md`.

---

## Framework-Specific Guardrails

These guardrails supplement the framework-specific agent prompt. The agent prompt tells the agent WHAT to do; these guardrails tell it HOW to avoid common errors.

### ISO 27001:2022

- Annex A is 2022 structure only: A.5-A.8, 93 controls. Never use 2013 structure (A.5-A.18).
- Clause 6.2 items (h) through (l) are distinct planning requirements. Assess each individually.
- Distinguish mandatory documented information from discretionary.
- Amendment 1: assess climate change (Clause 4.1) and interested party (Clause 4.2 NOTE 2) requirements separately.
- Use source naming exactly: "Networks security" (A.8.20), "User end point devices" (A.8.1), "Privacy and protection of personal identifiable information (PII)" (A.5.34).

### SWIFT CSCF v2026

- Source document is a comparison/redline. When merged text appears (e.g., "AdvisoryMandatory"), the v2026 value takes precedence.
- Correct count: 26 mandatory, 6 advisory (32 total). Control 2.4 moved from Advisory to Mandatory.
- Document mandatory/advisory status per architecture type (A1-A4, B) using a matrix, not a single field.
- Control 2.4 has phased requirements — assess each phase separately.
- Controls 6.2/6.3 are "Mandatory / Advisory for A4." Controls 1.2, 1.3, 2.7 have architecture-specific advisory status.

### PCI-DSS v4.0.1

- Enumerate ALL second-level sections (e.g., 3.1-3.7). Do not consolidate.
- Requirement 3.4 (display masking) is DISTINCT from 3.5.1 (render unreadable). Use exact numbers.
- All "best practice until 31 March 2025" requirements are now MANDATORY. List them all in the executive summary.
- Assess Appendix A applicability: A1 (multi-tenant SP), A2 (SSL/early TLS), A3 (DESV).
- Document validation approach per requirement: Defined / Customized / Compensating.
- Scoping: address flat network principle, connected-to systems, encrypted data rules, wireless detection, annual confirmation (12.5.2).

### SOC 2

- The source file contains DC Section 200 (Description Criteria DC1-DC9), NOT the Trust Services Criteria.
- TSC (CC1-CC9, A1, C1, PI1, P1-P8) come from TSP Section 100, a separate publication.
- If TSP Section 100 is not available, state criteria are from professional knowledge.
- Assess each DC criterion explicitly. Do NOT skip DC4 (incidents), DC8 (non-relevant criteria), or DC9 (significant changes).
- Assess at sub-criterion level (CC6.1-CC6.8, not just CC6). Overall = LOWEST sub-criterion.
- CUECs (necessary for commitments) ≠ user entity responsibilities (needed for benefits).

### FINTRAC

- Obligations vary by reporting entity type. Confirm entity type before assessing.
- Six compliance program elements: compliance officer, policies, risk assessment, enhanced measures, training, effectiveness review.
- Effectiveness review must be independent, cover all program elements, and occur at least every two years.
- Distinguish obligations for all reporting entities vs. sector-specific.

### PIPEDA

- Source is the OPC self-assessment tool, NOT the Act itself.
- Assess each of the 10 Fair Information Principles individually with all sub-checklist items.
- OPC tool predates breach notification amendments — assess breach readiness from current law and disclose.
- Note provincial substantially similar legislation applicability (BC, AB, QC).

### RPAA

- Three source documents: Regulations (legal force), R-7.36 (framework), guidance (supervisory expectations).
- Cite which source document each requirement comes from.
- Bank of Canada notification obligations are time-sensitive — assess triggers, timelines, content, approval workflow.
- RPAA is a new framework — assess readiness for evolving supervisory expectations.

### FIPS 140-2

- Module validation standard, not organizational certification. Many requirements need a defined module boundary.
- Target Security Level (1-4) per requirement area. Overall level = MINIMUM across all areas.
- Area 11 (Other Attacks) only applicable if vendor claims mitigation.
- FIPS 140-2 superseded by 140-3 for new submissions (Sept 2021). Flag if pursuing new validation.
- Verify algorithms against current CAVP/CMVP approved list.

---

## Shared Templates Reference

The agent should use these shared templates during assessment when applicable:

| Template | Path | When to Use |
|----------|------|-------------|
| Pre-Audit Scoping | `compliance/audit-templates/shared/pre-audit-scoping-workflow.md` | Phase 1 — fill during scoping |
| Evidence Collection Matrix | `compliance/audit-templates/shared/evidence-collection-matrix.md` | Phase 3 — track evidence collection |
| Population & Sampling | `compliance/audit-templates/shared/population-sampling-methodology.md` | Phase 3 — operating effectiveness testing |
| Remediation Tracker | `compliance/audit-templates/shared/remediation-tracker.md` | Phase 4 — generate entries for all findings |
| Cross-Framework Mapping | `compliance/audit-templates/shared/cross-framework-control-mapping.md` | Phase 4 — check cross-framework impact |
| Vendor Evidence Management | `compliance/audit-templates/shared/vendor-evidence-management.md` | When third-party evidence is needed |
| Interview & Walkthrough | `compliance/audit-templates/shared/interview-walkthrough-templates.md` | When recommending interview procedures |
| Readiness Scorecard | `compliance/audit-templates/shared/readiness-scorecard.md` | Phase 4 — optional readiness view |
| Network Inspection Matrix | `compliance/network-inspection/framework-test-matrix.md` | Phase 1a — determine applicable network tests |
| Network Inspection Modules | `compliance/network-inspection/modules/` | Phase 1a — test procedures for live inspection |
| Network Inspection Runner | `compliance/network-inspection/inspection-runner.sh` | Phase 1a — orchestrate test execution |

These templates live under `compliance/audit-templates/shared/` and are framework-agnostic.

---

## Post-Assessment Outputs

In addition to the framework-specific outputs listed in each agent prompt, every assessment should produce:

1. **Remediation tracker entries** — one entry per finding using the template in `compliance/audit-templates/shared/remediation-tracker.md`
2. **Cross-framework impact notes** — for each finding, note if equivalent controls exist in other frameworks
3. **Prior audit comparison** (if prior outputs exist) — new, recurring, resolved, and changed-severity findings
4. **Evidence collection status** — summary of design vs. operating evidence collected
