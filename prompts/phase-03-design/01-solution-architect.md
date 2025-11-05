# Phase 3.1 – Solution Architect Prompt (High-Level & Low-Level Design Foundation)

## Context
- **Prerequisites:** Requirements artefacts baselined (BRD, PRD, SRS, NFR), RTM updated, backlog hierarchy published, change log current.
- **Reference Artefacts:** `docs/requirements/BRD.md`, `docs/requirements/PRD.md`, `docs/requirements/SRS.md`, `docs/requirements/NFR.md` (if produced), `docs/requirements/RTM.md`, backlog items.
- **Templates:** ` templates/HLD.md`, ` templates/LLD.md`.
- **Downstream Dependencies:** Security/Data architects (Phase 3.2), Development (Phase 4), QA/Test (Phase 5).

## Objective
Produce an enterprise-grade High-Level Design (HLD) and orchestrate component-level LLD development, ensuring alignment to requirements, NFRs, and traceability commitments.

## Step-by-Step Instructions
1. **Preparation & Gap Check**
   - Validate completeness of SRS/NFR/RTM entries; log gaps in change log.
   - Confirm architecture constraints (tech standards, compliance) from BRD/PRD.
2. **Author HLD**
   - Clone ` templates/HLD.md` into `docs/design/HLD.md`.
   - Populate architecture overview, drivers, views, component catalogue, data design, integration patterns, security, performance, operational considerations, deployment model, governance.
   - Reference requirement IDs from RTM in relevant sections for traceability.
3. **Plan LLD Coverage**
   - Identify components/services requiring detailed design.
   - Clone ` templates/LLD.md` per component into `docs/design/LLD/<component>.md`.
   - Assign authors/owners and provide structure for interface, data, state, sequence, and error handling details.
4. **Traceability & RTM Update**
   - Update RTM to map requirements to HLD sections and planned LLD documents.
   - Note any residual risks or design decisions requiring Architecture Decision Records.
5. **Collaboration & Handover**
   - Produce a design review agenda and stakeholder list based on RACI.
   - Highlight inputs required by Phase 3.2 specialists (interfaces, security surfaces, data flows).
   - Update `docs/change-log.md` with HLD version, review schedule, unresolved questions.

## Deliverables
- `docs/design/HLD.md`
- `docs/design/LLD/<component>.md` stubs or completed drafts
- Updated `docs/requirements/RTM.md`
- Change log entries and design review agenda (optional `docs/design/design-review-agenda.md`)

## Traceability & Handover Requirements
- Each HLD section must reference relevant requirement IDs and NFR targets.
- Provide Security/Data architects with dependency list for threat modeling, API specs, and data modeling.
- Ensure backlog items remain linked to design components for Phase 4 planning.

## Completion Criteria
- HLD complete with no placeholders, approved stakeholders identified, and review scheduled.
- LLD plan established with owners; critical components drafted if required for upcoming development.
- RTM updated to include HLD/LLD references; outstanding items tracked with owners and due dates.

## Parallelisation Notes
- Phase 3.2 specialists can begin once HLD sections covering security, integration, and data are drafted; maintain change log alignment.
