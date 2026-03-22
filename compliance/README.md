# Compliance Audit Agents

A suite of AI-powered compliance audit agents that guide you through structured, checkpoint-driven audit preparation across 8 regulatory frameworks.

---

## How It Works

The compliance audit system has three layers:

```
Layer 1: ORCHESTRATION
  agent-prompt-instructions.md          <- Universal rules, intake questionnaire,
                                           phased workflow, checkpoints

Layer 2: FRAMEWORK PROMPTS
  Agent Prompt ISO27001.md              <- Framework-specific steps, templates,
  Agent Prompt SWIFT-CSCF.md               source docs, and output structure
  Agent Prompt PCI-DSS.md
  Agent Prompt SOC2.md
  Agent Prompt FINTRAC.md
  Agent Prompt PIPEDA.md
  Agent Prompt RPAA.md
  Agent Prompt FIPS140-2.md

Layer 3: TEMPLATES & SHARED TOOLS
  compliance/audit-templates/[framework]/   <- Per-framework registers, assessment
  compliance/audit-templates/shared/           records, policies, procedures
                                            <- Cross-framework tools (remediation
                                               tracker, evidence matrix, etc.)
```

When you activate a framework agent, it reads `agent-prompt-instructions.md` first (Step 0), then follows its own framework-specific steps. The result is a consistent experience regardless of which framework you're auditing.

---

## Available Frameworks

| Framework | Agent Prompt | Source Document | Use When |
|-----------|-------------|-----------------|----------|
| **ISO 27001:2022** | `Agent Prompt ISO27001.md` | AS/NZS ISO/IEC 27001:2023 | Information security management system certification |
| **PCI-DSS v4.0.1** | `Agent Prompt PCI-DSS.md` | PCI-DSS-v4_0_1.md | Payment card data protection |
| **SOC 2** | `Agent Prompt SOC2.md` | SOC 2.md (DC Section 200) | Service organization trust services |
| **SWIFT CSCF v2026** | `Agent Prompt SWIFT-CSCF.md` | CSCF v2026 comparison | SWIFT messaging security |
| **FINTRAC** | `Agent Prompt FINTRAC.md` | FINTRAC requirements.md | Canadian AML/ATF compliance |
| **PIPEDA** | `Agent Prompt PIPEDA.md` | OPC self-assessment tool | Canadian federal privacy |
| **RPAA** | `Agent Prompt RPAA.md` | SOR-2023-229 + R-7.36 + guidance | Canadian retail payments |
| **FIPS 140-2** | `Agent Prompt FIPS140-2.md` | NIST FIPS PUB 140-2 | Cryptographic module validation |

To audit **multiple frameworks at once**, use `Agent Prompt Multi-Framework.md`.

---

## Quick Start

### Single Framework Audit

1. Open the framework agent prompt (e.g., `Agent Prompt ISO27001.md`)
2. The agent will ask you **8 universal questions + 2-4 framework-specific questions** before starting
3. Answer all questions — the agent will not proceed until you do
4. The agent walks you through 5 phases with 3 checkpoints where it pauses for your review

### Multi-Framework Audit

1. Open `Agent Prompt Multi-Framework.md`
2. The agent will ask which frameworks to include
3. It runs each framework assessment sequentially with shared scoping
4. At the end, it produces a **Consolidated Executive Summary** covering all frameworks

---

## The Audit Experience: Phase by Phase

### Phase 0: Intake Questionnaire

The agent asks questions to understand your context before touching any documents. This is the most important phase — it prevents wasted work from wrong assumptions.

**Universal questions (asked for every framework):**

| # | Question | Why It Matters |
|---|---------|----------------|
| 1 | **Assessment type** — design only, operating effectiveness, or both? | Determines what evidence is needed and how controls are tested |
| 2 | **Audit period** — start and end dates? | Defines what operating evidence must cover |
| 3 | **Scope boundaries** — any exclusions or priority areas? | Prevents assessing out-of-scope items |
| 4 | **Prior audits** — previous results available? | Enables trend analysis and recurring finding detection |
| 5 | **Third parties** — outsourced services? Vendor reports? | Triggers vendor evidence collection workflow |
| 6 | **Known gaps** — any areas of concern? | Focuses attention where it matters most |
| 7 | **Audience** — who receives the output? | Adjusts language and detail level |
| 8 | **Cross-framework** — subject to other frameworks? | Enables cross-framework impact flagging |

**Framework-specific questions** are then asked based on the framework selected (e.g., CDE boundary for PCI-DSS, architecture type for SWIFT, report type for SOC 2).

### Phase 1: Scoping

The agent reads the source documents and business documents, then fills the scope template. It presents the scope summary and waits for your approval.

```
CHECKPOINT 1 — SCOPE APPROVAL
"Here is the assessment scope: [summary]. Please confirm before I proceed."
```

**What you should check:**
- Are all in-scope items correct?
- Are exclusions justified?
- Is the assessment type right?
- For operating effectiveness: is the audit period correct?

### Phase 2: Design Assessment

The agent extracts every requirement from the source document, maps each to evidence in your business documents, and assesses design suitability. It then presents findings before continuing.

```
CHECKPOINT 2 — DESIGN ASSESSMENT REVIEW
"Here are the findings: [summary table]. Any additional context?"
```

**What you should check:**
- Are ratings fair? (the agent is instructed to be conservative)
- Are there documents the agent didn't find?
- Should any ratings be adjusted based on information you have?

### Phase 3: Evidence Collection & Operating Effectiveness

*Only runs if you selected operating effectiveness in Phase 0.*

The agent identifies all evidence needed, applies sampling methodology (sample sizes, selection methods), and tests sampled items. This phase uses:
- `shared/evidence-collection-matrix.md` — tracking what's needed
- `shared/population-sampling-methodology.md` — how to sample

