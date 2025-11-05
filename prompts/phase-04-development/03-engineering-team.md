# Phase 4.3 – Engineering Team Prompt (Task Readiness & Execution Prep)

## Context
- **Prerequisites:** Coding standards, iteration plan, CI/CD spec, environment matrix, and backlog artefacts published; RTM current; change log updated with delivery notes.
- **Reference Artefacts:** `docs/development/coding-standards.md`, `docs/development/iteration-plan.md`, `docs/development/cicd-spec.md`, `docs/development/environment-matrix.md`, `docs/development/sbom-strategy.md`, backlog tasks, `docs/requirements/RTM.md`, `docs/design/LLD/`.
- **Downstream Dependencies:** QA/Test (Phase 5), Release (Phase 6) for readiness evidence.

## Objective
Validate that each development task is fully ready for execution, address gaps, and confirm traceability prior to implementation start.

## Step-by-Step Instructions
1. **Task Audit**
   - Open assigned task files in `backlog/tasks/` and review each section (objective, prerequisites, dependencies, acceptance tests, DoD, traceability, effort, risks).
   - Ensure alignment with corresponding stories/features and LLD components.
2. **Update & Enrich Tasks**
   - Where gaps exist, update task artefacts following ` templates/Task.md` (no placeholders). Include links to relevant design, RTM entries, and pipeline steps.
   - Capture partial work notes or clarifications within task file under “Open Questions/To Clarify”.
3. **Readiness Logging**
   - Record status in `docs/development/task-readiness.md`, noting blockers, dependencies, and ETA for resolution.
   - Escalate unresolved issues to Engineering Lead and DevOps Lead.
4. **Traceability Confirmation**
   - Verify RTM entries reference correct task IDs; update as needed to ensure forward traceability from requirements → design → backlog → implementation/testing.
5. **Risk & Dependency Management**
   - Document any technical or resource risks in change log or readiness log with mitigation plans.
   - Highlight tasks requiring cross-team coordination (security, data, QA).

## Deliverables
- Updated task files in `backlog/tasks/`
- `docs/development/task-readiness.md` with current status
- Updated `docs/requirements/RTM.md`
- Logged blockers/risks in change log

## Traceability & Handover Requirements
- Confirm every task references its originating requirement ID, design artefact, and planned test cases.
- Provide QA with early insight into implementation sequencing for test planning.
- Notify Release Manager of any deployment prerequisites discovered.

## Completion Criteria
- All tasks marked Ready with no TBD sections; blockers documented with owners and deadlines.
- RTM reflects complete linkage through to tasks; readiness log indicates go/no-go for execution.
- Stakeholders informed of risks and mitigation strategies.

## Parallelisation Notes
- QA planning (Phase 5.1) can start in parallel once readiness log is established; keep change log aligned for transparency.
