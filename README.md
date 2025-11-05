# AI-SDLC

# SDLC Artifacts – Phase-wise Catalogue

This document provides a **structured, phase-wise list of all key and optional artifacts** produced during the Software Development Life Cycle (SDLC). Each entry includes:
- **Document Name**
- **Description**
- **Input Required**
- **Depends On**
- **Referenced By**
- **Mandatory / Optional**
- **Applicable Methodologies**

---

## **Phase 1: Inception / Pre-Project**

| Phase      | Document Name       | Description                                      | Input Required                | Depends On | Referenced By                | Mandatory / Optional | Methodologies |
|------------|---------------------|--------------------------------------------------|--------------------------------|------------|--------------------------------|------------------------|---------------|
| Inception  | Business Case       | Justifies project, ROI, risks, benefits         | Opportunity / Idea            | None       | Project Charter, Roadmap      | **✅ Mandatory**      | All           |
| Inception  | Vision & Goals      | Defines product vision and success metrics      | Business Case                 | Business Case | PRD, Roadmap                  | **✅ Mandatory**      | All           |
| Inception  | Stakeholder Register| Identifies key stakeholders and roles           | Vision & Goals                | Vision & Goals | RACI, Comms Plan              | **✅ Mandatory**      | All           |
| Inception  | Project Charter     | Authorises project, scope, budget               | Business Case, Stakeholder Register | Business Case | Delivery Plan, RAID Log       | **✅ Mandatory**      | Waterfall, Hybrid |
| Inception  | RACI Matrix         | Roles and responsibilities                      | Stakeholder Register          | Stakeholder Register | Change Control, Governance    | *⚪ Optional*         | All           |
| Inception  | Communication Plan  | Defines communication cadence and channels      | Stakeholder Register          | Stakeholder Register | Governance, Release Comms     | *⚪ Optional*         | All           |

---

## **Phase 2: Requirements**

| Phase        | Document Name                | Description                                      | Input Required                  | Depends On       | Referenced By                     | Mandatory / Optional | Methodologies |
|--------------|-----------------------------|--------------------------------------------------|---------------------------------|-------------------|-----------------------------------|------------------------|---------------|
| Requirements | [BRD (Business Req Doc)](BRD.md)needs and KPIs               | Vision & Goals, Stakeholder Register | Vision & Goals    | SRS, HLD                          | *⚪ Optional*         | Waterfall, Hybrid |
| Requirements | PRD (Product Req Doc)       | Defines product features and acceptance criteria| Vision & Goals, Discovery Data | Vision & Goals    | Backlog, HLD, Test Strategy       | **✅ Mandatory**      | Agile, Hybrid |
| Requirements | SRS.md     | Functional & non-functional requirements        | BRD/PRD, Elicitation Outputs    | BRD/PRD          | HLD, LLD, RTM, Test Design        | **✅ Mandatory**      | All           |
| Requirements | NFR Spec                    | Quality attributes (performance, security)      | Vision & Goals, PRD/SRS         | PRD/SRS          | HLD, Test Strategy, SLOs          | **✅ Mandatory**      | All           |
| Requirements | RTM.md   | Maps requirements to design & tests             | SRS/User Stories                | SRS              | Test Evidence, Release Readiness  | **✅ Mandatory**      | All           |
| Requirements | User Stories & Acceptance Criteria | Agile slice of requirements                   | PRD                              | PRD              | Sprint Backlog, Test Cases         | **✅ Mandatory (Agile)** | Agile         |

---

## **Phase 3: Design**

| Phase   | Document Name         | Description                                      | Input Required                  | Depends On       | Referenced By                     | Mandatory / Optional | Methodologies |
|---------|-----------------------|--------------------------------------------------|---------------------------------|-------------------|-----------------------------------|------------------------|---------------|
| Design  | Architecture Overview | High-level principles and constraints           | SRS, NFR Spec                   | SRS, NFRs        | HLD, ADRs                          | **✅ Mandatory**      | All           |
| Design  | ADR (Decision Record) | Logs architecture decisions and rationale        | Architecture Overview            | Architecture Overview | HLD, LLD, Ops SOPs                | **✅ Mandatory**      | All           |
| Design  | [HLD (High-Level Design)](HLD.md)| System decomposition, interfaces, deployment    | SRS, NFRs, ADRs                 | SRS, ADRs        | LLD, API Spec, Threat Model        | **✅ Mandatory**      | All          el Design)| Detailed component-level design                 | HLD                              | HLD              | Code, Unit Tests                   | **✅ Mandatory (Waterfall)** | Waterfall, Hybrid |
| Design  | API Spec / ICD        | Interface contracts                             | HLD                              | HLD              | Dev, Contract Tests                | **✅ Mandatory**      | All           |
| Design  | Threat Model          | Identifies threats and mitigations             | Security Requirements, HLD       | Security Reqs, HLD| Security Tests, Controls           | **✅ Mandatory**      | All           |

