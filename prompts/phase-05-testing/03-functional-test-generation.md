# Phase 5.3 – Functional Test Case Generation from BRD (Automated Test Artefact Creation)

## Role Mission
Generate comprehensive, traceability-rich functional test cases directly from the Business Requirements Document (BRD) to ensure every business objective, process, and acceptance criterion is validated through structured testing artefacts.

## Inputs & References
| Source | Location | Purpose |
|--------|----------|---------|
| Business Requirements Document | `docs/requirements/BRD.md` | Extract business objectives, scope, processes, benefits, assumptions, constraints, and acceptance criteria. |
| Product Requirements Document | `docs/requirements/PRD.md` | Supplement BRD with feature details, user journeys, personas, and acceptance criteria where applicable. |
| Software Requirements Specification | `docs/requirements/SRS.md` | Cross-reference functional requirements and system behaviors for completeness. |
| Non-Functional Requirements | `docs/requirements/NFR.md` | Identify testable NFR targets (performance, usability, accessibility) requiring functional validation flows. |
| Requirements Traceability Matrix | `docs/requirements/RTM.md` | Ensure coverage mapping from requirement IDs to test case IDs; identify gaps. |
| Test Plan | `docs/testing/TestPlan.md` | Align with testing scope, approach, environments, data strategy, and quality metrics. |
| Design Artefacts | `docs/design/HLD.md`, `docs/design/LLD/`, `docs/design/api-specs/` | Understand system boundaries, interfaces, data flows, and integration points for test scenario design. |
| Backlog Items | `backlog/epics/`, `backlog/features/`, `backlog/stories/` | Map test cases to epics/features/stories; validate acceptance criteria coverage. |
| Change Log | `docs/change-log.md` | Monitor outstanding risks, clarifications, or scope changes affecting test coverage. |

## Expected Outputs
| Artefact | Destination | Format | Notes |
|----------|-------------|--------|-------|
| Functional Test Case Catalog | `tests/functional/brd-derived-test-cases.md` | Markdown | Comprehensive test case suite with unique IDs, traceability, preconditions, steps, expected results, data needs, execution priority. |
| Test Coverage Matrix | `tests/functional/brd-coverage-matrix.md` | Markdown | Map each BRD objective/process to corresponding test case IDs; highlight coverage gaps. |
| RTM Update | `docs/requirements/RTM.md` | Markdown | Add test case IDs linked to BRD requirement IDs; document validation status and evidence location. |
| Test Data Requirements Register | `tests/functional/test-data-requirements.md` | Markdown | Catalog data prerequisites, sourcing, masking needs, and refresh cadence per test case. |
| Change Log Update | `docs/change-log.md` | Markdown | Record test generation baseline, coverage metrics, risks, dependencies, and review schedule. |

## Procedure

### 1. BRD Analysis & Requirement Extraction
- **Parse BRD Structure:** Extract all sections including executive summary, business objectives, scope (in-scope/out-of-scope), stakeholder requirements, business processes (As-Is/To-Be), functional requirements overview, cost-benefit analysis, timeline, risks, assumptions, constraints, dependencies.
- **Identify Testable Elements:**
  - Business objectives with measurable KPIs (e.g., "Reduce order processing time by 20%")
  - Business processes and workflows (current vs. proposed state transitions)
  - Functional capabilities and features
  - Acceptance criteria embedded in BRD sections
  - Compliance requirements and regulatory obligations
  - Assumptions requiring validation
  - Risk scenarios requiring defensive testing
  - Integration touchpoints with external systems
- **Assign Unique Identifiers:** Map each testable element to BRD section IDs (e.g., BRD-OBJ-01, BRD-PROC-05, BRD-FR-12).

### 2. Test Case Design & Structuring
For each identified testable element, generate structured test cases following this format:

