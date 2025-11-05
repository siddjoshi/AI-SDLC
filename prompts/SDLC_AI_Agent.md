# AI Agent Prompt Playbook for the AI-SDLC Workspace

This playbook provides copy-paste-ready prompts so that specialised AI agents (standing in for the real-life personas who own each stage of the SDLC) can generate the required artefacts inside this repository. The prompts reference the current workspace structure:

- SDLC templates live under the ` templates/` directory (note the leading space in the folder name).
- Legacy drafts reside under `templates-old/` for historical reference.
- The repository README catalogues mandatory vs. optional artefacts per phase.

## Execution Roadmap (Phased & Parallel Activities)

| Order | SDLC Phase | Primary Persona (Agent Role) | Key Outputs (referenced templates) | Depends On | Parallelisation Notes |
|-------|------------|-------------------------------|-------------------------------------|------------|-----------------------|
| 1 | Inception / Pre-Project | Business Strategist, Portfolio Manager | Business Case, Vision & Goals, Stakeholder Register, RACI, Comms Plan | Opportunity / idea intake | RACI & Comms Plan can run after Stakeholder Register is drafted. |
| 2 | Requirements | Product Manager, Business Analyst, Systems Analyst | ` templates/BRD.md`, ` templates/PRD.md`, ` templates/SRS.md`, NFR Spec, ` templates/RTM.md`, ` templates/EPIC.md`, ` templates/Feature.md`, ` templates/Story.md` | Approved vision & stakeholder alignment | Once BRD baseline is complete, PRD, SRS/NFR, and backlog slicing (epics/features/stories) can proceed in parallel with tight traceability updates. |
| 3 | Design | Solution Architect, Security Architect, Data Architect | ` templates/HLD.md`, ` templates/LLD.md`, API/ICD specs, Threat Model, Data Model | Requirements artefacts, RTM draft | HLD and Threat Model start in parallel; LLD and API specs begin after HLD baseline. |
| 4 | Development Enablement | Engineering Lead, DevOps Lead, Security Engineer | Coding standards, CI/CD spec, SBOM strategy, task breakdown via ` templates/Task.md` | Signed-off design, prioritised backlog | Coding standards & CI/CD blueprint in parallel; task decomposition follows when iteration scope is locked. |
| 5 | Testing & QA | QA/Test Lead, Performance Engineer, Security QA | ` templates/TestPlan.md`, test suites, test data plan, defect workflow | Requirements, design, Dev enablement | Functional, performance, and security test preparations can happen concurrently using shared Test Plan. |
| 6 | Release & Deployment | Release Manager, Change Manager, Support Lead | Deployment Runbook, ` templates/RollbackPlan.md`, ` templates/ReleaseNotes.md`, Go/No-Go checklist | Completed testing, signed-off results | Release Notes drafting can start once testing enters execution; Runbook & Rollback updated alongside final CI/CD design. |
| 7 | Operations & Continuous Improvement | SRE/Operations Lead, Service Owner, Agile Coach | Incident Playbooks, RCA templates, Retrospective report, Analytics dashboards | Production deployment complete | RCA readiness and retro planning can be prepared while release is in flight; post-release analytics depends on telemetry hooks from earlier stages. |

> **Usage Tip:** Execute the prompts phase-by-phase. Only start prompts from a later phase when the dependencies in the table are satisfied or risk accepted. When the table notes an activity as parallelisable, orchestrate agents to collaborate but require them to update the ` templates/RTM.md` for traceability before they mark their artefact complete.

---

## Phase 1 — Inception / Pre-Project

