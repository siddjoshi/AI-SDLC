# Phase 7.1 – SRE / Operations Lead Prompt (Incident Response & Telemetry Validation)

## Context
- **Prerequisites:** Release artefacts prepared (deployment runbook, rollback plan, release notes), QA completed or in verification, CI/CD pipeline operational, monitoring requirements defined, RTM updated with release coverage, change log current.
- **Reference Artefacts:** `docs/release/deployment-runbook.md`, `docs/release/RollbackPlan.md`, `docs/release/ReleaseNotes.md`, `docs/requirements/RTM.md`, `docs/testing/TestPlan.md`, `docs/design/HLD.md`, `docs/design/LLD/`, `docs/design/threat-model.md`, `docs/development/cicd-spec.md`, `docs/development/environment-matrix.md`, `docs/development/sbom-strategy.md`.
- **Downstream Dependencies:** Service Owner & Agile Coach (Phase 7.2), continuous improvement backlog.

## Objective
Ensure operational readiness by validating telemetry coverage, documenting incident response procedures, and confirming service-level commitments post-release.

## Step-by-Step Instructions
1. **Telemetry Verification**
   - Review monitoring/logging requirements from HLD/LLD, NFRs, and Test Plan.
   - Validate actual telemetry configuration in staging/pre-prod environments; document gaps and remediation plans.
2. **Incident Response Playbook**
   - Create `docs/operations/incident-response.md` detailing alert thresholds, runbooks, escalation paths, on-call rotations, communication templates, and post-incident actions.
   - Align with rollback procedures and stakeholder expectations.
3. **Observability Status Report**
   - Draft `docs/operations/observability-status.md` summarising KPI monitoring coverage, dashboards, alert health, and readiness to measure success metrics.
   - Highlight missing metrics or tooling integrations requiring follow-up.
4. **Traceability & RTM Update**
   - Update RTM with operational readiness evidence, linking requirements/NFRs to incident response and telemetry artefacts.
   - Document open risks or actions in change log with owners and deadlines.
5. **Collaboration & Handover**
   - Notify Change Manager, Release Manager, and Service Owner of operational readiness status.
   - Identify improvements or backlog items for continuous enhancement.

## Deliverables
- `docs/operations/incident-response.md`
- `docs/operations/observability-status.md`
- Updated `docs/requirements/RTM.md`
- Change log entries for operational readiness and gaps

## Traceability & Handover Requirements
- Ensure incident response workflows tie back to NFR targets (availability, reliability, security).
- Provide Service Owner & Agile Coach with list of operational insights and improvement candidates for retrospectives.
- Confirm telemetry evidence is stored and accessible for compliance audits.

## Completion Criteria
- Incident response playbook and observability report completed with no placeholders; gaps documented with remediation timelines.
- RTM updated with operational evidence; change log reflects readiness status.
- Stakeholders informed of operational posture and any outstanding risks.

## Parallelisation Notes
- Phase 7.2 activities (retrospectives, RCA preparation) can commence once initial operational status is documented; maintain continuous updates as telemetry gaps are closed.
