# AI-SDLC Workspace

The AI-SDLC repository hosts an enterprise-grade documentation system for managing the entire software development life cycle with the help of autonomous AI agents. Every phase from inception to operations is represented by:

- **Production-ready templates** stored under ` templates/`
- **Persona-specific prompts** housed under `prompts/phase-xx-*`
- **Governance guides** that enforce traceability, compliance, and review discipline

Use this README as the north star for orchestrating artefact creation, review, and lifecycle management.

---

## Quick start for contributors

1. **Read `AGENTS.md`** to internalise operating rules before engaging in any phase.
2. **Review existing artefacts** in `docs/`, `backlog/`, and `tests/` to avoid duplication and understand context.
3. **Launch prompts phase by phase** (see table below) and allow agents to clone the corresponding templates into the correct location.
4. **Update `docs/change-log.md`** whenever a baseline, decision, or dependency shifts.
5. **Keep the Requirements Traceability Matrix (`docs/requirements/RTM.md`) current**. It is the single source of truth linking requirements to design, build, test, and operational evidence.
6. **Confirm approvals** using the tables embedded in each template before marking a deliverable complete.

---

## Repository map

| Path | Purpose |
|------|---------|
| ` templates/` | Canonical templates referenced by all prompts (note the leading space in the directory name). |
| `prompts/` | AI prompts organised by SDLC phase and persona (`phase-01-inception` … `phase-07-operations`). |
| `docs/` | Generated artefacts per phase (requirements, design, testing, release, operations). |
| `backlog/` | Epics, features, stories, tasks, and improvement items created from Phase 2 onwards. |
| `tests/` | Functional, automation, performance, and security test suites defined in Phase 5. |
| `AGENTS.md` | Mandatory operating handbook for all AI agents working in this workspace. |

---

## SDLC automation workflow

| Phase | Primary Personas & Prompt Folder | Key Deliverables (target paths) | Must Exist Before |
|-------|----------------------------------|----------------------------------|-------------------|
| 1. Inception | `prompts/phase-01-inception/` | `docs/inception/business-case.md`, `docs/inception/vision-and-goals.md`, stakeholder register, RACI, communication plan, `docs/change-log.md` | Opportunity / idea intake |
| 2. Requirements | `prompts/phase-02-requirements/` | `docs/requirements/BRD.md`, `docs/requirements/PRD.md`, `docs/requirements/SRS.md`, `docs/requirements/NFR.md`, `docs/requirements/RTM.md`, backlog hierarchy (`backlog/`) | Phase 1 artefacts approved |
| 3. Design | `prompts/phase-03-design/` | `docs/design/HLD.md`, `docs/design/LLD/<component>.md`, `docs/design/threat-model.md`, `docs/design/api-specs/`, `docs/design/data-architecture.md` | Requirements baseline and RTM |
| 4. Development Enablement | `prompts/phase-04-development/` | `docs/development/coding-standards.md`, iteration plan, CI/CD spec, environment matrix, SBOM strategy, task readiness log | HLD, backlog, and security design |
| 5. Testing & QA | `prompts/phase-05-testing/` | `docs/testing/TestPlan.md`, detailed test suites under `tests/`, `docs/testing/test-data-strategy.md` | Design and development readiness |
| 6. Release & Deployment | `prompts/phase-06-release/` | `docs/release/deployment-runbook.md`, `docs/release/go-no-go-checklist.md`, `docs/release/RollbackPlan.md`, `docs/release/ReleaseNotes.md`, support readiness checklist | Test evidence and approvals |
| 7. Operations & Improvement | `prompts/phase-07-operations/` | `docs/operations/incident-response.md`, `docs/operations/observability-status.md`, `docs/operations/rca-template.md`, `docs/operations/retrospective-agenda.md`, improvement backlog updates | Release artefacts and telemetry hooks |

> **Parallelisation:** Prompts marked as parallel in their instructions may run concurrently, but the RTM and change log must be updated before closing any deliverable.

---

## User input readiness guide

Agents can only automate downstream documentation if the right context is supplied up front. Aim to provide the full intake bundle below before starting Phase 1; the remaining touchpoints capture the few moments where manual confirmation is still required.

### Intake bundle to provide before Phase 1 kicks off

- **Business context:** Opportunity statement, success metrics/KPIs, desired business outcomes, and any hard deadlines.
- **Stakeholder universe:** Names, roles, decision authority, contact cadence, escalation path, and availability for reviews.
- **Scope framework:** In-scope vs. out-of-scope capabilities, core user journeys, assumptions, dependencies, and known constraints (budget, geography, licensing, vendor lock-ins).
- **Compliance posture:** Regulatory regimes (e.g., GDPR, PCI, HIPAA), privacy classifications, audit obligations, and security posture requirements.
- **Current-state landscape:** Existing systems, integrations, data sources, interface contracts, and technology guardrails set by enterprise architecture.
- **User and market insights:** Personas, usage scenarios, competitive research, market differentiation goals, accessibility expectations.
- **Delivery policies:** Funding model, release cadence targets, change-approval process, service-level objectives (SLOs), availability, performance, and accessibility thresholds.
- **Operational readiness inputs:** Support model expectations, monitoring/observability tool stack, incident escalation policies, and disaster-recovery mandates.
- **Access logistics:** Points of contact for environments, credential provisioning workflows, and location of authoritative reference material (wikis, RFCs, vendor docs).