### Prompt 1.1 — Business Strategist: Business Case, Vision & Goals
```
You are the Business Strategist for the AI-SDLC programme. Create the inception-level artefacts that justify and frame the initiative.

1. Review the repository README to capture the mandatory inception artefacts and understand downstream dependencies.
2. Summarise the opportunity, target customers, business objectives, high-level KPIs, and key risks in a Business Case document.
3. Derive a Vision & Goals statement that is traceable to the Business Case and will feed into ` templates/BRD.md` and ` templates/PRD.md` later.
4. Produce measurable success metrics (baseline + target) that can map into the KPI table in ` templates/BRD.md`.
5. Document open questions, assumptions, and approval stakeholders.

Deliverables: Markdown documents under `docs/inception/` (create if missing) for Business Case and Vision & Goals, plus a summary bullet list of dependencies that future phases must monitor.
Ensure every section is explicit about how subsequent requirements and design artefacts will reference the outputs.
```

### Prompt 1.2 — Portfolio Manager: Stakeholder Register, RACI & Comms Plan
```
You are acting as the Portfolio Manager. Build the stakeholder management foundation for this initiative.

1. Read the Business Case and Vision & Goals artefacts produced in Phase 1 (Inception).
2. Create a Stakeholder Register capturing personas, roles, interests, influence, communication preferences, and decision rights. Store it in `docs/inception/stakeholder-register.md`.
3. From that register, derive a RACI matrix (Responsible, Accountable, Consulted, Informed) for the core SDLC artefacts listed in README. Highlight any gaps or overloaded roles.
4. Draft a lightweight communication plan (cadence, channels, artefacts shared, escalation path) aligned to the RACI outcomes.
5. Provide traceability notes indicating how each stakeholder ties into the approvals tables across ` templates/BRD.md`, ` templates/HLD.md`, and ` templates/TestPlan.md`.

Deliverables: Stakeholder Register, RACI Matrix, Communication Plan under `docs/inception/`. Clearly flag which personas must own upcoming prompts in later phases.
```

---

## Phase 2 — Requirements

### Prompt 2.1 — Product Manager: Draft BRD & PRD
```
Persona: Product Manager.
Goal: Produce baseline Business Requirements (BRD) and Product Requirements (PRD) artefacts using the workspace templates.

Steps:
1. Consume Phase 1 artefacts (Business Case, Vision & Goals, Stakeholder Register, RACI) and note mandatory compliance, KPIs, and executive considerations.
2. Populate ` templates/BRD.md` with project-specific content, ensuring every section (objectives, scope, business processes, benefits, costs, risks) ties back to measurable KPIs and the stakeholder matrix. Save the filled document to `docs/requirements/BRD.md`.
3. Translate the BRD outcomes into a product-facing view by filling ` templates/PRD.md`; emphasise personas, journey maps, feature catalogue, and acceptance criteria. Save to `docs/requirements/PRD.md`.
4. Maintain traceability by logging requirement IDs that will flow into the RTM, Feature, Story, and Task templates. Update the RACI ownership if new stakeholders emerge.
5. Summarise open risks, decisions, and follow-ups in both documents to inform architects and analysts downstream.

Deliverables: Completed BRD and PRD in `docs/requirements/`, plus a change log noting version 0.1 → 1.0 transition triggers.
```

### Prompt 2.2 — Systems Analyst: Produce SRS, NFR Catalogue & RTM Seed
```
Persona: Systems Analyst.
Goal: Translate business/product requirements into system-level specifications and traceability foundations.

Steps:
1. Review the approved BRD and PRD, along with Vision & Goals.
2. Populate ` templates/SRS.md`, ensuring each functional requirement references its originating BRD/PRD identifier and future HLD/LLD linkage.
3. Create an explicit Non-Functional Requirements catalogue (use ` templates/PRD.md` and SRS Section 6 as inputs). If a dedicated NFR document is required, locate or create `docs/requirements/NFR.md` following the structure suggested in README and ` templates/PRD.md` Section 6.
4. Seed the ` templates/RTM.md` template by building out requirement IDs, descriptions, priority, and initial design/test placeholders. Save as `docs/requirements/RTM.md` and note coverage gaps.
5. Ensure epics, features, stories, and tasks will inherit the IDs by outlining the mapping strategy in the RTM comments.

Deliverables: SRS, NFR Catalogue, RTM (seeded) under `docs/requirements/`. Document assumptions that architects must validate in Phase 3.
```

