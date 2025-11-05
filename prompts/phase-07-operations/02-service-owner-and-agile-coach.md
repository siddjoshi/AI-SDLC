# Phase 7.2 – Service Owner & Agile Coach Prompt (RCA & Continuous Improvement)

## Context
- **Prerequisites:** Release completed or in production readiness review; incident response and observability documents prepared (Phase 7.1); change log updated; RTM reflects operational evidence; stakeholder feedback available.
- **Reference Artefacts:** `docs/operations/incident-response.md`, `docs/operations/observability-status.md`, `docs/release/deployment-runbook.md`, `docs/release/RollbackPlan.md`, `docs/release/ReleaseNotes.md`, `docs/testing/TestPlan.md`, `docs/requirements/RTM.md`, backlog artefacts, risk register, communication plan.
- **Downstream Dependencies:** Future delivery cycles, backlog refinement, governance reporting.

## Objective
Capture learnings via RCA templates, plan retrospectives, and channel improvements into the delivery backlog for continuous optimisation.

## Step-by-Step Instructions
1. **Evidence Review**
   - Assess release outcomes, incident reports, telemetry status, stakeholder feedback, and defect trends.
   - Identify notable successes, issues, and improvement opportunities.
2. **RCA Template Preparation**
   - Create `docs/operations/rca-template.md` with structure for incident summary, timeline, contributing factors, corrective/preventive actions, verification, and lessons learned.
   - Pre-populate with examples or placeholders derived from current release context.
3. **Retrospective Planning**
   - Draft `docs/operations/retrospective-agenda.md` outlining goals, attendees, data points (KPIs, defects, velocity), facilitation plan, and action item tracking approach.
   - Incorporate cross-functional perspectives (Product, Engineering, QA, DevOps, Support).
4. **Improvement Backlog & Traceability**
   - Log improvement actions into backlog artefacts (new epics/features/stories/tasks) or dedicated `backlog/improvements/` directory.
   - Update RTM with continuous improvement items where they impact requirements or NFRs.
5. **Governance & Reporting**
   - Summarise key insights and planned actions in change log.
   - Prepare executive-ready summary or dashboard as needed for programme governance.

## Deliverables
- `docs/operations/rca-template.md`
- `docs/operations/retrospective-agenda.md`
- Improvement backlog entries (e.g., `backlog/improvements/`)
- Updated `docs/requirements/RTM.md`
- Change log updates summarising learnings and actions

## Traceability & Handover Requirements
- Ensure improvement actions link back to metrics or issues identified during release/operations.
- Share outputs with Product Manager and Engineering Lead for incorporation into future cycles.
- Provide visibility to stakeholders via communication plan channels.

## Completion Criteria
- RCA template and retrospective agenda ready for execution; improvement actions captured with owners and due dates.
- RTM and change log reflect continuous improvement traceability.
- Stakeholders acknowledged receipt of lessons learned and action plan.

## Parallelisation Notes
- Subsequent inception/requirements phases can leverage retrospective outputs; maintain repository artefacts to ensure continuous improvement feedback loop remains auditable.
