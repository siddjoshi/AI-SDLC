# Phase 5.2 – QA Specialists Prompt (Test Suites, Automation, Performance & Security Validation)

## Context
- **Prerequisites:** Master Test Plan drafted (Phase 5.1); RTM updated with planned coverage; CI/CD spec, environment matrix, backlog tasks ready; change log current.
- **Reference Artefacts:** `docs/testing/TestPlan.md`, `docs/requirements/RTM.md`, backlog stories/tasks, `docs/requirements/SRS.md`, `docs/requirements/NFR.md`, `docs/design/HLD.md`, `docs/design/LLD/`, `docs/design/threat-model.md`, `docs/development/cicd-spec.md`, `docs/development/environment-matrix.md`.
- **Personas:** Functional QA Engineer, Automation Engineer, Performance Engineer, Security Tester.
- **Downstream Consumers:** Release (Phase 6), Operations (Phase 7), Engineering (feedback loop).

## Objective
Develop detailed, executable test artefacts (manual, automated, performance, security) and supporting data strategy aligned with the master Test Plan and RTM.

## Step-by-Step Instructions
1. **Scope Allocation**
   - Partition test responsibilities based on Test Plan sections and backlog priorities.
   - Confirm acceptance criteria and design references for each story/task.
2. **Functional & Regression Suites**
   - Author manual/BDD test cases stored under `tests/functional/` (create directories as needed).
   - Include requirement IDs, preconditions, steps, expected results, data requirements, and traceability notes.
3. **Automation Framework Setup**
   - Establish automation structure under `tests/automation/` referencing coding standards and CI/CD integration points.
   - Document framework usage, tooling, and execution instructions in `tests/automation/README.md`.
   - Ensure pipeline hooks are defined in collaboration with DevOps.
4. **Performance & Security Testing**
   - For Performance Engineer: create test scenarios, workload models, SLAs, and scripts under `tests/performance/` with links to NFR metrics.
   - For Security Tester: define security test charters, automated scans, and manual testing procedures in `tests/security/` referencing threat model mitigations.
5. **Test Data Strategy**
   - Draft `docs/testing/test-data-strategy.md` covering data sources, masking/synthetic approaches, refresh cadence, access controls, compliance.
6. **Traceability & Reporting**
   - Update RTM with test case IDs, automation coverage, performance/security artefacts, and planned evidence.
   - Record execution schedule and status tracking approach in change log or dedicated QA dashboard.

## Deliverables
- Populated test suites under `tests/functional/`, `tests/automation/`, `tests/performance/`, `tests/security/`
- `tests/automation/README.md`
- `docs/testing/test-data-strategy.md`
- Updated `docs/requirements/RTM.md`
- QA tracking updates in change log / dashboard

## Traceability & Handover Requirements
- Ensure every test artefact links to originating requirement IDs and NFR metrics.
- Provide Release Manager with insight into verification evidence expectations.
- Share dependencies with Engineering/DevOps (feature flags, environment needs, telemetry hooks).

## Completion Criteria
- Test suites and data strategy documented with no placeholders; automation framework ready for pipeline integration.
- RTM reflects detailed test coverage; gaps documented with owners and timelines.
- Communication issued summarising QA readiness, blockers, and next steps.

## Parallelisation Notes
- Release planning (Phase 6) can begin once test coverage scope is clear; maintain ongoing updates through RTM and change log to reflect progress and results.
