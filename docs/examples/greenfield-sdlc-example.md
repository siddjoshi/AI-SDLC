# Greenfield SDLC Walkthrough – Intelligent Fleet Platform

| Field | Value |
|-------|-------|
| Document ID | EX-GF-001 |
| Version | 0.1 |
| Date | 2025-11-05 |
| Author | AI SDLC Agent |
| Reviewed By | _TBD_ |
| Status | Draft |

## 1. Scenario Overview

An automotive OEM is launching a new **Intelligent Fleet Platform** that lets logistics operators monitor electric delivery vans, optimise routes, and orchestrate depot charging. No prior artefacts exist; the initiative is net-new. The organisation wants to automate documentation across the full SDLC using the AI-SDLC workspace while maintaining strict traceability and compliance.

### Business Goals
- Achieve a 12% reduction in delivery time and 8% increase in fleet utilisation within the first year.
- Ensure compliance with EU battery reporting regulations and ISO 27001 security controls.
- Launch the MVP in Q3 FY2026 with phased feature flags for early adopters.

### Key Personas
- VP Logistics (Executive Sponsor)
- Fleet Operations Manager (Primary User)
- Depot Technician (Secondary User)
- Security & Compliance Officer (Governance Stakeholder)

---

## 2. Pre-Phase Intake Package

Provide the following inputs **before starting Phase 1** so agents can operate autonomously:

| Area | Required Inputs |
|------|-----------------|
| Opportunity & Outcomes | Business problem statement, measurable success metrics, initial ROI hypothesis, launch deadlines. |
| Stakeholders | Stakeholder register draft with roles, responsibilities, availability, and approval authority. |
| Scope Guardrails | In-scope capabilities (asset telemetry, route optimisation, charging orchestration), explicit exclusions (autonomous driving), dependencies (telematics vendor). |
| Compliance & Policy | Applicable standards (GDPR, ISO 27001, UNECE R155), data residency rules, privacy classifications. |
| Technology Constraints | Approved cloud providers, mandated security stack, integration expectations with ERP and telematics devices. |
| Operational Expectations | Support model target, observability tooling (Datadog), incident escalation paths, desired SLAs (uptime 99.9%). |
| Access Logistics | Contacts for vendor systems, environment provisioning workflow, credentials request path. |

Upload intake data to the workspace (e.g., `docs/inception/intake-notes.md`) and log baseline in `docs/change-log.md` before triggering agents.

---

## 3. Phase-by-Phase Execution

| Phase | Prompt Folder | Inputs to Provide | Agent Activities | Human Checkpoints | Outputs & Storage |
|-------|---------------|-------------------|------------------|-------------------|-------------------|
| **1. Inception** | `prompts/phase-01-inception/` | Intake package, executive goals, funding constraints. | Generates business case, vision/goals, stakeholder register, RACI, communication plan, seeds change log. | Sponsor confirms KPIs & budget envelope within 1 business day. | `docs/inception/business-case.md`, `vision-and-goals.md`, `stakeholder-register.md`, `raci-matrix.md`, `communication-plan.md`, `docs/change-log.md` baseline entry. |
| **2. Requirements** | `prompts/phase-02-requirements/` | Signed-off Phase 1 artefacts, discovery notes, regulatory library. | Drafts BRD, PRD, SRS, NFR, RTM; decomposes backlog into epics/features/stories/tasks under `backlog/`; updates RTM links. | Product Steering Committee validates prioritisation and accepts NFR thresholds. | `docs/requirements/*.md`, `backlog/epics/`, `backlog/features/`, `backlog/stories/`, `backlog/tasks/`, updated `RTM.md`. |
| **3. Design** | `prompts/phase-03-design/` | Requirements baseline, RTM IDs, architecture principles. | Produces HLD, LLD components, API specs, data architecture, threat model, diagrams. | Enterprise Architecture board approves tech stack and integration approach; Security Officer reviews threat model. | `docs/design/HLD.md`, `docs/design/LLD/*.md`, `docs/design/api-specs/*.md`, `docs/design/data-architecture.md`, `docs/design/threat-model.md`, diagrams in `docs/diagrams/`. |
| **4. Development Enablement** | `prompts/phase-04-development/` | Design artefacts, backlog, security requirements. | Creates coding standards, iteration plan, CI/CD spec, environment matrix, SBOM strategy, task readiness log; engineers refine tasks. | DevOps lead provisions runners/secrets; Engineering lead resolves open questions in `task-readiness.md`. | `docs/development/*.md`, updated backlog tasks, `docs/development/task-readiness.md`. |
| **5. Testing & QA** | `prompts/phase-05-testing/` | Readiness log, RTM, NFR targets. | Builds master test plan, test suites (functional, integration, security, performance), test data strategy, defect management process. | QA leadership approves coverage; compliance officer okays data usage for testing. | `docs/testing/TestPlan.md`, `docs/testing/test-data-strategy.md`, `docs/testing/defect-management-process.md`, test suite catalog in `tests/`. |
| **6. Release & Deployment** | `prompts/phase-06-release/` | Test evidence, go/no-go criteria, CI/CD spec. | Drafts deployment runbook, rollback plan, release notes, go/no-go checklist, support readiness pack. | CAB approves runbook; Ops lead validates rollback drills. | `docs/release/deployment-runbook.md`, `docs/release/ReleaseNotes.md`, `docs/release/RollbackPlan.md`, `docs/release/go-no-go-checklist.md`. |
| **7. Operations & Improvement** | `prompts/phase-07-operations/` | Production telemetry, incident playbooks, customer feedback. | Documents incident response plan, observability status, RCA template, retrospective agenda; feeds continuous improvement backlog. | Support manager confirms on-call rotations; Product Owner reviews improvement backlog monthly. | `docs/operations/*.md`, backlog improvement stories, updated RTM & change log. |