#### Test Case Template Structure
```markdown
### TC-BRD-<NNNN>: <Test Case Title>

**Traceability:**
- BRD Reference: [BRD-OBJ-XX / BRD-PROC-YY / BRD-FR-ZZ]
- PRD Reference: [PRD-FEAT-XX] (if applicable)
- SRS Reference: [SRS-FR-XX] (if applicable)
- Epic/Feature: [EP-XXXX / FE-YYYY]
- Story: [US-ZZZZ]
- RTM Entry: [RTM-FR-XXXX]

**Objective:**
[Clear statement of what business requirement or objective this test validates]

**Test Type:** [Functional / Integration / End-to-End / Regression / Compliance]

**Priority:** [Critical / High / Medium / Low]  
**Execution Approach:** [Manual / Automated / Hybrid]

**Preconditions:**
- [Environment state, configuration, data prerequisites]
- [User roles/permissions required]
- [Dependent systems/services availability]

**Test Data Requirements:**
- [Specific datasets, volumes, characteristics]
- [Data classification (e.g., PII, synthetic, anonymized)]
- [Data sourcing approach and refresh cadence]

**Test Steps:**
| Step # | Action | Expected Result | Notes |
|--------|--------|-----------------|-------|
| 1 | [Detailed action] | [Observable outcome] | [Edge cases, variations] |
| 2 | [Detailed action] | [Observable outcome] | [Edge cases, variations] |
| ... | ... | ... | ... |

**Expected Outcome:**
[Overall pass criteria; how this validates the business requirement]

**Actual Result:**  
[To be completed during test execution]

**Status:** [Not Executed / Pass / Fail / Blocked]  
**Executed By:** [Tester name]  
**Execution Date:** [YYYY-MM-DD]  
**Defect IDs:** [DEF-XXXX] (if applicable)

**Post-Conditions:**
[System state after test completion; cleanup requirements]

**Risk Coverage:**
[Which BRD risk(s) this test mitigates or validates]

**Compliance Mapping:**
[Regulatory/policy requirements validated by this test]

**Notes & Edge Cases:**
- [Boundary conditions]
- [Error scenarios]
- [Alternative flows]
- [Known limitations]
```

### 3. Coverage Category Breakdown
Generate test cases across these categories derived from BRD sections:

#### A. Business Objective Validation Tests
- Map each BRD objective to measurable validation scenarios
- Include KPI threshold tests (e.g., "Verify order processing completes within target time")
- Capture benefit realization tests (e.g., cost savings, efficiency gains)

#### B. Business Process Tests (As-Is → To-Be Validation)
- Document current-state process tests (baseline behavior)
- Create future-state process tests (new workflow validation)
- Include process transition tests (migration, parallel run scenarios)
- Cover exception handling and rollback procedures

#### C. Scope Boundary Tests
- Validate in-scope capabilities are delivered
- Confirm out-of-scope items are correctly excluded
- Test assumption validation scenarios
- Verify constraint adherence (budget, timeline, technical limits)

#### D. Stakeholder Requirement Tests
- Map stakeholder-specific needs to test scenarios
- Include role-based access and permission tests
- Validate communication/notification requirements
- Test reporting and analytics capabilities per stakeholder needs

#### E. Integration & Dependency Tests
- Validate external system interfaces
- Test data exchange with upstream/downstream systems
- Verify dependency resolution (vendor integrations, third-party services)
- Include failure mode tests (graceful degradation, fallback behavior)

#### F. Compliance & Regulatory Tests
- Map regulatory obligations to validation scenarios
- Include audit trail and logging verification
- Test data privacy, retention, and deletion workflows
- Verify security controls and access restrictions

#### G. Risk Mitigation Tests
- Create defensive tests for each identified BRD risk
- Include negative testing for high-impact scenarios
- Test mitigation strategies and contingency plans
- Validate monitoring and alerting for risk indicators

#### H. Acceptance Criteria Tests
- Convert each BRD acceptance criterion into executable test cases
- Include success criteria validation
- Test measurability and observability of acceptance metrics

### 4. Test Coverage Matrix Generation
Create `tests/functional/brd-coverage-matrix.md` with this structure:

```markdown
# BRD Test Coverage Matrix

| BRD Section | BRD ID | Requirement Summary | Test Case IDs | Coverage % | Gaps/Notes | Owner | Status |
|-------------|--------|---------------------|---------------|------------|------------|-------|--------|
| Business Objectives | BRD-OBJ-01 | Reduce processing time by 20% | TC-BRD-0001, TC-BRD-0002 | 100% | — | QA Lead | Covered |
| Business Process | BRD-PROC-05 | Implement automated approval flow | TC-BRD-0045, TC-BRD-0046, TC-BRD-0047 | 100% | — | QA Specialist | Covered |
| Functional Requirements | BRD-FR-12 | Real-time inventory sync | TC-BRD-0089 | 50% | Missing error handling tests | QA Specialist | Partial |
| ... | ... | ... | ... | ... | ... | ... | ... |
```

### 5. Test Data Requirements Cataloging
Document in `tests/functional/test-data-requirements.md`:

```markdown
# Functional Test Data Requirements (BRD-Derived)

| Test Case ID | Data Category | Volume | Characteristics | Source | Masking/Anonymization | Refresh Cadence | Compliance Notes |
|--------------|---------------|--------|-----------------|--------|----------------------|-----------------|------------------|
| TC-BRD-0001 | Order records | 500 | Various states, payment methods | Production clone | PII masked | Weekly | GDPR compliant |
| TC-BRD-0045 | User accounts | 50 | Multi-role, multi-tenant | Synthetic generator | N/A | On-demand | ISO 27001 aligned |
| ... | ... | ... | ... | ... | ... | ... | ... |
```

### 6. RTM Integration & Traceability
- **Update RTM:** For each BRD requirement ID, add corresponding test case IDs in the RTM "Test Coverage" column.
- **Bidirectional Linkage:** Ensure each test case references its originating BRD section/ID; RTM links back to test case location.
- **Gap Identification:** Highlight BRD requirements without test coverage; assign owners and due dates for remediation.
- **Validation Status Tracking:** Use RTM to record test execution status, evidence location, and approval sign-off.

### 7. Prioritization & Execution Sequencing
- **Critical Path Tests:** Identify tests validating high-priority objectives, compliance mandates, or high-risk areas; mark as "Critical" priority.
- **Dependency Ordering:** Sequence tests respecting technical dependencies (e.g., infrastructure setup before integration tests).
- **Automation Candidates:** Flag repetitive, regression-critical, or high-frequency tests for automation framework inclusion.
- **Manual Exploratory Tests:** Identify complex, judgment-intensive, or user-experience-focused scenarios requiring manual execution.

### 8. Quality & Completeness Validation
- **Peer Review:** Engage Product Manager, Systems Analyst, and QA Lead to review test cases for accuracy and BRD alignment.
- **Coverage Metrics:** Calculate percentage coverage per BRD section; target ≥95% for critical objectives/processes.
- **Edge Case Inclusion:** Verify boundary conditions, error paths, and alternative flows are documented.
- **Compliance Verification:** Confirm regulatory/audit requirements have dedicated test cases with evidence capture plans.

### 9. Change Log & Governance
- **Record Baseline:** Log functional test case generation completion, coverage metrics, and review schedule in `docs/change-log.md`.
- **Risk Documentation:** Capture untestable requirements, environment dependencies, or data limitations as risks with mitigation plans.
- **Stakeholder Communication:** Notify Test Lead, Product Manager, Release Manager of test readiness and coverage status per communication plan.
- **Version Control:** Update document control tables in all test artefacts with version, date, author, review/approval stakeholders.

### 10. Continuous Maintenance & Updates
- **BRD Change Tracking:** Monitor `docs/change-log.md` for BRD updates; regenerate or update affected test cases.
- **Test Result Feedback Loop:** Analyze test execution results; refine test cases based on defects, edge cases discovered.
- **Traceability Audits:** Periodically validate RTM accuracy; ensure test case IDs remain synchronized with requirement changes.
- **Regression Suite Evolution:** Promote critical test cases into regression packs; update automation framework as needed.

## Traceability & Governance
- **End-to-End Linkage:** Every test case must reference BRD section ID → PRD/SRS IDs → Epic/Feature/Story → RTM entry → Evidence location.
- **Approval Workflow:** Test cases require QA Lead approval before execution; critical compliance tests need additional stakeholder sign-off.
- **Evidence Management:** Define where test execution evidence (screenshots, logs, reports) will be stored; link locations in RTM.
- **Communication Cadence:** Report coverage metrics, execution progress, and blockers weekly per communication plan.

## Completion Checklist
- [ ] All BRD objectives, processes, and functional requirements have corresponding test cases.
- [ ] Test case catalog (`tests/functional/brd-derived-test-cases.md`) completed with no placeholders.
- [ ] Coverage matrix (`tests/functional/brd-coverage-matrix.md`) shows ≥95% coverage for critical BRD sections.
- [ ] Test data requirements documented with sourcing, masking, and compliance details.
- [ ] RTM updated with bidirectional test case linkage; gaps assigned owners with due dates.
- [ ] Prioritization, execution sequencing, and automation candidates identified.
- [ ] Change log records baseline, metrics, risks, and stakeholder notifications.
- [ ] Peer review completed; approvals captured in document control tables.

## Parallelisation Notes
- Performance and security test generation (Phase 5.2 outputs) can proceed in parallel using NFR and threat model inputs.
- Test automation framework setup can begin once automation candidates are flagged in functional test cases.
- Release planning (Phase 6) can start once test coverage scope and execution sequencing are clear.

## Example Test Case (BRD Objective Validation)

### TC-BRD-0001: Validate 20% Reduction in Order Processing Time

