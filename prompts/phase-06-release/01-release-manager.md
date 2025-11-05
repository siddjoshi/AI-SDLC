# Phase 6.1 – Release Manager Prompt (Deployment Runbook & Go/No-Go Criteria)

## Context
- **Prerequisites:** QA artefacts in progress/completed (Test Plan, suites, data strategy); CI/CD spec and environment matrix finalised; backlog status tracked; RTM updated with test progress; change log current.
- **Reference Artefacts:** `docs/testing/TestPlan.md`, test suite directories under `tests/`, `docs/development/cicd-spec.md`, `docs/development/environment-matrix.md`, `docs/development/sbom-strategy.md`, `docs/requirements/RTM.md`, stakeholder register, communication plan.
- **Downstream Dependencies:** Change Manager & Support Lead (Phase 6.2), Operations (Phase 7).

## Objective
Define the deployment process, governance checkpoints, and Go/No-Go criteria to ensure controlled release into target environments.

## Step-by-Step Instructions
1. **Gather Inputs**
   - Review test coverage status, outstanding defects, and risk assessments from QA team.
   - Confirm pipeline deployment steps, approval workflows, and rollback hooks.
2. **Create Deployment Runbook**
   - Draft `docs/release/deployment-runbook.md` detailing pre-deployment checks, deployment steps per environment, validation activities, monitoring, communication, and contingency plans.
   - Include roles & responsibilities mapped to stakeholder register/RACI.
3. **Define Go/No-Go Criteria**
   - Establish entry/exit criteria referencing RTM coverage, test results, defect thresholds, compliance checks, and stakeholder approvals.
   - Store checklist within runbook or separate `docs/release/go-no-go-checklist.md`.
4. **Evidence & Reporting Plan**
   - Specify required deployment evidence (logs, screenshots, metrics) and storage location.
   - Align reporting cadence with communication plan.
5. **Traceability & Updates**
   - Update RTM with deployment evidence requirements and control references.
   - Log decisions, risks, and pending approvals in `docs/change-log.md`.

## Deliverables
- `docs/release/deployment-runbook.md`
- `docs/release/go-no-go-checklist.md` (optional separate file)
- Updated `docs/requirements/RTM.md`
- Change log entries summarising release governance decisions

## Traceability & Handover Requirements
- Link runbook steps to requirements/NFRs (e.g., availability, compliance) via RTM.
- Notify Change Manager and Support Lead of required inputs (rollback details, release notes, support readiness).
- Provide Operations with monitoring and telemetry expectations post-release.

## Completion Criteria
- Deployment runbook approved; Go/No-Go criteria agreed with stakeholders.
- RTM captures release evidence linkage; change log lists outstanding actions with owners.
- Communication sent to release stakeholders outlining schedule, checkpoints, and responsibilities.

## Parallelisation Notes
- Change Manager/Support Lead (Phase 6.2) can proceed once runbook structure and key criteria are defined; ensure updates reflected in RTM and change log for traceability.
