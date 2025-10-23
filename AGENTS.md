# Agent Instructions for Plan and Design Workflow (Don't create Code)

## Overview
This document provides instructions for AI agents on how to create comprehensive project documentation using the available templates when a user requests "Plan and Design" for a business requirement. Do not write any runnable code. Create documentation only. Produce clear, structured Markdown files

## Workflow for Plan and Design(Don't create any Code)

When a user provides a business requirement and asks for "Plan and Design", do not write any runnable code and follow this structured workflow:

### Step 1: Create Business Requirements Document (BRD)
**Template:** `/templates/BRD_Template.md`

**Instructions:**
1. Start by analyzing the business requirement provided by the user
2. Use the BRD template as the foundation
3. Fill in all relevant sections based on the business requirement:
   - Executive Summary with project overview and business objectives
   - Background and business context
   - Stakeholders identification and their requirements
   - Scope (in-scope, out-of-scope, assumptions, constraints, dependencies)
   - Business processes (current As-Is and proposed To-Be)
   - Functional requirements at a high level
   - Non-functional requirements overview
   - Cost-benefit analysis
   - Timeline and milestones
   - Risks and mitigation strategies
4. Save the completed BRD in `/docs/BRD.md`

**Key Focus Areas:**
- Ensure business objectives are clear and measurable
- Define success criteria with specific KPIs
- Identify all stakeholders and their interests
- Document all assumptions and constraints explicitly
- Provide realistic timeline estimates

### Step 2: Create Functional Specification Document (FSD)
**Template:** `/templates/Functional_Spec_Template.md`

**Instructions:**
1. Use the BRD as the primary input
2. Use the Functional Specification template
3. Expand the high-level functional requirements from BRD into detailed specifications:
   - System overview and context
   - Detailed feature specifications with user stories
   - User interface specifications with screen descriptions
   - Data specifications and models
   - Integration specifications with external systems
   - API specifications with request/response formats
   - Security specifications
   - Performance specifications
   - Workflow and business process details
   - Error handling and logging requirements
   - Testing requirements
4. Save the completed FSD in `/docs/Functional_Spec.md`

**Key Focus Areas:**
- Break down each feature into specific, testable requirements
- Include acceptance criteria for each requirement
- Document data flows and transformations
- Specify API contracts clearly
- Define error scenarios and handling

### Step 3: Create High-Level Design Document (HLD)
**Template:** `/templates/HLD_Template.md`

**Instructions:**
1. Use both BRD and FSD as inputs
2. Use the HLD template
3. Design the technical architecture that satisfies the functional requirements:
   - Define architecture style (microservices, monolithic, etc.)
   - Select appropriate technology stack
   - Design system architecture with layers (presentation, application, data, integration)
   - Design component architecture
   - Design data architecture and database schema
   - Design interface specifications (UI, API, integration)
   - Design security architecture (authentication, authorization, encryption)
   - Design performance and scalability approach
   - Design availability and reliability mechanisms
   - Design deployment architecture
   - Design monitoring and logging strategy
4. Save the completed HLD in `/docs/HLD.md`

**Key Focus Areas:**
- Ensure architecture aligns with non-functional requirements
- Design for scalability and maintainability
- Address security at every layer
- Consider deployment and operational aspects
- Document design decisions and trade-offs

### Step 4: Create Architecture Diagrams
**Template:** `/templates/Architecture_Diagram_Template.md`

**Instructions:**
1. Use the HLD as the primary input
2. Use the Architecture Diagram template as a guide
3. Create the following diagrams:
   - **System Context Diagram:** Show the system, users, and external systems
   - **Container Diagram:** Show web apps, APIs, databases, and their relationships
   - **Component Diagram:** Show internal components of key containers
   - **Deployment Diagram:** Show infrastructure and deployment topology
   - **Data Flow Diagram:** Show how data moves through the system
   - **Sequence Diagrams:** Show key interaction flows
4. Use standard notation (C4 Model, UML, PlantUML, or Mermaid)
5. Save diagrams in `/docs/diagrams/` folder
   - `/docs/diagrams/system-context.md`
   - `/docs/diagrams/container-diagram.md`
   - `/docs/diagrams/component-diagram.md`
   - `/docs/diagrams/deployment-diagram.md`
   - `/docs/diagrams/data-flow.md`
   - `/docs/diagrams/sequence-diagrams.md`

**Key Focus Areas:**
- Keep diagrams clear and uncluttered
- Use consistent notation and colors
- Include legends for symbols used
- Ensure diagrams match the HLD descriptions
- Version and date all diagrams

### Step 5: Create Non-Functional Requirements (NFR) Document
**Template:** `/templates/NFR_Template.md`

