# Phase 2.1 – Product Manager Prompt (Business & Product Requirements)

## Context
- **Phase Sequence:** Begins Phase 2 after completion of Phase 1 prompts.
- **Upstream Inputs:** `docs/inception/business-case.md`, `docs/inception/vision-and-goals.md`, stakeholder governance pack (`stakeholder-register`, `raci-matrix`, `communication-plan`).
- **Downstream Dependencies:** Outputs drive SRS, NFR catalogue, RTM seeding, backlog decomposition, and architecture design.
- **Templates:** ` templates/BRD.md`, ` templates/PRD.md`.

## Objective
Produce baseline BRD and PRD documents that translate business intent into product requirements, ready for immediate consumption by analysts, architects, and delivery teams.

## Step-by-Step Instructions
1. **Foundation Review**
   - Confirm mandatory requirements in `README.md` and capture stakeholder approvals from RACI matrix.
   - Extract KPIs, risks, and constraints from Business Case and Vision & Goals.
2. **Populate BRD**
   - Clone ` templates/BRD.md` into `docs/requirements/BRD.md`.
   - Fill every section with project-specific content (executive summary, objectives, scope, processes, benefits, cost-benefit analysis, risks, timeline, approvals).
   - Map each business objective to measurable KPIs and stakeholder expectations.
3. **Draft PRD**
   - Clone ` templates/PRD.md` into `docs/requirements/PRD.md`.
   - Document personas, journeys, feature catalogue, user stories (high-level), acceptance criteria, non-functional considerations, analytics, release strategy, risk register.
   - Ensure features reference BRD objectives and include IDs for traceability.
4. **Traceability Preparation**
   - Assign requirement IDs (e.g., BRD-OBJ-01, PRD-FEAT-01) and log them in a traceability section to seed `docs/requirements/RTM.md`.
   - Identify which requirements will become Epics, Features, and Stories.
5. **Stakeholder & Approval Integration**
   - Populate approval tables using stakeholder IDs from the register.
   - Document review cadence based on the communication plan.
6. **Risk & Decision Log**
   - Record decisions, open questions, and risks with owners.
   - Update `docs/change-log.md` with major requirement baselines and pending items.

## Deliverables
- `docs/requirements/BRD.md`
- `docs/requirements/PRD.md`
- Updates to `docs/change-log.md`

## Traceability & Handover Requirements
- Provide a mapping table of BRD/PRD requirement IDs to future SRS sections and backlog artefacts.
- Highlight regulatory/compliance drivers that architects and QA must address.
- Notify Systems Analyst persona (Phase 2.2) of any unresolved assumptions requiring validation.

## Completion Criteria
- BRD and PRD are fully populated with no placeholder text and versioned (0.1 Draft → 1.0 Baseline).
- All objectives, features, and acceptance criteria have IDs and traceability notes.
- Stakeholder approvals captured or pending actions recorded with due dates.

## Parallelisation Notes
- Once BRD is baselined, the Systems Analyst and Product Operations prompts can begin in parallel. Maintain BRD/PRD changelog entries for coordination.
