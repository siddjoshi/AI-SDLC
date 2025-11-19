# AI-SDLC Architecture Flow

## Document Control
| Version | Date | Author | Reviewer | Changes |
|---------|------|--------|----------|---------|
| 1.0     | 2025-11-19 | AI Agent | - | Initial architecture flow diagram |

## Purpose

This document provides a comprehensive Mermaid-based visualization of the AI-SDLC workflow, showing the flow from inception through operations, including agent personas, artifacts, and dependencies.

## Architecture Overview

The AI-SDLC framework follows a phased approach with 7 distinct phases, each with specific personas, deliverables, and quality gates. The diagram below illustrates the complete flow.

## High-Level SDLC Flow Diagram

```mermaid
graph TB
    Start([Opportunity/Idea Intake]) --> Phase1
    
    subgraph Phase1[Phase 1: Inception]
        P1_Input[Business Context<br/>Stakeholder Info<br/>Compliance Requirements]
        P1_Persona1[Business Strategist]
        P1_Persona2[Portfolio Manager]
        P1_Artifacts[Business Case<br/>Vision & Goals<br/>Stakeholder Register<br/>RACI Matrix<br/>Communication Plan]
        P1_Gate{Phase Gate 1:<br/>Business Case Approved?}
        
        P1_Input --> P1_Persona1
        P1_Input --> P1_Persona2
        P1_Persona1 --> P1_Artifacts
        P1_Persona2 --> P1_Artifacts
        P1_Artifacts --> P1_Gate
    end
    
    P1_Gate -->|Yes| Phase2
    P1_Gate -->|No| P1_Input
    
    subgraph Phase2[Phase 2: Requirements]
        P2_Persona1[Product Manager]
        P2_Persona2[Systems Analyst]
        P2_Persona3[Product Operations]
        P2_Persona4[NFR Specialist]
        P2_Artifacts[BRD<br/>PRD<br/>SRS<br/>NFR<br/>RTM<br/>Backlog Hierarchy]
        P2_Gate{Phase Gate 2:<br/>Requirements Baselined?}
        
        P2_Persona1 --> P2_Artifacts
        P2_Persona2 --> P2_Artifacts
        P2_Persona3 --> P2_Artifacts
        P2_Persona4 --> P2_Artifacts
        P2_Artifacts --> P2_Gate
    end
    
    P2_Gate -->|Yes| Phase3
    P2_Gate -->|No| Phase2
    
    subgraph Phase3[Phase 3: Design]
        P3_Persona1[Solution Architect]
        P3_Persona2[Security Architect]
        P3_Persona3[Data Architect]
        P3_Artifacts[HLD<br/>LLD<br/>API Specs<br/>Threat Model<br/>Data Architecture<br/>ADRs]
        P3_Gate{Phase Gate 3:<br/>Architecture Approved?}
        
        P3_Persona1 --> P3_Artifacts
        P3_Persona2 --> P3_Artifacts
        P3_Persona3 --> P3_Artifacts
        P3_Artifacts --> P3_Gate
    end
    
    P3_Gate -->|Yes| Phase4
    P3_Gate -->|No| Phase3
    
    subgraph Phase4[Phase 4: Development Enablement]
        P4_Persona1[Engineering Lead]
        P4_Persona2[DevOps Lead]
        P4_Persona3[Security Engineer]
        P4_Artifacts[Coding Standards<br/>CI/CD Spec<br/>Environment Matrix<br/>SBOM Strategy<br/>Iteration Plan]
        P4_Gate{Phase Gate 4:<br/>Dev Ready?}
        
        P4_Persona1 --> P4_Artifacts
        P4_Persona2 --> P4_Artifacts
        P4_Persona3 --> P4_Artifacts
        P4_Artifacts --> P4_Gate
    end
    
    P4_Gate -->|Yes| Phase5
    P4_Gate -->|No| Phase4
    
    subgraph Phase5[Phase 5: Testing & QA]
        P5_Persona1[QA/Test Lead]
        P5_Persona2[Performance Engineer]
        P5_Persona3[Security QA]
        P5_Artifacts[Test Plan<br/>Test Suites<br/>Test Data Strategy<br/>Defect Management<br/>Test Coverage Matrix]
        P5_Gate{Phase Gate 5:<br/>All Tests Passed?}
        
        P5_Persona1 --> P5_Artifacts
        P5_Persona2 --> P5_Artifacts
        P5_Persona3 --> P5_Artifacts
        P5_Artifacts --> P5_Gate
    end
    
    P5_Gate -->|Yes| Phase6
    P5_Gate -->|No| Phase5
    
    subgraph Phase6[Phase 6: Release & Deployment]
        P6_Persona1[Release Manager]
        P6_Persona2[Change Manager]
        P6_Persona3[Support Lead]
        P6_Artifacts[Deployment Runbook<br/>Release Notes<br/>Rollback Plan<br/>Go/No-Go Checklist<br/>Support Readiness]
        P6_Gate{Phase Gate 6:<br/>Production Ready?}
        
        P6_Persona1 --> P6_Artifacts
        P6_Persona2 --> P6_Artifacts
        P6_Persona3 --> P6_Artifacts
        P6_Artifacts --> P6_Gate
    end
    
    P6_Gate -->|Yes| Phase7
    P6_Gate -->|No| Phase6
    
    subgraph Phase7[Phase 7: Operations & Improvement]
        P7_Persona1[SRE/Operations Lead]
        P7_Persona2[Service Owner]
        P7_Persona3[Agile Coach]
        P7_Artifacts[Incident Playbooks<br/>Observability Status<br/>RCA Templates<br/>Retrospective Reports]
        P7_Output[Production System<br/>Continuous Improvement]
        
        P7_Persona1 --> P7_Artifacts
        P7_Persona2 --> P7_Artifacts
        P7_Persona3 --> P7_Artifacts
        P7_Artifacts --> P7_Output
    end
    
    P7_Output --> Feedback[Feedback Loop]
    Feedback -.->|Improvements| Phase2
    
    style Phase1 fill:#e1f5ff
    style Phase2 fill:#fff4e1
    style Phase3 fill:#ffe1f5
    style Phase4 fill:#e1ffe8
    style Phase5 fill:#fff0e1
    style Phase6 fill:#f0e1ff
    style Phase7 fill:#e1f0ff
```