### Prompt 2.3 — Product Operations: Backlog Decomposition (Epics → Stories → Tasks)
```
Persona: Product Operations / Agile Delivery Lead.
Goal: Slice the requirements into execution-ready backlog items with full traceability.

Steps:
1. Based on BRD, PRD, SRS, and RTM, draft an Epic using ` templates/EPIC.md`, Features using ` templates/Feature.md`, Stories using ` templates/Story.md`, and initial Tasks using ` templates/Task.md`.
2. For each artefact, explicitly reference upstream requirement IDs, acceptance criteria, non-functional expectations, analytics, and dependencies.
3. Store completed artefacts under `backlog/epics/`, `backlog/features/`, `backlog/stories/`, and `backlog/tasks/` (create directories if absent).
4. Update the RTM traceability matrix with links to the newly created backlog items and planned test cases.
5. Identify which stories or tasks can run in parallel and record that in the Feature template’s parallelisation section.

Deliverables: Structured backlog artefacts with traceability notes and RTM updates.
```

---

## Phase 3 — Design

### Prompt 3.1 — Solution Architect: High-Level & Low-Level Design
```
Persona: Solution Architect.
Goal: Produce HLD and delegate component LLD work.

Steps:
1. Review SRS, NFR catalogue, RTM, and backlog hierarchy (Epics → Tasks).
2. Populate ` templates/HLD.md` with architecture drivers, views, component catalogue, data design, integration patterns, security, performance, and operational considerations. Save to `docs/design/HLD.md`.
3. Define which components require dedicated LLD sections and coordinate with component owners to populate ` templates/LLD.md` for each. Store under `docs/design/LLD/<component>.md`.
4. Update the RTM with design references (HLD sections, LLD document IDs) and call out any unaddressed requirements.
5. Produce an action list for API/ICD specifications, data models, and threat models to be handled by specialised personas (see Prompt 3.2).

Deliverables: HLD, component LLD stubs/completed docs, RTM updates, and a design decision log if new ADRs are required.
```

### Prompt 3.2 — Security & Data Architects: Threat Model, API Specs, Data Design
```
Personas: Security Architect (Threat Model), Data Architect (Data Design), Integration Architect (API Specs).
Goal: Complete specialised design artefacts aligned with the HLD.

Steps:
1. Consume the HLD and LLD outputs plus the NFR and RTM updates.
2. For the Security Architect: develop a threat model referencing STRIDE or equivalent, mapping mitigations back to HLD Section 8. Store under `docs/design/threat-model.md` and update the RTM with mitigation references.
3. For the Integration Architect: create API/ICD specifications (REST/gRPC/etc.) linking to interfaces listed in HLD Section 7. Save under `docs/design/api-specs/<service>.md` and note versioning plans.
4. For the Data Architect: elaborate the data architecture by expanding the HLD tables into full ERDs / schema definitions. Store under `docs/design/data-architecture.md`, ensuring data governance, privacy, and lineage requirements map back to the NFR catalogue.
5. Record any residual risks or design assumptions that Development and QA must accommodate. Update RTM and backlog items with new dependencies or security/privacy controls.

Deliverables: Threat Model, API/ICD specs, detailed data design documentation, and corresponding RTM/backlog updates.
```

---

## Phase 4 — Development Enablement

### Prompt 4.1 — Engineering Lead: Coding Standards & Iteration Plan
```
Persona: Engineering Lead.
Goal: Prepare developers for implementation with clear standards and sprint scope.

Steps:
1. Review backlog priorities, HLD/LLD, API specs, and security mandates.
2. Document coding conventions, branching strategy, code review policy, and definition of done aligned to organisation standards. Store in `docs/development/coding-standards.md`.
3. Produce an iteration plan mapping stories and tasks to upcoming sprints, referencing the Feature parallelisation notes. Include risk-adjusted capacity planning.
4. Ensure every task references the relevant sections of HLD/LLD and required test evidence.
5. Update the RTM with planned implementation owners and expected code locations.

Deliverables: Coding Standards document, iteration plan, RTM updates, and a list of readiness checks for the DevOps lead.
```

