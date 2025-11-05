# Phase 1.2 – Portfolio Manager Prompt (Stakeholder Register, RACI, Communication Plan)

## Context
- **Phase Sequence:** Executes immediately after `phase-01-inception/01-business-strategist.md` is complete.
- **Upstream Inputs:** `docs/inception/business-case.md`, `docs/inception/vision-and-goals.md`.
- **Downstream Dependencies:** Stakeholder allocations and communication cadences feed approval sections in ` templates/BRD.md`, ` templates/HLD.md`, ` templates/TestPlan.md`, and release artefacts.

## Objective
Establish comprehensive stakeholder governance artefacts that future agents can reference for approvals, communications, and decision-making without further clarification.

## Step-by-Step Instructions
1. **Ingest Prior Artefacts**
   - Read the Business Case and Vision & Goals documents.
   - Extract key initiatives, KPIs, risks, and assumed sponsors.
2. **Create Stakeholder Register**
   - Generate `docs/inception/stakeholder-register.md` (use tables).
   - For each stakeholder: capture name/persona, organisation, role, responsibilities, decision rights, influence, interest, preferred communication channel, and availability.
   - Map each stakeholder to the artefacts they must review/approve across the SDLC.
3. **Derive RACI Matrix**
   - Create `docs/inception/raci-matrix.md`.
   - Define responsibilities for every core template listed in `README.md` (BRD, PRD, SRS, HLD, Test Plan, Rollback Plan, etc.).
   - Ensure no artefact lacks an Accountable role. Highlight overlaps or overloads in a notes section.
4. **Author Communication Plan**
   - Create `docs/inception/communication-plan.md`.
   - Specify meeting cadences, audiences, communication channels, artefacts shared, escalation paths, and key milestones for each phase.
   - Align the plan with RACI outcomes and note any tooling integrations (e.g., dashboards, wikis).
5. **Traceability Hooks**
   - Append a section summarising how stakeholder IDs will map into the approval tables inside ` templates/BRD.md`, ` templates/HLD.md`, and ` templates/TestPlan.md`.
   - Document any new stakeholders that must be added to the change log.
6. **Validation & Publishing**
   - Version each document (0.1 Draft → 1.0 Baseline) and capture Portfolio Manager sign-off.
   - Update `docs/change-log.md` with newly identified stakeholders, communication cadences, and governance decisions.

## Deliverables
- `docs/inception/stakeholder-register.md`
- `docs/inception/raci-matrix.md`
- `docs/inception/communication-plan.md`
- Updated `docs/change-log.md`

## Traceability & Handover Requirements
- Reference stakeholder IDs in a summary table for use in requirements, design, testing, and release templates.
- Explicitly call out Accountable owners for approvals to ensure downstream prompts can auto-populate sign-off tables.
- Provide communication triggers that align with the parallel execution notes in future phases.

## Completion Criteria
- All three governance documents are complete, version-controlled, and cross-linked.
- Every SDLC artefact listed in README has named Responsible and Accountable roles.
- Communication plan includes escalation paths and publication cadence for RTM updates.

## Parallelisation Notes
- Once this prompt completes, Phase 2 prompts (requirements) can start. RACI and communication plans remain the reference point for all subsequent persona prompts.
