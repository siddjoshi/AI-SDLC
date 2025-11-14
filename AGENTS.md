# Agent Operating Handbook for the AI-SDLC Workspace (Documentation Only)
## sample change
## Mission & Guardrails

- Produce **documentation only** in Markdown. 
- Every artefact must trace back to a documented requirement. Maintain the Requirements Traceability Matrix (RTM) throughout.
- Update `docs/change-log.md` for new baselines, decisions, open risks, or deviations.
- Use templates exclusively from the ` templates/` directory (note the leading space). Do not reuse files from `templates-old/`.
- Record approvers, reviewers, and version history using the tables embedded in each template.
- Keep terminology, IDs, and references aligned across all documents and prompts.

## Phase-by-Phase Execution

For each phase, run the corresponding prompts under `prompts/phase-0x-*`. Before starting a phase, confirm all prerequisite deliverables are signed off. Create folders under `docs/`, `backlog/`, or `tests/` if they do not already exist.

### Phase 1 – Inception & Governance Setup
- **Prompt folder:** `prompts/phase-01-inception/`
- **Templates:** ` templates/business-case.md`, ` templates/vision-and-goals.md`, ` templates/stakeholder-register.md`, ` templates/raci-matrix.md`, ` templates/communication-plan.md`
- **Primary outputs:**
   - `docs/inception/business-case.md`
   - `docs/inception/vision-and-goals.md`
   - `docs/inception/stakeholder-register.md`
   - `docs/inception/raci-matrix.md`
   - `docs/inception/communication-plan.md`
   - `docs/change-log.md` (baseline entry)
- **Key actions:** capture KPIs, stakeholders, or constraints; record all open questions in the change log with owners and due dates.

### Phase 2 – Requirements & Backlog
- **Prompt folder:** `prompts/phase-02-requirements/`
- **Prompts:** `01-product-manager.md`, `02-systems-analyst.md`, `03-product-operations.md`, `03b-nfr-specialist.md`
- **Templates:**
   - ` templates/BRD.md`
   - ` templates/PRD.md`
   - ` templates/SRS.md`
   - ` templates/NFR.md`
   - ` templates/RTM.md` (enhanced with Jira/ADO integration and automation guidance)
   - Backlog templates: ` templates/Epic.md`, ` templates/Feature.md`, ` templates/Story.md`, ` templates/Task.md`
- **Primary outputs:** place under `docs/requirements/` and `backlog/`.
- **Must do:**
   - Populate BRD, then PRD, then SRS using systems analyst prompt
   - Use NFR Specialist prompt (03b) to generate comprehensive NFR.md covering performance, security, scalability, availability, usability, maintainability
   - Update `docs/requirements/RTM.md` with unique IDs, linking every requirement to Phase 1 goals
   - Configure RTM tool integration (Jira/Azure DevOps) for bidirectional sync
   - Create backlog hierarchy in `backlog/` using provided templates; maintain cross-references to RTM IDs.

### Phase 3 – Architecture & Design
- **Prompt folder:** `prompts/phase-03-design/`
- **Templates:** ` templates/HLD.md`, ` templates/LLD.md`, ` templates/threat-model.md`, ` templates/data-architecture.md`, ` templates/api-spec-template.md`, ` templates/ADR.md`
- **Primary outputs:**
   - `docs/design/HLD.md`
   - Component-level LLD files in `docs/design/LLD/`
   - `docs/design/api-specs/` (one file per interface using api-spec-template.md)
   - `docs/design/data-architecture.md` (comprehensive data model, lineage, governance, security)
   - `docs/design/threat-model.md` (STRIDE analysis, OWASP Top 10, security controls)
   - `docs/design/ADRs/` (Architecture Decision Records for major decisions)
- **Supplementary diagrams:** Save C4 or UML diagrams under `docs/diagrams/` (system-context, container, component, deployment, data-flow, sequence). Ensure diagram IDs match HLD sections.
- **Governance:** For every architecture decision, create an ADR using ` templates/ADR.md` and reference it from the HLD and change log if it affects scope or risk.

### Phase 4 – Development Enablement
- **Prompt folder:** `prompts/phase-04-development/`
- **Templates:** ` templates/coding-standards.md`, ` templates/ci-cd-spec.md`, ` templates/environment-matrix.md`, ` templates/iteration-plan.md`, ` templates/sbom-strategy.md`
- **Outputs:**
   - `docs/development/coding-standards.md` (language-specific standards, security practices, OWASP compliance)
   - `docs/development/iteration-plan.md` (sprint planning, velocity, DoR/DoD)
   - `docs/development/ci-cd-spec.md` (pipeline stages, quality gates, deployment strategies)
   - `docs/development/environment-matrix.md` (dev/test/staging/prod configuration)
   - `docs/development/sbom-strategy.md` (SPDX/CycloneDX, vulnerability management)
- **Key actions:** Confirm each story/task from Phase 2 has acceptance criteria and link them in the RTM before declaring development-ready. Coordinate with security and compliance requirements documented in Phase 3.

### Phase 5 – Testing & Quality Assurance
- **Prompt folder:** `prompts/phase-05-testing/`
- **Templates:** ` templates/TestPlan.md`, ` templates/test-data-strategy.md`, ` templates/defect-management-process.md`, ` templates/test-case-template.md`, ` templates/test-coverage-matrix.md`
- **Outputs:**
   - `docs/testing/TestPlan.md`
   - Test suites and scripts under `tests/` (documentation, not executable code)
   - `docs/testing/test-data-strategy.md` (synthetic data, anonymization, refresh)
   - `docs/testing/defect-management-process.md` (triage, severity, lifecycle)
   - `docs/testing/test-coverage-matrix.md` (requirements → test cases mapping)
