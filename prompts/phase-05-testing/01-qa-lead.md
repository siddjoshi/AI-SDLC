# Phase 5.1 – QA/Test Lead Prompt (Master Test Plan)

## Context
- **Prerequisites:** Requirements (BRD, PRD, SRS, NFR), design artefacts (HLD, LLD, threat model, API specs, data architecture), backlog items, coding standards, CI/CD spec, environment matrix, RTM current, change log updated.
- **Reference Artefacts:** `docs/requirements/RTM.md`, `docs/requirements/SRS.md`, `docs/requirements/NFR.md`, `docs/design/HLD.md`, `docs/design/LLD/`, `docs/design/threat-model.md`, `docs/design/api-specs/`, `docs/design/data-architecture.md`, `docs/development/cicd-spec.md`, `docs/development/environment-matrix.md`, backlog stories/tasks.
- **Template:** ` templates/TestPlan.md`.
- **Downstream Dependencies:** QA specialists (Phase 5.2), Release (Phase 6), Operations (Phase 7).

## Objective
Create a comprehensive Test Plan that governs QA strategy, scope, schedules, environments, metrics, and risk management for the programme.

## Step-by-Step Instructions
1. **Requirement Review**
   - Validate RTM coverage; identify high-risk requirements, NFRs, and compliance obligations.
   - Capture any ambiguities or missing acceptance criteria and raise with requirements/design owners.
2. **Populate Test Plan Template**
   - Clone ` templates/TestPlan.md` into `docs/testing/TestPlan.md`.
   - Complete all sections: objectives, scope, approach, test types, environment needs, data strategy overview, metrics, entry/exit criteria, roles & responsibilities, schedule, defect process, risks, assumptions, approvals.
3. **Integration with CI/CD & Environments**
   - Align test stages with pipeline design (unit, static, integration, performance, security).
   - Define environment usage schedule referencing environment matrix; address data refresh and access controls.
4. **Traceability Setup**
   - Update RTM with planned test artefacts and coverage entries (e.g., test plan sections, suite IDs).
   - Identify residual gaps and assign owners for additional test artefacts.
5. **Stakeholder Alignment**
   - Prepare test governance cadence aligned with communication plan.
   - Update `docs/change-log.md` with test plan baseline, review schedule, and outstanding dependencies.

## Deliverables
- `docs/testing/TestPlan.md`
- Updated `docs/requirements/RTM.md`
- Change log updates (test planning decisions, risks)

## Traceability & Handover Requirements
- Ensure every requirement/NFR has corresponding planned test coverage documented in RTM.
- Brief QA specialists on ownership of detailed suites and data strategy tasks.
- Notify Release Manager of entry/exit criteria and reporting commitments.

## Completion Criteria
- Test Plan complete with no placeholders, approved roles assigned, review scheduled.
- RTM reflects test coverage mapping; outstanding gaps tracked with due dates.
- Communication sent to QA specialists and stakeholders summarising plan highlights.

## Parallelisation Notes
- QA specialists (Phase 5.2) can begin detailed suite creation once initial Test Plan sections on scope, environments, and metrics are drafted; maintain RTM synchronisation.
