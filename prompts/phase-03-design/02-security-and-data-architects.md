# Phase 3.2 – Security, Data & Integration Architect Prompt (Specialised Design Artefacts)

## Context
- **Prerequisites:** HLD drafted (Phase 3.1) with RTM updates, LLD component list available, change log current.
- **Reference Artefacts:** `docs/design/HLD.md`, `docs/design/LLD/`, `docs/requirements/SRS.md`, `docs/requirements/NFR.md`, `docs/requirements/RTM.md`, backlog priorities.
- **Target Documents:** Threat model, API/ICD specifications, detailed data architecture package.
- **Downstream Dependencies:** Development (Phase 4), QA (Phase 5), Release (Phase 6).

## Objective
Deliver specialised design artefacts—threat modeling, integration specifications, and data architecture—ensuring mitigation of security risks, clarity of interfaces, and integrity of data flows.

## Step-by-Step Instructions
1. **Synchronise with Solution Architect**
   - Review HLD sections related to security, integration, data, deployment, and operational requirements.
   - Confirm assumptions, unresolved items, and priority areas from change log.
2. **Threat Model (Security Architect)**
   - Document assets, trust boundaries, attack surfaces using STRIDE or equivalent.
   - Map threats to mitigations referencing HLD/LLD controls and NFR security targets.
   - Store output in `docs/design/threat-model.md` with diagrams if applicable.
   - Update RTM with threat IDs and mitigation references.
3. **API & Integration Specifications (Integration Architect)**
   - Identify interfaces from HLD Section 7 and backlog stories.
   - For each interface, create specification using internal standards (include endpoints, payloads, auth, error handling, SLAs). Store under `docs/design/api-specs/<service>.md`.
   - Link to corresponding stories/features and note test expectations for QA.
4. **Data Architecture Package (Data Architect)**
   - Expand HLD data design into detailed ERDs/schema definitions, data flow diagrams, and governance notes.
   - Capture data classification, privacy, retention, lineage, and integration with existing systems.
   - Save documentation in `docs/design/data-architecture.md` plus supporting diagrams under `docs/diagrams/` as needed.
5. **Traceability & Collaboration**
   - Update `docs/requirements/RTM.md` to include references for each specialised artefact against relevant requirements and NFRs.
   - Communicate dependencies to Engineering, QA, and DevOps (e.g., security controls, data pipelines, integration test needs).
   - Log decisions, risks, and follow-up actions in `docs/change-log.md` or dedicated design decision log.

## Deliverables
- `docs/design/threat-model.md`
- `docs/design/api-specs/<service>.md`
- `docs/design/data-architecture.md` (plus diagrams)
- Updated `docs/requirements/RTM.md`
- Change log updates / design decision entries

## Traceability & Handover Requirements
- Each threat, API, and data element must cite originating requirement IDs and note validation strategy.
- Provide QA with test considerations (security/performance/data quality) for Phase 5 planning.
- Highlight infrastructure or monitoring requirements for DevOps and Operations teams.

## Completion Criteria
- Specialised artefacts complete, reviewed with Solution Architect, and no placeholders remain.
- RTM reflects security, integration, and data design coverage; outstanding gaps have owners and deadlines.
- Stakeholders notified of new controls, dependencies, and verification obligations.

## Parallelisation Notes
- Engineering Lead (Phase 4.1) and DevOps Lead (Phase 4.2) can begin once initial specs are published; keep change log and RTM synchronised for subsequent revisions.