- **Traceability:** Add RTM references for every test case. Capture entry/exit criteria, environments, and tooling. Document how non-functional targets from `docs/requirements/NFR.md` will be validated.

### Phase 6 – Release & Deployment
- **Prompt folder:** `prompts/phase-06-release/`
- **Templates:** ` templates/ReleaseNotes.md`, ` templates/RollbackPlan.md`, ` templates/deployment-runbook.md`, ` templates/go-no-go-checklist.md`, ` templates/support-readiness-checklist.md`
- **Outputs:**
   - `docs/release/deployment-runbook.md` (step-by-step deployment procedures)
   - `docs/release/ReleaseNotes.md`
   - `docs/release/RollbackPlan.md`
   - `docs/release/go-no-go-checklist.md` (readiness criteria, approvals)
   - `docs/release/support-readiness-checklist.md` (training, documentation, on-call)
- **Key actions:** Align the runbook with the CI/CD spec from Phase 4, note dependencies, approvals, and rollback validation evidence. Update change log with deployment decision and sign-offs.

### Phase 7 – Operations, Monitoring & Improvement
- **Prompt folder:** `prompts/phase-07-operations/`
- **Templates:** ` templates/incident-response.md`, ` templates/observability-status.md`, ` templates/rca-template.md`, ` templates/retrospective-agenda.md`
- **Outputs:**
   - `docs/operations/incident-response.md` (playbooks, escalation, communication)
   - `docs/operations/observability-status.md` (SLIs/SLOs, dashboards, alerts)
   - `docs/operations/rca-template.md` (root cause analysis, 5 whys, action items)
   - `docs/operations/retrospective-agenda.md` (continuous improvement ceremonies)
   - Continuous improvement backlog updates under `backlog/`
- **Key actions:** Capture SLIs/SLOs, on-call rotations, and post-release learnings. Feed improvement stories into the backlog with clear RTM links.

## Cross-Phase Governance Checklist

- [ ] **Traceability:** RTM updated with design, test, and release column entries for every requirement.
- [ ] **Change log:** Latest decisions, risks, assumptions, and dependencies recorded with status and owner.
- [ ] **Approvals:** Each deliverable includes reviewer/approver names, roles, and timestamps.
- [ ] **Compliance:** Security, privacy, accessibility, and regulatory requirements satisfied in BRD, NFR, design, testing, and release artefacts.
- [ ] **Versioning:** Document headers include version, date, author, and change history aligned with the change log.
- [ ] **Consistency:** Terminology, IDs, and references synchronised across docs, backlog, tests, and diagrams.

## Phase Gates & Quality Criteria

**Template:** ` templates/phase-gates.md`

Each phase transition requires formal gate approval based on entry/exit criteria. Use the phase-gates template to document:
- **Entry Criteria:** Prerequisites to begin the phase (e.g., Phase 2 requires approved Business Case from Phase 1)
- **Exit Criteria:** Deliverables, quality metrics, and approvals required to proceed (e.g., Phase 3 requires HLD approval, threat model sign-off)
- **Quality Gates:** Automated and manual checks (e.g., RTM coverage >95%, all critical risks mitigated)
- **Go/No-Go Decision:** Formal approval from steering committee or governance board

**Phase Gate Reviews:**
- Phase 1 → 2: Business case approved, stakeholders aligned, governance established
- Phase 2 → 3: Requirements baselined, RTM complete, backlog created
- Phase 3 → 4: Architecture approved, ADRs documented, security review complete
- Phase 4 → 5: Code complete, CI/CD operational, SBOM generated
- Phase 5 → 6: All tests passed, defects resolved, UAT sign-off
- Phase 6 → 7: Production deployment successful, rollback validated, support trained
- Ongoing Operations: SLAs met, incidents managed, continuous improvement active

## Operating Playbook

1. **Prepare:** Read existing artefacts to understand context and avoid duplicating work. If information is missing, log questions in the change log before proceeding.
2. **Execute:** Clone the relevant template(s), populate all sections (no placeholders), and ensure alignment with upstream phases.
3. **Validate:** Run through the phase-specific prompt checklist plus the cross-phase checklist above. Cross-reference RTM IDs and confirm approvals.
4. **Communicate:** Document stakeholder feedback, open issues, and next steps in both the deliverable and the change log. Notify subsequent phases of dependencies.
5. **Close:** Ensure the RTM and change log are accurate, archive interim notes, and confirm the README workflow table still reflects your outputs.

## Reference Materials

- **Templates:** ` templates/` (includes 26 comprehensive templates across all phases)
- **Prompts catalogue:** `prompts/SDLC_AI_Agent_Prompts.md`
- **Historical templates:** `templates-old/` (for reference only; do not copy without approval)
- **Traceability hub:** `docs/requirements/RTM.md` (with Jira/ADO integration guidance)
- **Governance register:** `docs/change-log.md`
- **Phase gates:** ` templates/phase-gates.md`

Stay disciplined, keep the audit trail pristine, and deliver documentation that enables seamless progression through the AI-driven SDLC.