**Traceability:**
- BRD Reference: BRD-OBJ-01 (Reduce order processing time by 20%)
- PRD Reference: PRD-FEAT-05 (Automated approval workflow)
- SRS Reference: SRS-FR-023 (Order status transition automation)
- Epic: EP-0002 (Order Management Modernization)
- Story: US-0156 (Implement automated approval engine)
- RTM Entry: RTM-FR-023

**Objective:**
Verify that the automated approval workflow reduces average order processing time from baseline 120 minutes to target ≤96 minutes (20% reduction).

**Test Type:** End-to-End  
**Priority:** Critical  
**Execution Approach:** Automated (with manual validation for baseline comparison)

**Preconditions:**
- Baseline order processing time measured and documented (120 min average over 100 orders)
- Automated approval engine deployed in test environment
- Test user accounts provisioned with appropriate roles (Submitter, Approver Level 1, Approver Level 2)
- Order management system integrated with approval engine

**Test Data Requirements:**
- 100 representative orders covering various complexity levels, amounts, and approval paths
- User accounts: 5 submitters, 3 Level 1 approvers, 2 Level 2 approvers
- Synthetic order data (no PII) matching production distribution
- Refresh: Weekly from synthetic data generator

**Test Steps:**
| Step # | Action | Expected Result | Notes |
|--------|--------|-----------------|-------|
| 1 | Submit 100 test orders via system interface | Orders enter "Pending Approval" state within 5 seconds | Track submission timestamp |
| 2 | Automated approval engine evaluates orders per business rules | 70% auto-approved within 10 minutes; 30% routed to manual review | Monitor approval logs |
| 3 | Manual approvers process routed orders | All manual approvals complete within 30 minutes | Simulate realistic approver response times |
| 4 | Calculate average processing time from submission to final approval | Average ≤96 minutes (20% improvement over 120 min baseline) | Aggregate timestamps; compare to baseline |
| 5 | Verify no orders stuck in processing or error states | 100% orders reach final state (Approved/Rejected) | Check for timeouts or failures |

**Expected Outcome:**
Average order processing time ≤96 minutes with statistical significance (p<0.05 vs. baseline); confirms BRD-OBJ-01 achievement.

**Actual Result:** [To be completed]  
**Status:** Not Executed  
**Executed By:** [Tester]  
**Execution Date:** [YYYY-MM-DD]  
**Defect IDs:** [If applicable]

**Post-Conditions:**
- Test orders archived or purged per data retention policy
- Approval engine logs captured for analysis
- Performance metrics exported to reporting dashboard

**Risk Coverage:**
Mitigates BRD-RISK-03 (Approval bottlenecks causing customer dissatisfaction)

**Compliance Mapping:**
Audit trail requirements per ISO 9001 (quality management) validated through approval logs

**Notes & Edge Cases:**
- Test edge case: Orders requiring multi-level escalation (longest path)
- Boundary condition: Orders submitted during peak load (concurrent processing)
- Alternative flow: Approver unavailability triggering delegation rules

---

## Quality Standards & Best Practices

1. **Clarity:** Every test case must be executable by any tester without additional context; avoid ambiguous language.
2. **Traceability:** Maintain complete bidirectional linkage from BRD → Test Case → RTM → Evidence.
3. **Measurability:** Acceptance criteria must be quantifiable; use metrics, thresholds, and objective pass/fail criteria.
4. **Maintainability:** Structure test cases for easy updates; use modular approach for reusable test steps.
5. **Compliance:** Ensure regulatory/audit requirements have explicit validation steps with evidence capture.
6. **Risk-Based Prioritization:** Allocate more test cases and edge case coverage to high-risk, high-impact BRD requirements.
7. **Data Privacy:** Never use production PII in test data; document masking/anonymization approach in every test case.
8. **Version Control:** Treat test cases as living documents; update with BRD changes and maintain change history.

---

## Automation & Tool Integration Considerations

- **Test Management Tools:** Export test cases to tools like Jira/Zephyr, TestRail, or qTest; maintain ID synchronization.
- **CI/CD Integration:** Flag automation candidates for inclusion in pipeline quality gates; reference in `docs/development/cicd-spec.md`.
- **Evidence Capture:** Define screenshot, log, and report storage conventions; link evidence locations in RTM and test execution records.
- **Defect Lifecycle:** Integrate with defect management process defined in `docs/testing/TestPlan.md`; ensure defect IDs trace back to test cases and BRD requirements.

This comprehensive prompt ensures every business requirement documented in the BRD receives rigorous, traceable functional test coverage with clear validation criteria, data needs, and governance alignment.