---

## 4. Sample Traceability Snapshot

| RTM ID | Requirement Summary | Design Link | Backlog Link | Test Coverage | Release Artefact |
|--------|---------------------|-------------|--------------|---------------|------------------|
| RTM-FR-001 | "System shall ingest CAN telemetry every 30s." | `docs/design/LLD/telemetry-ingest.md` | `backlog/epics/EP-0003-telemetry.md` → `backlog/stories/US-1024.md` → `backlog/tasks/TSK-3101.md` | `tests/functional/telemetry-intake-suite.md` | `docs/release/deployment-runbook.md` §3.2 |
| RTM-NFR-005 | "p95 API latency ≤ 250ms." | `docs/design/HLD.md` §5.1 | `backlog/tasks/TSK-3140-perf-tuning.md` | `tests/performance/api-latency-suite.md` | `docs/release/go-no-go-checklist.md` Item 7 |
| RTM-SEC-011 | "Support ISO 27001 Annex A logging." | `docs/design/threat-model.md` §4.4 | `backlog/tasks/TSK-3205-log-hardening.md` | `tests/security/logging-controls-suite.md` | `docs/operations/observability-status.md` §2 |

---

## 5. Change Log & Decision Capture (Excerpt)

| Entry ID | Date | Description | Owner | Status | Next Review |
|----------|------|-------------|-------|--------|-------------|
| CL-2025-045 | 2025-11-07 | Approved telemetry vendor SDK for MVP scope; update security review schedule. | Security Officer | Open | 2025-11-14 |
| CL-2025-046 | 2025-11-10 | Baseline backlog EP-0001 to EP-0005; freeze for iteration planning. | Product Owner | Closed | — |

All new decisions discovered during phase execution must be appended to `docs/change-log.md` and linked in relevant artefacts.

---

## 6. Practical Workflow Tips

1. **Front-load Context:** Spend the first workshop curating the intake package. The richer the initial data, the fewer manual interventions later.
2. **Automate File Naming:** Use consistent IDs (e.g., `EP-0003`, `US-1024`) so agents, RTM, and release docs stay aligned.
3. **Parallel Processing:** Once Phase 2 backlog is published, you can run Phase 3 design prompts in parallel for different domains (telemetry, charging) while keeping RTM updated.
4. **Weekly Governance Sync:** Review change log, RTM diffs, and backlog updates with cross-functional leads; trigger re-generation only for impacted artefacts.
5. **Secure Secrets Off-Repo:** When agents flag environment or credential needs, store values in your secret manager and reference procedures in documentation.
6. **Continuous Validation:** After each prompt run, tick off the contribution checklist in README and ensure approvals are captured inside the generated template tables.

---

## 7. Go-Live Readiness Checklist (Condensed)

- [ ] All RTM entries link through design, implementation, and test artefacts.
- [ ] NFR targets validated with performance/security evidence.
- [ ] Deployment runbook and rollback plan rehearsed with ops team.
- [ ] Support readiness package delivered and acknowledged.
- [ ] Post-launch monitoring dashboards configured and alert thresholds agreed.
- [ ] Improvement backlog seeded with post-MVP candidates.

---

## 8. Post-Launch Continuous Improvement

- Run the Phase 7 retrospective agenda quarterly to capture learnings.
- Feed production incidents into `docs/operations/rca-template.md` and translate actions into backlog tasks.
- Refresh NFR baselines annually or when customer geography/regulatory context changes.
- Schedule architecture fitness reviews every two releases and update HLD/LLDs as needed.

This example demonstrates how a greenfield programme can leverage the AI-SDLC workspace end-to-end while maintaining auditable traceability, compliance, and stakeholder alignment.
