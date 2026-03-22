# Multi-Framework Compliance Audit

Use this prompt when auditing **two or more frameworks concurrently**. This orchestrator handles framework selection, shared scoping, sequential assessment, and produces a consolidated executive summary across all selected frameworks.

---

## Pre-Audit Requirements

Before writing anything, complete all steps below in order.

### Step 0 — Read universal instructions
Read `agency-agents/compliance/agent-prompt-instructions.md` in full.

### Step 1 — Framework Selection

Present the framework selection menu to the user and wait for their response:

```
FRAMEWORK SELECTION

Which compliance frameworks should be included in this audit?
Select all that apply:

  [ ] 1. ISO 27001:2022 — Information security management system
  [ ] 2. PCI-DSS v4.0.1 — Payment card data protection
  [ ] 3. SOC 2 — Service organization trust services
  [ ] 4. SWIFT CSCF v2026 — SWIFT messaging security
  [ ] 5. FINTRAC — Canadian AML/ATF compliance
  [ ] 6. PIPEDA — Canadian federal privacy
  [ ] 7. RPAA — Canadian retail payments
  [ ] 8. FIPS 140-2 — Cryptographic module validation
  [ ] ALL — Select all 8 frameworks

Enter the numbers of the frameworks to include (e.g., "1, 2, 3" or "ALL"):
```

Record the user's selection. Do not proceed until a selection is made.

### Step 2 — Unified Intake Questionnaire

Ask the universal intake questions from `agent-prompt-instructions.md` Phase 0 **once** (not per framework). Then ask the framework-specific questions for **each selected framework** in sequence.

**Ask ONE question at a time.** Follow the one-at-a-time conversational intake approach defined in `agent-prompt-instructions.md`. Begin with:

```
INTAKE QUESTIONNAIRE

Since you've selected [N] frameworks, I'll ask the universal questions once,
then framework-specific questions for each selection.
I'll ask one question at a time.
```

Then ask questions 1-8 from `agent-prompt-instructions.md` one at a time, waiting for the user's response to each before presenting the next. After the 8 universal questions, ask framework-specific questions for each selected framework, also one at a time.

After all questions are answered, present the intake summary for confirmation as defined in `agent-prompt-instructions.md`, then proceed to Step 3.

### Step 3 — Unified Scoping

Complete a single unified scoping pass that covers all selected frameworks:

1. Read ALL source documents for selected frameworks
2. Read ALL scope templates for selected frameworks
3. Fill each framework's scope template
4. Identify **scope overlaps** — systems, data, or processes in scope for multiple frameworks
5. Identify **scope-unique items** — items in scope for only one framework

Present the unified scope for approval:

```
===========================================================
  CHECKPOINT 1 — UNIFIED SCOPE APPROVAL
  Intake > [Scoping] > Assessment (0/N) > Analysis > Reporting > Done
===========================================================

I have completed scoping for all [N] frameworks. Here is the unified view:

COMMON SCOPE (applies to multiple frameworks):
- [Systems/services in scope for 2+ frameworks]

PER-FRAMEWORK SCOPE:
  [Framework 1]:
  - In scope: [list]
  - Excluded: [list]
  - Assessment type: [type]

  [Framework 2]:
  - In scope: [list]
  - Excluded: [list]
  - Assessment type: [type]

  [... repeat for each]

SCOPE OVERLAPS (efficiency opportunities):
- [System X] is in scope for [Framework A, B, C] — evidence collected once
- [Process Y] is in scope for [Framework A, D] — single walkthrough covers both

Please confirm the unified scope before I proceed to assessment.
```

Do not proceed until the user confirms.

### Step 4 — Sequential Framework Assessment

Assess each selected framework in sequence. For each framework:

1. Follow the steps in its specific `Agent Prompt [Framework].md` (Steps 1-5)
2. Use the cross-framework control mapping to flag shared controls
3. When evidence collected for one framework satisfies another, note it
4. Present findings at **CHECKPOINT 2** before moving to the next framework

```
===========================================================
  CHECKPOINT 2a — [FRAMEWORK 1] ASSESSMENT COMPLETE
  Intake > Scoping > [Assessment (1/N)] > Analysis > Reporting > Done
===========================================================

[Framework 1] assessment summary:
| Requirement Area | Pass | Partial | Fail |
| ... |

Key findings: [top 3-5]

I will now proceed to [Framework 2] assessment.
Any adjustments needed before I continue?
```