**Instructions:**
1. Use BRD and FSD as inputs for context
2. Use the NFR template
3. Define comprehensive non-functional requirements:
   - **Security Requirements:**
     - Authentication requirements (MFA, SSO, session management)
     - Authorization requirements (RBAC, permissions)
     - Data security (encryption at rest and in transit)
     - Network security (WAF, DDoS protection)
     - Application security (XSS, CSRF, SQL injection prevention)
     - Security monitoring and logging
     - Vulnerability management
     - Compliance (OWASP, GDPR, PCI-DSS, SOC 2, ISO 27001)
   - **Performance Requirements:**
     - Response time targets for different operations
     - Throughput requirements (TPS, concurrent users)
     - Scalability requirements (horizontal/vertical)
     - Resource utilization limits (CPU, memory, disk)
     - Database performance targets
     - Caching strategy and targets
     - Capacity planning
   - **Accessibility Requirements:**
     - WCAG 2.1 Level AA compliance
     - Perceivable content (alt text, captions, contrast)
     - Operable interface (keyboard accessible, no keyboard traps)
     - Understandable content (clear errors, consistent navigation)
     - Robust markup (valid HTML, ARIA attributes)
     - Assistive technology compatibility
   - **Additional Quality Attributes:**
     - Availability (uptime, MTTR, MTBF)
     - Reliability (error rate, data accuracy)
     - Maintainability (code standards, documentation)
     - Usability (task completion, error rate)
     - Disaster recovery (RTO, RPO, backup strategy)
4. Save the completed NFR in `/docs/NFR.md`

**Key Focus Areas:**
- Specify measurable targets for all NFRs
- Prioritize requirements (High, Medium, Low)
- Ensure security requirements cover OWASP Top 10
- Define clear acceptance criteria
- Address compliance requirements explicitly

## Document Organization

All generated documents should be placed in the `/docs` folder with the following structure:

```
/docs
├── BRD.md                          # Business Requirements Document
├── Functional_Spec.md               # Functional Specification Document
├── HLD.md                           # High-Level Design Document
├── NFR.md                           # Non-Functional Requirements Document
└── diagrams/                        # Architecture Diagrams
    ├── system-context.md
    ├── container-diagram.md
    ├── component-diagram.md
    ├── deployment-diagram.md
    ├── data-flow.md
    └── sequence-diagrams.md
```

## Quality Checklist

Before finalizing the documentation, verify:

- [ ] BRD clearly articulates business objectives and success criteria
- [ ] FSD provides detailed, testable functional requirements
- [ ] HLD provides comprehensive technical design
- [ ] Architecture diagrams are clear and consistent with HLD
- [ ] NFR covers security, performance, and accessibility comprehensively
- [ ] All documents reference each other appropriately
- [ ] All assumptions and constraints are documented
- [ ] All risks are identified with mitigation strategies
- [ ] All documents are complete with no TBD items
- [ ] All compliance requirements are addressed

## Templates Location

All templates are located in the `/templates` directory:
- `/templates/BRD_Template.md`
- `/templates/Functional_Spec_Template.md`
- `/templates/HLD_Template.md`
- `/templates/Architecture_Diagram_Template.md`
- `/templates/NFR_Template.md`

## Example Usage

**User Request:**
> "I need plan and design for an e-commerce platform that allows users to browse products, add to cart, and checkout with payment processing."

**Agent Actions:**
1. Create `/docs/BRD.md` based on the e-commerce requirement
2. Create `/docs/Functional_Spec.md` with detailed features for product browsing, cart, checkout, and payment
3. Create `/docs/HLD.md` with architecture for web app, API services, database, and payment gateway integration
4. Create architecture diagrams in `/docs/diagrams/`
5. Create `/docs/NFR.md` with security (PCI-DSS for payments), performance (response times), and accessibility requirements

## Industry Standards Reference

Ensure all templates are filled following these industry standards:

### For BRD:
- IEEE 830 (Software Requirements Specification)
- BABOK (Business Analysis Body of Knowledge)
- PMI PMBOK (Project Management Body of Knowledge)

### For FSD:
- IEEE 1016 (Software Design Descriptions)
- ISO/IEC/IEEE 29148 (Requirements Engineering)

### For HLD:
- IEEE 1471 (Architecture Descriptions)
- C4 Model for Software Architecture
- The Twelve-Factor App methodology

### For Architecture Diagrams:
- C4 Model notation
- UML 2.0 standards
- ArchiMate 3.0

### For NFR:
- **Security:** OWASP Top 10, NIST Cybersecurity Framework, ISO 27001
- **Performance:** ISO/IEC 25010 (Quality Model)
- **Accessibility:** WCAG 2.1 Level AA, Section 508, EN 301 549

## Agent Best Practices

1. **Ask Clarifying Questions:** If the business requirement is vague or incomplete, ask the user for clarification before proceeding
2. **Start with BRD:** Always create the BRD first as it forms the foundation for all other documents
3. **Maintain Consistency:** Ensure all documents are consistent with each other
4. **Be Comprehensive:** Don't leave sections empty; fill them thoughtfully based on the requirement
5. **Use Industry Standards:** Apply industry best practices and standards throughout
6. **Focus on Quality:** Prioritize quality over speed; thorough documentation is critical
7. **Version Control:** Include version information in all documents
8. **Cross-Reference:** Link related sections across documents
9. **Validate Completeness:** Review the quality checklist before marking the task complete

## Notes

- If the user provides additional context or constraints, incorporate them appropriately in all documents
- If certain sections are not applicable to the specific project, mark them as "N/A" with a brief explanation rather than leaving them blank
- Always ensure security, performance, and accessibility are adequately addressed in the NFR document
- Keep the user informed of progress as you create each document