## Traceability & Governance Flow

```mermaid
graph LR
    subgraph Governance[Continuous Governance]
        RTM[Requirements<br/>Traceability Matrix]
        ChangeLog[Change Log]
        PhaseGates[Phase Gates]
    end
    
    subgraph Artifacts[Document Flow]
        Inception[Inception Docs] --> Requirements[Requirements Docs]
        Requirements --> Design[Design Docs]
        Design --> DevEnable[Dev Enablement]
        DevEnable --> Testing[Testing Docs]
        Testing --> Release[Release Docs]
        Release --> Operations[Operations Docs]
    end
    
    Inception -.->|Traces to| RTM
    Requirements -.->|Updates| RTM
    Design -.->|Links| RTM
    Testing -.->|Validates| RTM
    
    Inception -.->|Records| ChangeLog
    Requirements -.->|Records| ChangeLog
    Design -.->|Records| ChangeLog
    DevEnable -.->|Records| ChangeLog
    Testing -.->|Records| ChangeLog
    Release -.->|Records| ChangeLog
    Operations -.->|Records| ChangeLog
    
    PhaseGates -.->|Controls| Inception
    PhaseGates -.->|Controls| Requirements
    PhaseGates -.->|Controls| Design
    PhaseGates -.->|Controls| DevEnable
    PhaseGates -.->|Controls| Testing
    PhaseGates -.->|Controls| Release
    
    style RTM fill:#ffcccc
    style ChangeLog fill:#ccffcc
    style PhaseGates fill:#ccccff
```

## Detailed Phase Workflow

```mermaid
flowchart TD
    subgraph Legend
        Input[/Input/]
        Process[Process]
        Decision{Decision}
        Output[Output]
        Document[(Document)]
    end
    
    subgraph DetailedFlow[Detailed SDLC Workflow]
        A[/Opportunity Intake/] --> B[Business Case Development]
        B --> C[(Business Case<br/>Vision & Goals)]
        C --> D{Stakeholders<br/>Aligned?}
        
        D -->|No| B
        D -->|Yes| E[Requirements Gathering]
        
        E --> F[BRD Creation]
        E --> G[PRD Creation]
        E --> H[SRS Creation]
        E --> I[NFR Definition]
        
        F --> J[(BRD)]
        G --> K[(PRD)]
        H --> L[(SRS)]
        I --> M[(NFR)]
        
        J & K & L & M --> N[RTM Initialization]
        N --> O[(RTM v1.0)]
        
        O --> P[Backlog Creation]
        P --> Q[(Epics/Features/<br/>Stories/Tasks)]
        
        Q --> R{Requirements<br/>Baseline?}
        R -->|No| E
        R -->|Yes| S[Architecture Design]
        
        S --> T[HLD Development]
        S --> U[Security Design]
        S --> V[Data Architecture]
        
        T --> W[(HLD)]
        U --> X[(Threat Model)]
        V --> Y[(Data Architecture)]
        
        W & X & Y --> Z{Architecture<br/>Approved?}
        Z -->|No| S
        Z -->|Yes| AA[Development Setup]
        
        AA --> AB[CI/CD Configuration]
        AA --> AC[Coding Standards]
        AA --> AD[Environment Setup]
        
        AB & AC & AD --> AE[(Dev Enablement<br/>Package)]
        
        AE --> AF{Dev<br/>Ready?}
        AF -->|No| AA
        AF -->|Yes| AG[Test Planning]
        
        AG --> AH[Test Case Design]
        AG --> AI[Test Automation]
        AG --> AJ[Performance Tests]
        
        AH & AI & AJ --> AK[(Test Suite)]
        
        AK --> AL{Tests<br/>Passed?}
        AL -->|No| AG
        AL -->|Yes| AM[Release Preparation]
        
        AM --> AN[Deployment Runbook]
        AM --> AO[Release Notes]
        AM --> AP[Rollback Plan]
        
        AN & AO & AP --> AQ[(Release Package)]
        
        AQ --> AR{Go/No-Go?}
        AR -->|No-Go| AM
        AR -->|Go| AS[Production Deployment]
        
        AS --> AT[Operations Setup]
        AT --> AU[Monitoring & Observability]
        AT --> AV[Incident Management]
        
        AU & AV --> AW[Live System]
        AW --> AX[Continuous Improvement]
        AX -.->|Feedback| E
    end
    
    style A fill:#e1f5ff
    style C fill:#ffe1e1
    style O fill:#ffe1e1
    style Q fill:#ffe1e1
    style W fill:#ffe1e1
    style AE fill:#ffe1e1
    style AK fill:#ffe1e1
    style AQ fill:#ffe1e1
    style AW fill:#e1ffe1
```