Repeat CHECKPOINT 2 for each framework (2a, 2b, 2c, etc.).

### Step 5 — Cross-Framework Analysis

After completing all individual assessments:

1. Identify findings that affect multiple frameworks (using `shared/cross-framework-control-mapping.md`)
2. Consolidate duplicate findings — a single access control gap should appear once with all affected framework references
3. Identify framework-unique findings
4. Calculate consolidated remediation priorities

### Step 6 — Consolidated Executive Summary

Produce a consolidated executive summary in addition to per-framework summaries:

```
===========================================================
  CHECKPOINT 3 — CONSOLIDATED REVIEW
  Intake > Scoping > Assessment (N/N) > Analysis > [Reporting] > Done
===========================================================

I have completed all [N] framework assessments. Here is the consolidated view:

OVERALL COMPLIANCE POSTURE:
| Framework | Pass | Partial | Fail | Assessment Type |
| ... |

TOP CROSS-FRAMEWORK FINDINGS:
1. [Finding] — affects [Frameworks A, B, C]
2. [Finding] — affects [Frameworks A, D]

FRAMEWORK-SPECIFIC FINDINGS:
[Framework 1]: [N] unique findings
[Framework 2]: [N] unique findings

REMEDIATION PRIORITIES (consolidated):
1. [Highest priority — addresses findings in N frameworks]
2. ...

Please review the consolidated summary and per-framework deliverables.
```

### Step 7 — Write All Outputs

After user confirmation at CHECKPOINT 3, write all output files.

---

## Output Files

Create a dated output folder with per-framework subdirectories:

**Output folder:** `compliance/outputs/multi-framework-audit-[DATE]/`

```
multi-framework-audit-[DATE]/
  consolidated-executive-summary.md     <- Cross-framework overview
  consolidated-remediation-tracker.md   <- Unified finding tracker
  cross-framework-findings.md          <- Findings affecting 2+ frameworks

  iso27001/                            <- Per-framework outputs
    audit-report.md                       (same structure as single-
    annex-a-controls-assessed.md           framework audit)
    corrective-action-register.md
    evidence-requests.md
    executive-summary.md

  pci-dss/
    scope-and-cde.md
    pci-dss-requirements.md
    requirement-[1-12]-assessment.md
    evidence-requests.md
    executive-summary.md

  [... one subdirectory per selected framework]
```

---

## Mandatory Rules

All rules from `agent-prompt-instructions.md` apply, plus:

**Unified evidence collection:** When the same evidence satisfies multiple frameworks, collect it once. Reference it in each framework's assessment using the same file path.

**Cross-framework finding consolidation:** Do not duplicate findings. If an access control gap affects ISO 27001 A.5.15, PCI-DSS 7.1, and SOC 2 CC6.1, create one consolidated finding that references all three.

**Assessment order:** When possible, start with the broadest framework (ISO 27001 or SOC 2) to establish a baseline, then assess more specific frameworks. This maximizes evidence reuse.

**Per-framework executive summaries still required:** The consolidated summary supplements — does not replace — individual framework summaries.

**No readiness scores or effort estimates:** Same rule as single-framework audits.

---

## Efficiency Guidance

### Recommended Assessment Order

If all 8 frameworks are selected, assess in this order for maximum evidence reuse:

1. **ISO 27001** — broadest scope, establishes baseline for all security controls
2. **SOC 2** — overlaps heavily with ISO; most unique items are DC criteria
3. **PCI-DSS** — builds on access control, encryption, logging from ISO/SOC2
4. **SWIFT CSCF** — specialized network controls; leverages PCI network evidence
5. **FINTRAC** — AML-specific; limited overlap with security frameworks
6. **PIPEDA** — privacy-specific; some overlap with ISO A.5.34 and SOC 2 Privacy
7. **RPAA** — operational risk; overlaps with ISO BCP and incident management
8. **FIPS 140-2** — module-specific; mostly independent of other frameworks

### Evidence Reuse Map

The agent should maintain a running evidence reuse tracker:

| Evidence Collected | Framework Collected For | Also Satisfies |
|-------------------|------------------------|----------------|
| [evidence item] | [first framework] | [list of other frameworks + requirement IDs] |
