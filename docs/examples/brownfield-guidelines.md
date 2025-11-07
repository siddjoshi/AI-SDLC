# Brownfield SDLC Adaptation Guidelines

| Field | Value |
|-------|-------|
| Document ID | EX-BF-001 |
| Version | 0.1 |
| Date | 2025-11-05 |
| Author | AI SDLC Agent |
| Reviewed By | _TBD_ |
| Status | Draft |

## 1. Purpose

These guidelines tailor the AI-SDLC workflow for projects enhancing or modernising an existing product line. Brownfield initiatives must reconcile legacy context, operational constraints, and customer continuity while still taking advantage of autonomous documentation across the SDLC.

---

## 2. Intake Enhancements for Brownfield Work

Provide the standard greenfield intake package **plus** the following:

| Area | Additional Inputs Needed |
|------|--------------------------|
| Current-State Artefacts | Legacy architecture diagrams, SOPs, existing RTM/backlog, historical change logs, known technical debt register. |
| Operational SLAs | Live SLO dashboards, incident metrics, maintenance windows, compliance attestations, customer commitments. |
| Data & Integration Constraints | Data classification matrix, migration plans, interface compatibility requirements, ref data ownership. |
| Release Cadence | Blackout periods, customer contract obligations, regional rollout restrictions. |
| Risk & Debt Inventory | Security findings, outstanding audit actions, vendor dependencies, capacity limitations. |
| Stakeholder Map | Include support teams, customer success, legacy product owners, and key accounts impacted by change. |

Log gaps or missing artefacts as open questions in the change log before proceeding.

---

## 3. Phase Adjustments

### Phase 1 – Inception
- Update the business case to include cost of change, refactoring ROI, and customer impact mitigation plans.
- Vision and goals must account for technical debt reduction targets (e.g., “retire monolith service X by Q4”).

### Phase 2 – Requirements & Backlog
- BRD/PRD should differentiate between **enhancements**, **deprecations**, and **remediations**.
- SRS must capture compatibility requirements (API versioning, schema changes).
- When generating backlog artefacts:
  - Tag epics/stories with legacy touchpoints (e.g., `LegacyComponent: payments-gateway-v2`).
  - Include migration and regression tasks explicitly in `templates/Task.md` outputs.
- RTM should link to both new requirements and legacy obligations.

### Phase 3 – Design
- HLD/LLD must document coexistence strategy (parallel run, strangler pattern, feature toggles).
- Threat model should include legacy vulnerabilities and compensating controls.
- Capture data migration sequencing and rollback strategy in design artefacts.

### Phase 4 – Development Enablement
- Iteration plan should alternate between feature delivery and remediation waves to limit customer disruption.
- CI/CD spec must address dual pipelines (legacy + modernised). Include automated regression triggers.
- Task readiness should highlight prerequisites such as environment clones, data anonymisation, or legacy access credentials.

### Phase 5 – Testing & QA
- Test plan must combine new feature coverage with regression packs for legacy flows.
- Test data strategy should provide masked production datasets to validate backward compatibility.
- Defect process must define severity thresholds for regressions vs net-new defects.

### Phase 6 – Release & Deployment
- Deployment runbook needs explicit fallback procedures to legacy components and smoke test scripts for critical journeys.
- Go/no-go checklist must include stakeholder notifications (support, customer success) and contract compliance checks.
- Release notes should flag customer-facing behaviour changes with mitigation steps.

### Phase 7 – Operations & Improvement
- Observability updates should reflect new telemetry alongside legacy monitoring to ensure end-to-end visibility.
- Incident response must include joint playbooks until legacy components are retired.
- Feed technical debt burn-down and customer feedback into the continuous improvement backlog.

---

## 4. Additional Governance Controls

| Control | Description | Owner | Artefact |
|---------|-------------|-------|---------|
| Coexistence Register | Track systems/features running in parallel and their sunset dates. | Architecture Lead | `docs/operations/observability-status.md` appendix |
| Migration Readiness Checklist | Validate data integrity, user communications, support training before switching traffic. | Product Owner | `docs/release/deployment-runbook.md` section |
| Regression Coverage Matrix | Map legacy features to regression suites and automation packs. | QA Lead | `docs/testing/TestPlan.md` annex |
| Customer Commitment Tracker | Log SLAs, contractual obligations, and blackout periods. | Customer Success Manager | `docs/change-log.md` references |

---

## 5. Brownfield Best Practices

1. **Prioritise Risk:** Rank backlog items by customer impact and technical risk; ensure high-risk migrations have dedicated rehearsal tasks.
2. **Leverage Feature Flags:** Use rollout strategies to decouple deployment from release, allowing staged customer exposure.
3. **Automate Regression Early:** Integrate regression suites in CI/CD before new features reach staging.
4. **Communicate Widely:** Provide frequent updates to support teams and key customers; document summaries in the change log.
5. **Track Debt Burn-Down:** Include a section in each epic/story for debt reduction benefits to measure progress.
6. **Post-Change Reviews:** After each migration wave, run Phase 7 retrospectives to capture lessons and adjust remaining backlog.

---

## 6. Exit Criteria for Modernisation Waves

- [ ] Legacy capability retired or isolated with clear owner.
- [ ] Customer-facing documentation updated and distributed.
- [ ] Support teams trained with new runbooks and escalation paths.
- [ ] Monitoring confirms stability for at least one full business cycle.
- [ ] RTM, change log, and backlog reflect closure of modernisation tasks.

Use these guidelines alongside the standard prompts to ensure brownfield initiatives remain compliant, low-risk, and transparent while benefiting from the AI-SDLC automation.