## Agent Collaboration Model

```mermaid
graph TB
    subgraph AgentEcosystem[AI Agent Ecosystem]
        Templates[(" templates/")]
        Prompts[(prompts/)]
        
        subgraph Phase1Agents[Phase 1 Agents]
            BS[Business<br/>Strategist]
            PM_Inception[Portfolio<br/>Manager]
        end
        
        subgraph Phase2Agents[Phase 2 Agents]
            PM[Product<br/>Manager]
            SA[Systems<br/>Analyst]
            PO[Product<br/>Operations]
            NFR[NFR<br/>Specialist]
        end
        
        subgraph Phase3Agents[Phase 3 Agents]
            SolArch[Solution<br/>Architect]
            SecArch[Security<br/>Architect]
            DataArch[Data<br/>Architect]
        end
        
        subgraph Phase4Agents[Phase 4 Agents]
            EngLead[Engineering<br/>Lead]
            DevOps[DevOps<br/>Lead]
            SecEng[Security<br/>Engineer]
        end
        
        subgraph Phase5Agents[Phase 5 Agents]
            QALead[QA/Test<br/>Lead]
            PerfEng[Performance<br/>Engineer]
            SecQA[Security<br/>QA]
        end
        
        subgraph Phase6Agents[Phase 6 Agents]
            RelMgr[Release<br/>Manager]
            ChgMgr[Change<br/>Manager]
            SuppLead[Support<br/>Lead]
        end
        
        subgraph Phase7Agents[Phase 7 Agents]
            SRE[SRE/Ops<br/>Lead]
            SvcOwner[Service<br/>Owner]
            Coach[Agile<br/>Coach]
        end
        
        subgraph Outputs[Documentation Outputs]
            DocsInception[(docs/inception/)]
            DocsReq[(docs/requirements/)]
            DocsDesign[(docs/design/)]
            DocsDev[(docs/development/)]
            DocsTest[(docs/testing/)]
            DocsRelease[(docs/release/)]
            DocsOps[(docs/operations/)]
            Backlog[(backlog/)]
        end
        
        Templates --> Phase1Agents
        Templates --> Phase2Agents
        Templates --> Phase3Agents
        Templates --> Phase4Agents
        Templates --> Phase5Agents
        Templates --> Phase6Agents
        Templates --> Phase7Agents
        
        Prompts --> Phase1Agents
        Prompts --> Phase2Agents
        Prompts --> Phase3Agents
        Prompts --> Phase4Agents
        Prompts --> Phase5Agents
        Prompts --> Phase6Agents
        Prompts --> Phase7Agents
        
        Phase1Agents --> DocsInception
        Phase2Agents --> DocsReq
        Phase2Agents --> Backlog
        Phase3Agents --> DocsDesign
        Phase4Agents --> DocsDev
        Phase5Agents --> DocsTest
        Phase6Agents --> DocsRelease
        Phase7Agents --> DocsOps
        
        DocsInception -.->|Input| Phase2Agents
        DocsReq -.->|Input| Phase3Agents
        DocsDesign -.->|Input| Phase4Agents
        DocsDev -.->|Input| Phase5Agents
        DocsTest -.->|Input| Phase6Agents
        DocsRelease -.->|Input| Phase7Agents
    end
    
    style Templates fill:#ffcccc
    style Prompts fill:#ccffcc
    style Outputs fill:#ccccff
```