Providing this package upfront allows agents across every phase to execute without pausing for clarifications.

### Phase-specific touchpoints where manual input is still required

| Phase | Why agents still need you | Manual input required | Ideal timing |
|-------|---------------------------|-----------------------|--------------|
| 1. Inception | Resolve open questions that arise while drafting the business case and governance artefacts. | Clarify ambiguous objectives, confirm stakeholder commitments, approve initial change-log entries. | During initial prompt run; respond within 1 business day. |
| 2. Requirements | Validate prioritisation and legal/compliance interpretations that cannot be inferred from intake data. | Approve story prioritisation, confirm acceptance criteria sign-off, supply data classification matrices, endorse RTM numbering scheme. | Immediately after BRD/PRD drafts are produced. |
| 3. Design | Align technical decisions with enterprise standards and integration owners. | Confirm approved tech stack, supply vetted reference architectures, share integration credentials/protocol specs that cannot reside in source control, provide security review outcomes. | Before HLD sign-off and prior to creating LLD/API specs. |
| 4. Development Enablement | Unlock delivery tooling and secrets the agents cannot provision autonomously. | Provide repository or package registry access, CI/CD runner credentials, environment provisioning approvals, third-party license confirmations. | As soon as Phase 4 prompts begin so iteration planning can proceed. |
| 5. Testing & QA | Authorise regulated data usage and finalise go/no-go criteria for quality gates. | Approve use of production-like datasets or synthetic data plans, confirm required compliance evidence, designate test environments and SLAs for defect turnaround. | Prior to freezing the master Test Plan and test data strategy. |
| 6. Release & Deployment | Interface with organisational change management and operations leads. | Provide CAB approvals, lock production release windows, nominate on-call responders, supply rollback validation proof from dry runs. | At least one release cycle ahead of deployment to avoid schedule slips. |
| 7. Operations & Improvement | Feed real-world telemetry and business outcomes back into the automation loop. | Share live SLI/SLO dashboards, incident postmortems, customer satisfaction metrics, and prioritised improvement backlog entries. | On a recurring cadence post-release (e.g., monthly or per incident). |

Outside these checkpoints, the agents operate autonomously using the supplied templates, prompts, and governance artefacts. Update the intake bundle whenever business priorities shift so downstream phases remain in sync.

---

## Template inventory

| Template (under ` templates/`) | Primary Deliverable | Prompt Phase |
|--------------------------------|---------------------|--------------|
| `BRD.md` | `docs/requirements/BRD.md` | Phase 2.1 – Product Manager |
| `PRD.md` | `docs/requirements/PRD.md` | Phase 2.1 – Product Manager |
| `SRS.md` | `docs/requirements/SRS.md` | Phase 2.2 – Systems Analyst |
| `NFR.md` | `docs/requirements/NFR.md` | Phase 2.3 – Product Operations |
| `RTM.md` | `docs/requirements/RTM.md` | Phase 2.2 – Systems Analyst |
| `EPIC.md`, `Feature.md`, `Story.md`, `Task.md` | Backlog artefacts (`backlog/`) | Phase 2.3 – Product Operations |
| `HLD.md` | `docs/design/HLD.md` | Phase 3.1 – Solution Architect |
| `LLD.md` | `docs/design/LLD/<component>.md` | Phase 3.1 – Solution Architect |
| `TestPlan.md` | `docs/testing/TestPlan.md` | Phase 5.1 – QA/Test Lead |
| `ReleaseNotes.md` | `docs/release/ReleaseNotes.md` | Phase 6.2 – Change Manager |
| `RollbackPlan.md` | `docs/release/RollbackPlan.md` | Phase 6.2 – Change Manager |

All prompts assume these templates remain unchanged. Update templates thoughtfully and note changes in the change log to keep downstream automation consistent.

---

## Governance & quality guardrails

- **Traceability first:** Every requirement, design component, test case, and operational control must link back to RTM identifiers.
- **Change management:** Maintain `docs/change-log.md` for approvals, baselines, open questions, and risk decisions across phases.
- **Approvals & versioning:** Use the tables embedded in each template to capture reviewer sign-off and document version history.
- **Compliance alignment:** Ensure security, privacy, accessibility, and regulatory constraints are satisfied in BRD, NFR, design, and release artefacts.
- **Documentation consistency:** Keep terminology, IDs, and references uniform. If a concept changes, cascade updates through dependent artefacts.

---

## Contribution checklist

Before concluding any task:

- [ ] All referenced templates were cloned from ` templates/` and populated without placeholders.
- [ ] RTM entries and the change log reflect new or modified work.
- [ ] Stakeholder approvals or follow-up actions are recorded with owners and due dates.
- [ ] Parallel teams (architecture, engineering, QA, release, operations) have been notified of dependencies or impacts.

---

## Additional resources

- **Operating handbook:** `AGENTS.md`
- **Prompt catalogue:** `prompts/SDLC_AI_Agent_Prompts.md`
- **Historical templates:** `templates-old/` (for reference only; do not reuse without review).

Use these resources together to deliver audit-ready SDLC documentation with predictable quality and full lifecycle traceability.
