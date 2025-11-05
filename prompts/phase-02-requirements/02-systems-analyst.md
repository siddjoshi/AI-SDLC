# Phase 2.2 – Systems Analyst Prompt (Functional & System Requirements Specification)

## Context
- **Entry Conditions:** BRD & PRD baselined (Phase 2.1), change log seeded, stakeholder approvals recorded.
- **Primary References:** `docs/requirements/BRD.md`, `docs/requirements/PRD.md`, business capability map, stakeholder interviews, and communication plan.
- **Templates:** ` templates/SRS.md`, ` templates/RTM.md`, ` templates/NFR.md` (for cross-checking).
- **Downstream Consumers:** Architects (Phase 3), Test Leads (Phase 5), Product Operations (Phase 2.3), Development Teams (Phase 4).

## Objective
Translate business and product requirements into a structured System Requirements Specification (SRS) and initialise the Requirements Traceability Matrix (RTM) to ensure linkage across the delivery lifecycle.

## Step-by-Step Instructions
1. **Context Validation**
   - Review BRD/PRD objectives, scope, personas, and prioritized features.
   - Confirm assumptions, dependencies, and regulatory obligations.
   - Capture outstanding questions for resolution via stakeholder workshops.
2. **Assemble SRS**
   - Clone ` templates/SRS.md` into `docs/requirements/SRS.md`.
   - Populate sections: system overview, business context, functional requirements (use cases, user stories, acceptance criteria), data requirements, interface specifications, compliance, constraints, and change management.
   - Create detailed requirement IDs (e.g., SRS-FUNC-001) and map to BRD/PRD IDs.
3. **Detail “To-Be” Processes & Scenarios**
   - Model process flows, state diagrams, and data flow narrative for critical use cases.
   - Annotate exception paths, alternate flows, and non-happy path scenarios.
   - Document business rules and validation logic explicitly.
4. **Seed RTM**
   - Clone ` templates/RTM.md` into `docs/requirements/RTM.md` if not already present.
   - Populate initial matrix linking BRD/PRD IDs → SRS requirement IDs → planned test coverage → backlog artefacts.
   - Note unfulfilled traceability gaps and assign owners.
5. **Non-Functional Requirement Alignment**
   - Extract NFR references from PRD and draft initial NFR catalogue entries to be elaborated in Phase 2.3.
   - Flag critical performance, security, accessibility, and compliance drivers for architects/test leads.
6. **Collaboration & Review Prep**
   - Schedule requirement walkthrough sessions using communication plan.
   - Update `docs/change-log.md` with SRS/RTM version info and open decisions.
   - Prepare summary for sign-off including open issues and dependencies.

## Deliverables
- `docs/requirements/SRS.md`
- Seeded `docs/requirements/RTM.md`
- Updated `docs/change-log.md`
- Decision & query backlog (append to change log or separate `docs/requirements/questions.md`)

## Traceability & Handover Requirements
- Ensure each SRS requirement traces back to a BRD/PRD item and forward to RTM entries.
- Provide architects with consolidated list of integration points, data entities, and interface requirements.
- Notify Test Lead (Phase 5.1) of critical acceptance criteria impacting test design.

## Completion Criteria
- SRS sections complete with no TBD placeholders; all requirements uniquely identified and classified.
- RTM initial pass completed with ≥90% coverage of BRD/PRD requirements; gaps documented with owners.
- All outstanding queries recorded with due dates and responsible stakeholders.

## Parallelisation Notes
- Product Operations (Phase 2.3) can begin NFR elaboration after SRS draft is available; maintain synchronized updates through change log and RTM revisions.