## Document Traceability Chain

```mermaid
flowchart LR
    subgraph Traceability[End-to-End Traceability]
        BC[Business Case] --> BRD[BRD]
        BRD --> PRD[PRD]
        PRD --> SRS[SRS]
        SRS --> NFR[NFR]
        
        BRD & PRD & SRS & NFR --> RTM[RTM]
        
        RTM --> Epic[Epics]
        Epic --> Feature[Features]
        Feature --> Story[Stories]
        Story --> Task[Tasks]
        
        RTM --> HLD[HLD]
        HLD --> LLD[LLD]
        LLD --> API[API Specs]
        
        RTM --> TestPlan[Test Plan]
        TestPlan --> TestCase[Test Cases]
        
        Story & Task --> DevWork[Development Work]
        TestCase --> TestExec[Test Execution]
        
        DevWork & TestExec --> Release[Release]
        Release --> Ops[Operations]
        
        Ops -.->|Feedback| RTM
    end
    
    subgraph ChangeManagement[Change Management]
        ChangeLog[Change Log]
        RTM -.->|Updates| ChangeLog
        HLD -.->|Updates| ChangeLog
        TestPlan -.->|Updates| ChangeLog
        Release -.->|Updates| ChangeLog
    end
    
    style RTM fill:#ff9999,stroke:#ff0000,stroke-width:3px
    style ChangeLog fill:#99ff99,stroke:#00ff00,stroke-width:3px
```

## Technology Stack & Integration Points

```mermaid
graph TB
    subgraph Workspace[AI-SDLC Workspace]
        Git[Git Repository]
        Templates[Templates Directory]
        Prompts[Prompts Library]
        Docs[Documentation]
    end
    
    subgraph AIAgents[AI Agent Layer]
        GPT[GPT-4/Claude]
        Copilot[GitHub Copilot]
        Custom[Custom Agents]
    end
    
    subgraph Tools[Development Tools]
        Jira[Jira/ADO]
        CI[CI/CD Pipeline]
        Monitor[Monitoring Tools]
    end
    
    subgraph Quality[Quality Gates]
        CodeQL[CodeQL Security]
        Lint[Linters]
        Tests[Automated Tests]
    end
    
    Workspace <--> AIAgents
    AIAgents <--> Tools
    AIAgents <--> Quality
    
    Git -.->|Version Control| Docs
    Templates -.->|Input| AIAgents
    Prompts -.->|Instructions| AIAgents
    
    Jira <-.->|Sync| Docs
    CI <-.->|Validate| Docs
    Monitor <-.->|Feedback| Docs
    
    style Workspace fill:#e1f5ff
    style AIAgents fill:#fff4e1
    style Tools fill:#e1ffe8
    style Quality fill:#ffe1e1
```

## Key Features

### Phase Gates
Each phase has explicit entry and exit criteria enforced through phase gates:
- **Entry Criteria**: Prerequisites that must be met before starting the phase
- **Exit Criteria**: Deliverables and quality metrics required to proceed
- **Quality Gates**: Automated and manual checks
- **Go/No-Go Decision**: Formal approval from governance board

### Traceability
The Requirements Traceability Matrix (RTM) serves as the single source of truth:
- Links requirements to design, development, testing, and operations
- Bidirectional sync with Jira/Azure DevOps
- Automated coverage tracking
- Change impact analysis

### Governance
Continuous governance through:
- Change Log: Records all decisions, risks, and baselines
- Approval Tables: Embedded in each template for sign-offs
- Version Control: Document history and audit trail
- Compliance Alignment: Security, privacy, and regulatory requirements

### Automation
AI agents automate documentation creation:
- Template-driven approach ensures consistency
- Persona-specific prompts guide each agent
- Parallel execution where dependencies allow
- Quality checks before phase transitions

## Usage

1. **Start with Inception**: Ensure business case and stakeholder alignment
2. **Follow Phase Sequence**: Respect dependencies and phase gates
3. **Update RTM Continuously**: Maintain traceability throughout
4. **Record in Change Log**: Document all decisions and changes
5. **Obtain Approvals**: Use embedded approval tables
6. **Iterate as Needed**: Feedback loop from operations to requirements

## References

- [README.md](../README.md) - Repository overview and quick start
- [AGENTS.md](../AGENTS.md) - Agent operating handbook
- [Phase Gates Template](../ templates/phase-gates.md) - Detailed gate criteria
- [RTM Template](../ templates/RTM.md) - Traceability matrix structure
- [Prompts Catalog](../prompts/SDLC_AI_Agent.md) - All agent prompts