---

## **Phase 4: Development**

| Phase       | Document Name           | Description                                      | Input Required                  | Depends On       | Referenced By                     | Mandatory / Optional | Methodologies |
|-------------|-------------------------|--------------------------------------------------|---------------------------------|-------------------|-----------------------------------|------------------------|---------------|
| Development | Coding Standards        | Language/framework conventions                  | LLD/Stories                     | LLD              | Code Reviews, CI Gates            | **✅ Mandatory**      | All           |
| Development | CI/CD Pipeline Spec     | Build, test, deploy automation                 | Branching Strategy              | Config Mgmt Plan | Release Plan, Deployment Plan      | **✅ Mandatory**      | DevOps        |
| Development | SBOM                    | Software Bill of Materials                     | Pipeline                        | Pipeline          | Security Reviews, Audits           | **✅ Mandatory**      | DevOps        |
| Development | Unit Test Specs         | Module-level verification                      | LLD/Stories                     | LLD              | Test Summary, RTM                  | **✅ Mandatory**      | All           |

---

## **Phase 5: Testing**

| Phase    | Document Name       | Description                                      | Input Required                  | Depends On       | Referenced By                     | Mandatory / Optional | Methodologies |
|----------|---------------------|--------------------------------------------------|---------------------------------|-------------------|-----------------------------------|------------------------|---------------|
| Testing  | TestPlan.md       | Levels, coverage, automation policy             | SRS, NFR Spec                   | SRS, NFRs        | Test Plan, Test Suites             | **✅ Mandatory**      | All           |
| Testing  | [Test Plan](TestPlan.md)           | Scope, environment, entry/exit criteria         | Test Strategy                    | Test Strategy    | Execution Reports, Go/No-Go        | **✅ Mandatory**      | All           |
UAT Plan & Sign-off | Business validation and approval                | BRD/PRD, Test Plan               | BRD/PRD          | Go/No-Go, Release                  | **✅ Mandatory**      | All           |
| Testing  | Defect Log          | Tracks defects and triage                       | Test Execution                   | Test Execution   | RCA/Postmortem                     | **✅ Mandatory**      | All           |

---

## **Phase 6: Deployment & Release**

| Phase      | Document Name       | Description                                      | Input Required                  | Depends On       | Referenced By                     | Mandatory / Optional | Methodologies |
|------------|---------------------|--------------------------------------------------|---------------------------------|-------------------|-----------------------------------|------------------------|---------------|
| Release    | Deployment Runbook  | Step-by-step deployment instructions            | CI/CD Pipeline, HLD             | CI/CD, HLD       | OAT, Ops SOPs                      | **✅ Mandatory**      | DevOps        |
| Release    | Rollback Plan       | Verified rollback paths                         | Deployment Plan                  | Deployment Plan   | Incident Response                   | **✅ Mandatory**      | All           |
| Release    | Release Notes       | Changes, known issues, rollback hints          | Test Summary                     | Test Summary      | CAB/Comms, Ops                      | **✅ Mandatory**      | All           |

---

## **Phase 7: Maintenance & Operations**

| Phase       | Document Name       | Description                                      | Input Required                  | Depends On       | Referenced By                     | Mandatory / Optional | Methodologies |
|-------------|---------------------|--------------------------------------------------|---------------------------------|-------------------|-----------------------------------|------------------------|---------------|
| Operations  | Incident RCA        | Root cause analysis and corrective actions      | Incident Record, Telemetry       | Incident Record   | Problem Management, Backlog        | **✅ Mandatory**      | DevOps, ITIL  |
| Operations  | Retrospective Report| Process improvement actions                     | Release or Sprint                | Release/Sprint    | Ways-of-working updates             | **✅ Mandatory**      | Agile, DevOps |

---
