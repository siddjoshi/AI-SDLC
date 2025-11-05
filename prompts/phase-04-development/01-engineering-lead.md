# Phase 4.1 – Engineering Lead Prompt (Coding Standards & Iteration Planning)

## Context
- **Prerequisites:** Design artefacts (HLD, LLD, threat model, API specs, data architecture) approved/drafted; backlog hierarchy established; RTM current; change log updated.
- **Reference Artefacts:** `docs/design/HLD.md`, `docs/design/LLD/`, `docs/design/threat-model.md`, `docs/design/api-specs/`, `docs/design/data-architecture.md`, `docs/requirements/RTM.md`, backlog directories.
- **Outputs Feed:** Development teams, DevOps pipeline design (Phase 4.2), QA planning (Phase 5).

## Objective
Define coding conventions, engineering governance, and iteration plan that align design intent with delivery execution.

## Step-by-Step Instructions
1. **Synthesize Inputs**
   - Review backlog priorities and dependencies from `backlog/` artefacts and RTM.
   - Identify architectural and security guidelines requiring developer adherence.
2. **Draft Coding Standards**
   - Create `docs/development/coding-standards.md` covering languages, frameworks, patterns, code review processes, branching strategy, testing expectations, documentation standards, and definition of done.
   - Reference security, performance, and accessibility requirements from NFR catalogue.
3. **Iteration/Sprint Planning**
   - Produce `docs/development/iteration-plan.md` mapping features/stories to sprints with capacity, dependencies, and risk adjustments.
   - Note parallelisation opportunities and constraints documented in backlog artefacts.
4. **Readiness & Risk Register**
   - Create or update `docs/development/readiness-checklist.md` capturing prerequisites (environments, tooling, access, data, training).
   - Record risks, mitigations, and escalation paths impacting delivery.
5. **Traceability Update**
   - Update RTM with planned implementation ownership and references to coding standards/iteration plan.
   - Log significant decisions in `docs/change-log.md`.

## Deliverables
- `docs/development/coding-standards.md`
- `docs/development/iteration-plan.md`
- `docs/development/readiness-checklist.md`
- Updated `docs/requirements/RTM.md`
- Change log entries and risk updates

## Traceability & Handover Requirements
- Link coding standards to relevant requirements/NFRs within RTM comments.
- Provide DevOps Lead with dependencies for pipeline configuration and quality gates.
- Share iteration plan with QA and Release teams for scheduling alignment.

## Completion Criteria
- Coding standards approved/published, iteration plan aligns with backlog priorities, readiness checklist clear with owners and due dates.
- RTM reflects implementation ownership; change log records outstanding actions.

## Parallelisation Notes
- DevOps Lead (Phase 4.2) may start once initial coding standards are drafted; engineering team readiness checks (Phase 4.3) follow after plan publication.
