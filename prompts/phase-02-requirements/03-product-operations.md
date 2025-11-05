# Phase 2.3 – Product Operations Prompt (Backlog Decomposition & Delivery Readiness)

## Context
- **Prerequisites:** BRD & PRD baselined (Phase 2.1), SRS & RTM seeded (Phase 2.2), change log current.
- **Reference Artefacts:** `docs/requirements/BRD.md`, `docs/requirements/PRD.md`, `docs/requirements/SRS.md`, `docs/requirements/RTM.md`, stakeholder register, communication plan.
- **Templates:** ` templates/EPIC.md`, ` templates/Feature.md`, ` templates/Story.md`, ` templates/Task.md`.
- **Downstream Consumers:** Engineering (Phase 4), QA (Phase 5), Release/Operations (Phases 6 & 7).

## Objective
Decompose approved requirements into a delivery-ready backlog hierarchy (Epics → Features → Stories → Tasks) with full traceability and execution guidance.

## Step-by-Step Instructions
1. **Scope Confirmation**
   - Validate priority requirements with Product Manager and Systems Analyst.
   - Note dependencies, constraints, and NFR drivers impacting backlog sequencing.
2. **Epic Creation**
   - Clone ` templates/EPIC.md` for each major capability and store under `backlog/epics/`.
   - Populate objective, scope, success metrics, traceability, and acceptance tests.
3. **Feature Decomposition**
   - For each epic, create Features using ` templates/Feature.md` in `backlog/features/`.
   - Describe user value, functional slices, dependencies, and rollout strategy.
4. **Story Authoring**
   - Break features into Stories leveraging ` templates/Story.md` in `backlog/stories/`.
   - Include user narrative, acceptance criteria, NFR callouts, test notes, and Definition of Ready checklist.
5. **Task Detailing**
   - For every story, define implementation Tasks via ` templates/Task.md` in `backlog/tasks/`.
   - Specify engineering activities, tooling, DoD alignment, and verification evidence.
6. **Traceability & RTM Update**
   - Map each backlog item to its originating BRD/PRD/SRS IDs within documents and update `docs/requirements/RTM.md` accordingly.
   - Flag coverage gaps or dependencies requiring architecture or QA input.
7. **Parallelisation Notes & Delivery Cadence**
   - Record which features/stories can run in parallel, including dependency management guidance.
   - Update `docs/change-log.md` with backlog baseline, versioning, and outstanding actions.

## Deliverables
- Populated backlog hierarchy under `backlog/epics/`, `backlog/features/`, `backlog/stories/`, `backlog/tasks/`.
- Updated `docs/requirements/RTM.md` with backlog references.
- Logged updates in `docs/change-log.md` (or dedicated backlog log).

## Traceability & Handover Requirements
- Ensure every backlog item references upstream requirement IDs and planned validation artefacts.
- Notify Engineering Lead (Phase 4.1) of iteration planning considerations and any unresolved questions.
- Provide QA Lead (Phase 5.1) with traceability cues for test planning.

## Completion Criteria
- Backlog artefacts completed with no placeholders; IDs assigned and stored consistently.
- RTM reflects forward links from requirements to backlog with clear owners.
- Parallelisation guidance documented, and stakeholders informed of backlog baseline.

## Parallelisation Notes
- Once initial backlog is published, Engineering Lead (Phase 4.1) and DevOps Lead (Phase 4.2) can proceed using the backlog and RTM as inputs. Maintain change log entries for adjustments.
