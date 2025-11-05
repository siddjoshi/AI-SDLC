# Phase 6.2 – Change Manager & Support Lead Prompt (Rollback Plan & Release Communications)

## Context
- **Prerequisites:** Deployment runbook and Go/No-Go criteria drafted (Phase 6.1); QA evidence progressing; RTM updated with release coverage; change log current.
- **Reference Artefacts:** `docs/release/deployment-runbook.md`, `docs/release/go-no-go-checklist.md`, `docs/requirements/RTM.md`, `docs/testing/TestPlan.md`, test results, stakeholder register, communication plan, risk register.
- **Templates:** ` templates/RollbackPlan.md`, ` templates/ReleaseNotes.md`.
- **Downstream Dependencies:** Operations readiness (Phase 7), support teams, stakeholders receiving communications.

## Objective
Develop a robust rollback strategy and stakeholder-facing release communications, ensuring alignment with governance requirements and support readiness.

## Step-by-Step Instructions
1. **Inputs Review**
   - Confirm deployment steps, validation points, and risk profile from runbook and QA status.
   - Identify support escalation paths and incident processes from stakeholder register.
2. **Author Rollback Plan**
   - Clone ` templates/RollbackPlan.md` into `docs/release/RollbackPlan.md`.
   - Document rollback triggers, ownership, detailed steps, verification checks, data considerations, communication, and recovery timelines.
3. **Prepare Release Notes**
   - Clone ` templates/ReleaseNotes.md` into `docs/release/ReleaseNotes.md`.
   - Capture delivered features, fixes, technical impacts, known issues, dependencies, and user communication details.
   - Align messaging with stakeholder communication plan (channels, cadence).
4. **Support Readiness Assessment**
   - Create or update `docs/release/support-readiness-checklist.md` covering training, knowledge base updates, on-call roster, SLA agreements, and incident routes.
5. **Traceability & Governance**
   - Update RTM with rollback controls, release note references, and support readiness evidence.
   - Log approvals, risks, and outstanding actions in `docs/change-log.md`.
6. **Communication Coordination**
   - Plan announcement schedule, Go/No-Go decision points, and post-release follow-ups in alignment with RACI.

## Deliverables
- `docs/release/RollbackPlan.md`
- `docs/release/ReleaseNotes.md`
- `docs/release/support-readiness-checklist.md`
- Updated `docs/requirements/RTM.md`
- Change log entries for rollback and communication decisions

## Traceability & Handover Requirements
- Ensure rollback steps align with CI/CD pipeline controls and operations monitoring.
- Provide SRE/Operations with failure scenarios and support contact matrix.
- Share release notes with stakeholders per communication plan; confirm acknowledgement where required.

## Completion Criteria
- Rollback Plan and Release Notes approved with no placeholders; support readiness checklist indicates Go or flagged items with deadlines.
- RTM reflects release artefact coverage; change log captures outstanding risks and approvals.
- Communication plan scheduled and stakeholders informed of timelines and responsibilities.

## Parallelisation Notes
- Operations readiness (Phase 7) can begin once rollback strategy and support checklist are drafted; maintain RTM/change log alignment for updates.
