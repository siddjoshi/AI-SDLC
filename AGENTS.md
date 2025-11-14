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
- **Templates:**
   - ` templates/BRD.md`
   - ` templates/PRD.md`
   - ` templates/SRS.md`
   - ` templates/NFR.md`
   - ` templates/RTM.md`
   - Backlog templates: ` templates/Epic.md`, ` templates/Feature.md`, ` templates/Story.md`, ` templates/Task.md`
- **Primary outputs:** place under `docs/requirements/` and `backlog/`.
- **Must do:**
   - Populate BRD, then PRD, then SRS/NFR to ensure traceability.
   - Update `docs/requirements/RTM.md` with unique IDs, linking every requirement to Phase 1 goals.
   - Create backlog hierarchy in `backlog/` using provided templates; maintain cross-references to RTM IDs.

### Phase 3 – Architecture & Design
- **Prompt folder:** `prompts/phase-03-design/`
- **Templates:** ` templates/HLD.md`, ` templates/LLD.md`, plus ad-hoc specs for APIs, data, and security.
- **Primary outputs:**
   - `docs/design/HLD.md`
   - Component-level LLD files in `docs/design/LLD/`
   - `docs/design/api-specs/` (one file per interface)
   - `docs/design/data-architecture.md`
   - `docs/design/threat-model.md`
- **Supplementary diagrams:** Save C4 or UML diagrams under `docs/diagrams/` (system-context, container, component, deployment, data-flow, sequence). Ensure diagram IDs match HLD sections.
- **Governance:** For every architecture decision, create or update an ADR section within the HLD template and reference it from the change log if it affects scope or risk.

### Phase 4 – Development Enablement
- **Prompt folder:** `prompts/phase-04-development/`
- **Outputs:**
   - `docs/development/coding-standards.md`
   - `docs/development/iteration-plan.md`
   - `docs/development/ci-cd-spec.md`
   - `docs/development/environment-matrix.md`
   - SBOM & dependency tracking approach under `docs/development/sbom-strategy.md`
- **Key actions:** Confirm each story/task from Phase 2 has acceptance criteria and link them in the RTM before declaring development-ready. Coordinate with security and compliance requirements documented in Phase 3.

### Phase 5 – Testing & Quality Assurance
- **Prompt folder:** `prompts/phase-05-testing/`
- **Templates:** ` templates/TestPlan.md`
- **Outputs:**
   - `docs/testing/TestPlan.md`
   - Test suites and scripts under `tests/` (documentation, not executable code)
   - `docs/testing/test-data-strategy.md`
   - `docs/testing/defect-management-process.md`
- **Traceability:** Add RTM references for every test case. Capture entry/exit criteria, environments, and tooling. Document how non-functional targets from `docs/requirements/NFR.md` will be validated.

### Phase 6 – Release & Deployment
- **Prompt folder:** `prompts/phase-06-release/`
- **Templates:** ` templates/ReleaseNotes.md`, ` templates/RollbackPlan.md`
- **Outputs:**
   - `docs/release/deployment-runbook.md`
   - `docs/release/ReleaseNotes.md`
   - `docs/release/RollbackPlan.md`
   - `docs/release/go-no-go-checklist.md`
- **Key actions:** Align the runbook with the CI/CD spec from Phase 4, note dependencies, approvals, and rollback validation evidence. Update change log with deployment decision and sign-offs.

### Phase 7 – Operations, Monitoring & Improvement
- **Prompt folder:** `prompts/phase-07-operations/`
- **Outputs:**
   - `docs/operations/incident-response.md`
   - `docs/operations/observability-status.md`
   - `docs/operations/rca-template.md`
   - `docs/operations/retrospective-agenda.md`
   - Continuous improvement backlog updates under `backlog/`
- **Key actions:** Capture SLIs/SLOs, on-call rotations, and post-release learnings. Feed improvement stories into the backlog with clear RTM links.

## Cross-Phase Governance Checklist

- [ ] **Traceability:** RTM updated with design, test, and release column entries for every requirement.
- [ ] **Change log:** Latest decisions, risks, assumptions, and dependencies recorded with status and owner.
- [ ] **Approvals:** Each deliverable includes reviewer/approver names, roles, and timestamps.
- [ ] **Compliance:** Security, privacy, accessibility, and regulatory requirements satisfied in BRD, NFR, design, testing, and release artefacts.
- [ ] **Versioning:** Document headers include version, date, author, and change history aligned with the change log.
- [ ] **Consistency:** Terminology, IDs, and references synchronised across docs, backlog, tests, and diagrams.

## Operating Playbook

1. **Prepare:** Read existing artefacts to understand context and avoid duplicating work. If information is missing, log questions in the change log before proceeding.
2. **Execute:** Clone the relevant template(s), populate all sections (no placeholders), and ensure alignment with upstream phases.
3. **Validate:** Run through the phase-specific prompt checklist plus the cross-phase checklist above. Cross-reference RTM IDs and confirm approvals.
4. **Communicate:** Document stakeholder feedback, open issues, and next steps in both the deliverable and the change log. Notify subsequent phases of dependencies.
5. **Close:** Ensure the RTM and change log are accurate, archive interim notes, and confirm the README workflow table still reflects your outputs.

## Reference Materials

- **Templates:** ` templates/`
- **Prompts catalogue:** `prompts/SDLC_AI_Agent_Prompts.md`
- **Historical templates:** `templates-old/` (for reference only; do not copy without approval)
- **Traceability hub:** `docs/requirements/RTM.md`
- **Governance register:** `docs/change-log.md`

Stay disciplined, keep the audit trail pristine, and deliver documentation that enables seamless progression through the AI-driven SDLC.