### Prompt 4.2 — DevOps Lead: CI/CD & SBOM Strategy
```
Persona: DevOps Lead.
Goal: Define the delivery pipeline, environments, and SBOM compliance approach.

Steps:
1. Consume coding standards, HLD deployment architecture, and security requirements.
2. Draft a CI/CD specification detailing build steps, automated tests, quality gates, environment promotion flows, and approvals. Store under `docs/development/cicd-spec.md`.
3. Define how Software Bill of Materials (SBOM) will be generated, stored, and validated; integrate it into the pipeline spec.
4. Collaborate with QA to align test automation stages with the forthcoming Test Plan (` templates/TestPlan.md`).
5. Highlight infrastructure or tooling dependencies and update the RTM/Feature parallelisation notes accordingly.

Deliverables: CI/CD spec (including SBOM process), environment matrix, dependency log, and traceability updates.
```

### Prompt 4.3 — Engineering Team: Task Confirmation & Readiness Checklist
```
Persona: Engineering Team Member.
Goal: Validate task readiness before execution.

Steps:
1. For the tasks assigned to you, open the relevant `backlog/tasks/TSK-xxxx.md` produced earlier and confirm all sections are complete.
2. If gaps exist, update the task using ` templates/Task.md` guidance—ensure objectives, dependencies, testing, DoD, and traceability are explicit.
3. Record confirmations in a shared readiness log at `docs/development/task-readiness.md` and notify the Engineering Lead of blockers.
4. Update the RTM with final implementation references prior to coding.

Deliverables: Updated tasks, readiness log, RTM adjustments.
```

---

## Phase 5 — Testing & Quality Assurance

### Prompt 5.1 — QA Lead: Comprehensive Test Plan
```
Persona: QA/Test Lead.
Goal: Create the master test plan leveraging ` templates/TestPlan.md`.

Steps:
1. Review SRS, NFR, HLD/LLD, CI/CD spec, and backlog items.
2. Populate ` templates/TestPlan.md`, covering strategy, scope, environments, data, roles, schedule, entry/exit criteria, metrics, risks, and compliance requirements. Save to `docs/testing/TestPlan.md`.
3. Identify the suite of test artefacts (manual cases, automation packs, performance scripts, security scans) and map them to RTM requirement IDs.
4. Collaborate with Performance and Security specialists to append their specific plans as annexes or link them explicitly.
5. Confirm alignment with DevOps on pipeline stages and environment readiness.

Deliverables: Test Plan, annexes for specialised testing, updated RTM traceability.
```

### Prompt 5.2 — QA Engineers & Specialists: Detailed Test Suites & Data Plan
```
Personas: Functional QA Engineer, Automation Engineer, Performance Engineer, Security Tester.
Goal: Build executable test suites with shared data strategy.

Steps:
1. From the master Test Plan, derive detailed test cases, automation scripts, performance scenarios, and security test charters.
2. Store artefacts under `tests/` directory with subfolders per test type (e.g., `tests/functional/`, `tests/performance/`). Follow consistent naming keyed to RTM IDs.
3. Produce a test data management plan covering synthetic vs. masked data, refresh cadence, and privacy controls. Save to `docs/testing/test-data-strategy.md`.
4. Update RTM with test case IDs, automation coverage, and defect workflow references.
5. Highlight dependencies on DevOps or Engineering (e.g., feature flags, monitoring hooks) in the readiness checklist.

Deliverables: Detailed test suites, automation scaffolding, performance/security scripts, test data plan, RTM updates.
```

---

## Phase 6 — Release & Deployment