### Phase 4: Reporting

The agent produces all deliverables:
- Framework-specific assessment records
- Executive summary (leadership-ready)
- Evidence requests for missing items
- Remediation tracker entries for all findings
- Cross-framework impact notes

```
CHECKPOINT 3 — FINAL REVIEW
"Here is the executive summary. Please review before I finalize."
```

**What you should check:**
- Is the executive summary accurate?
- Are the recommendations actionable?
- Are cross-framework impacts correctly identified?

### Phase 5: Finalization

After your confirmation, the agent writes all output files, performs a completeness self-check, and provides recommended next steps.

---

## File Reference

### Agent Files (this directory)

| File | Purpose |
|------|---------|
| `agent-prompt-instructions.md` | Universal orchestrator — intake questions, rules, checkpoints, guardrails |
| `Agent Prompt [Framework].md` | Framework-specific steps, templates, source docs, outputs |
| `Agent Prompt Multi-Framework.md` | Multi-framework orchestrator for concurrent audits |
| `network-compliance-auditor.md` | Network-focused auditor agent (topology, segmentation, access paths) |
| `README.md` | This file |

### Shared Templates (`compliance/audit-templates/shared/`)

These cross-framework tools are used during and after every audit:

| Template | Purpose | When Used |
|----------|---------|-----------|
| `pre-audit-scoping-workflow.md` | Structured scoping with sign-off gates | Phase 1 |
| `evidence-collection-matrix.md` | Track all evidence across frameworks | Phase 3 |
| `population-sampling-methodology.md` | Sample size tables, selection methods | Phase 3 |
| `interview-walkthrough-templates.md` | Question banks for 8 control areas | Phase 3 |
| `vendor-evidence-management.md` | SOC reports, bridge letters, CUEC tracking | Phase 3 |
| `remediation-tracker.md` | Finding lifecycle: open to closed | Phase 4 |
| `cross-framework-control-mapping.md` | Which controls overlap across frameworks | Phase 4 |
| `readiness-scorecard.md` | Dashboard view of audit readiness | Phase 4 |
| `continuous-monitoring.md` | Between-audit compliance maintenance | Post-audit |
| `management-review.md` | Structured management review meetings | Post-audit |
| `training-tracker.md` | Compliance training tracking | Post-audit |
| `risk-acceptance-workflow.md` | Formal risk acceptance process | Post-audit |
| `compliance-change-impact-assessment.md` | Regulatory/org change impact analysis | As needed |

### Framework Templates (`compliance/audit-templates/[framework]/`)

Each framework has its own directory with:

```
[framework]/
  controls/          <- Requirement registers, scope definitions
  templates/         <- Assessment records, evidence index, executive summary
  policies/          <- Governance policies
  procedures/        <- Operational procedures
  evidence/          <- Evidence storage (you populate this)
  audits/            <- Audit outputs and internal reviews
```

### Output Location

All audit outputs go to dated folders:

```
compliance/outputs/[framework]-audit-[YYYY-MM-DD]/
  scope-and-[...].md           <- Completed scope
  [requirement-register].md    <- Updated requirement register
  [assessment-records]/        <- Individual assessment records
  executive-summary.md         <- Leadership-ready summary
  evidence-requests.md         <- Missing evidence list
  remediation-tracker.md       <- Finding-level remediation entries
```

For multi-framework audits, an additional consolidated summary is produced:

```
compliance/outputs/multi-framework-audit-[YYYY-MM-DD]/
  consolidated-executive-summary.md    <- Cross-framework overview
  [framework-1]-audit/                 <- Per-framework outputs
  [framework-2]-audit/
  ...
```

---

## Key Design Decisions

### Why the agent asks so many questions upfront
Real audits start with scoping meetings. The intake questionnaire prevents the most common audit failure: assessing the wrong scope, wrong period, or wrong assessment type. Five minutes of questions saves hours of rework.

### Why there are three checkpoints
Each checkpoint is a moment where the human's judgment is essential:
1. **Scope** — only you know your real boundaries
2. **Findings** — you may have context the documents don't show
3. **Executive summary** — this is what leadership sees

### Why cross-framework mapping exists
Organizations subject to multiple frameworks waste enormous effort collecting the same evidence multiple times. The mapping shows that your firewall rule review satisfies ISO A.8.23, PCI 1.2, SOC 2 CC6.6, and SWIFT 1.1 simultaneously.

### Why the agent can't give readiness scores
No template contains a scoring field because arbitrary scores (e.g., "85/100") misrepresent binary conformity determinations. A single critical gap makes the score meaningless. The agent uses per-requirement Pass/Partial/Fail instead.

### Why evidence is classified as Design or Operating
This is the most common source of inflated audit results. A policy document (design evidence) proves what SHOULD happen. A log file (operating evidence) proves what DID happen. The agent tracks the ratio and flags when only design evidence exists.

---

## Customization

### Adding a new framework

1. Create a directory under `compliance/audit-templates/[new-framework]/` with the standard structure
2. Add the source document to `compliance/Source Docs/`
3. Create an `Agent Prompt [New-Framework].md` following the pattern of existing prompts
4. Add framework-specific guardrails to `agent-prompt-instructions.md`
5. Add framework-specific intake questions to `agent-prompt-instructions.md`
6. Update `cross-framework-control-mapping.md` with the new framework column
7. Update `Agent Prompt Multi-Framework.md` to include the new option

### Adjusting the intake questionnaire

Edit `agent-prompt-instructions.md` Phase 0. Universal questions apply to all frameworks; framework-specific questions are grouped by framework name.

### Changing checkpoint behavior

Edit `agent-prompt-instructions.md` Phases 1-4. Each CHECKPOINT block defines exactly what the agent presents and what it waits for.