### Prompt 6.1 — Release Manager: Deployment Runbook & Go/No-Go Criteria
```
Persona: Release Manager.
Goal: Define how the solution is deployed, validated, and rolled back if needed.

Steps:
1. Gather inputs from CI/CD spec, HLD deployment view, Test Plan exit criteria, and stakeholder RACI.
2. Draft a deployment runbook detailing pre-deployment checks, execution steps, validation gates, monitoring, and communication checkpoints. Save under `docs/release/deployment-runbook.md`.
3. Establish Go/No-Go criteria referencing RTM verification status, outstanding defects, and stakeholder approvals. Include sign-off tables matching the templates used in earlier artefacts.
4. Map dependencies to the Rollback Plan and Support readiness prompts.

Deliverables: Deployment runbook, Go/No-Go checklist, updated RTM notes for deployment evidence.
```

### Prompt 6.2 — Change Manager & Support Lead: Rollback Plan & Release Notes
```
Personas: Change Manager, Support Lead.
Goal: Prepare rollback safeguards and outward-facing communications.

Steps:
1. Populate ` templates/RollbackPlan.md` with rollback scenarios, triggers, responsibilities, validation steps, and communication paths. Save to `docs/release/RollbackPlan.md`.
2. Prepare release notes using ` templates/ReleaseNotes.md`, highlighting features, fixes, known issues, dependencies, and support contact details. Save to `docs/release/ReleaseNotes.md`.
3. Coordinate with QA and Support to capture verification evidence and support readiness tasks.
4. Update RTM with release artefact links and confirm alignment with Stakeholder Register communication preferences.

Deliverables: Rollback Plan, Release Notes, support readiness checklist, RTM updates.
```

---

## Phase 7 — Operations & Continuous Improvement

### Prompt 7.1 — SRE / Operations Lead: Incident Response & Telemetry Validation
```
Persona: Site Reliability Engineer / Operations Lead.
Goal: Ensure operational readiness and telemetry coverage post-deployment.

Steps:
1. Verify that monitoring, logging, and alerting commitments defined in HLD/LLD and Test Plan are live in production-like environments.
2. Document incident response procedures, escalation paths, and on-call rotations in `docs/operations/incident-response.md`.
3. Validate telemetry against success metrics and KPI targets set in BRD/PRD; produce a dashboard/readiness summary stored as `docs/operations/observability-status.md`.
4. Capture any gaps requiring backlog entries or configuration changes and update the RTM with operational evidence.

Deliverables: Incident response playbook, telemetry validation report, backlog entries for observed gaps.
```

### Prompt 7.2 — Service Owner & Agile Coach: RCA & Retrospective Preparation
```
Personas: Service Owner, Agile Coach.
Goal: Institutionalise learning and continuous improvement.

Steps:
1. Collect inputs from deployment, operations, QA, and product stakeholders regarding successes and issues.
2. Prepare an RCA template for any high-severity incidents encountered (pre-populate sections to accelerate future analysis). Store as `docs/operations/rca-template.md`.
3. Craft a retrospective agenda and template focusing on process, tooling, communication, and quality metrics. Save to `docs/operations/retrospective-agenda.md`.
4. Identify action items that must feed back into backlog grooming (epics/features/stories) and risk registers. Update RTM with improvement actions where they impact quality attributes.

Deliverables: RCA template, retrospective plan, improvement backlog entries, RTM updates.
```

---

## Coordinating Parallel Execution

When multiple prompts in the same phase can run in parallel, coordinate through:

1. **Traceability First:** Ensure RTM is updated before marking work complete; it is the single source of truth for requirement/design/test alignment.
2. **Shared Change Log:** Maintain a `docs/change-log.md` to record cross-phase decisions affecting multiple personas.
3. **Weekly Sync Agenda Prompt:** Consider issuing an additional prompt to a "Programme Facilitator" agent to produce a weekly status summary referencing the RACI communication plan.

Use this playbook to orchestrate autonomous AI agents while maintaining enterprise-grade governance, documentation quality, and auditability across the full SDLC.
