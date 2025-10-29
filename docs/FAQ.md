# Frequently Asked Questions (FAQ)

## 📋 General Questions

### What is AI-SDLC?

AI-SDLC is a comprehensive framework and template collection designed to streamline the software development life cycle (SDLC) documentation process. It provides industry-standard templates for Business Requirements Documents (BRD), Functional Specifications (FSD), High-Level Design (HLD), Architecture Diagrams, and Non-Functional Requirements (NFR).

### Who should use these templates?

These templates are useful for:
- **Business Analysts**: Creating BRDs and gathering requirements
- **Product Owners**: Defining product features and specifications
- **Solution Architects**: Designing system architecture
- **Technical Leads**: Planning technical implementation
- **Project Managers**: Managing project scope and stakeholders
- **Developers**: Understanding requirements and design
- **QA Teams**: Creating test plans and acceptance criteria
- **Compliance Officers**: Ensuring regulatory requirements are met

### Do I need to use all templates?

No, use the templates that fit your project needs. For small projects, you might combine BRD and FSD. For large enterprises, you might use all templates plus additional ones. Adapt based on:
- Project size and complexity
- Organization requirements
- Regulatory needs
- Team size and structure
- Project methodology (Waterfall, Agile, etc.)

### Can I modify the templates?

Absolutely! These templates are meant to be customized:
- Add or remove sections as needed
- Adjust for your organization's standards
- Combine templates if appropriate
- Extend with additional templates
- Adapt terminology to your domain

### Are these templates Agile-compatible?

Yes! While the format may seem traditional:
- Use templates for initial epics and features
- Create lightweight versions for sprints
- Update iteratively as understanding evolves
- Focus on relevant sections for each sprint
- Use as living documents, not one-time artifacts

## 📚 Template-Specific Questions

### Business Requirements Document (BRD)

**Q: How detailed should the BRD be?**

A: The BRD should be detailed enough to:
- Clearly communicate business objectives
- Define success criteria
- Establish scope boundaries
- Get stakeholder agreement

Avoid technical implementation details—save those for HLD.

**Q: Who approves the BRD?**

A: Typically:
- Project sponsor
- Key business stakeholders
- Product owner
- Executive sponsor (for large projects)

**Q: When should the BRD be created?**

A: Create the BRD during project initiation, before detailed functional specification or design work begins.

### Functional Specification Document (FSD)

**Q: What's the difference between BRD and FSD?**

A: 
- **BRD**: Business perspective—WHY and WHAT from business viewpoint
- **FSD**: User/functional perspective—WHAT the system does from user viewpoint

**Q: Should FSD include database schema?**

A: FSD should include:
- Logical data model (entities, attributes, relationships)
- Data validation rules
- Data flows

Reserve physical database schema for HLD or Low-Level Design (LLD).

**Q: How much UI detail in FSD?**

A: Include:
- Screen descriptions and purposes
- UI elements and their behavior
- Navigation flows
- User actions and outcomes
- Mockups or wireframes (if available)

Avoid pixel-perfect design—that's for UI/UX design docs.

### High-Level Design Document (HLD)

**Q: What's the difference between HLD and Low-Level Design (LLD)?**

A:
- **HLD**: Architecture, major components, technology choices, integration approach
- **LLD**: Detailed design, class diagrams, algorithms, data structures

Think of HLD as the blueprint, LLD as the construction plans.

**Q: Should HLD include code?**

A: Generally no. HLD may include:
- Pseudocode for complex algorithms
- API contract examples
- Configuration examples

Actual implementation code belongs in code comments and separate technical documentation.

**Q: How do I choose between architectural styles?**

A: Consider:
- **Monolithic**: Small to medium projects, single team, simpler deployment
- **Microservices**: Large projects, multiple teams, need for independent scaling
- **Serverless**: Event-driven workloads, variable traffic, minimal operations
- **Event-Driven**: Complex workflows, loose coupling, asynchronous processing

Document your rationale in the HLD.

### Architecture Diagrams

**Q: Which diagram notation should I use?**

A: We recommend:
- **C4 Model**: For architecture diagrams (simple, effective, widely understood)
- **UML**: For detailed design diagrams (class, sequence, state diagrams)
- **PlantUML/Mermaid**: For code-as-diagram approaches

Choose based on team familiarity and tool availability.

**Q: How many diagrams do I need?**

A: At minimum:
- System Context Diagram
- Container Diagram (showing major applications)
- Component Diagram (for complex containers)
- Deployment Diagram

Add more as needed (data flow, sequence diagrams) for complex scenarios.

**Q: Should diagrams be in separate files?**

A: Yes, we recommend:
- One diagram per file in `docs/diagrams/`
- Reference diagrams from main documents
- Use descriptive file names
- Version and date each diagram

### Non-Functional Requirements (NFR)

**Q: What's the difference between functional and non-functional requirements?**

A:
- **Functional**: What the system does (features, capabilities)
- **Non-Functional**: How well the system performs (quality attributes)

Example:
- Functional: "User can log in with username and password"
- Non-Functional: "Login shall complete within 2 seconds for 95% of requests"

**Q: How specific should performance requirements be?**

A: Very specific. Instead of "fast response time," specify:
- "API response time < 200ms for 95th percentile"
- "Page load time < 3 seconds on 3G connection"
- "System supports 10,000 concurrent users"

**Q: Are security requirements mandatory?**

A: Absolutely! Every system should address:
- Authentication and authorization
- Data protection (encryption)
- Input validation
- Security logging
- Compliance requirements (if applicable)

Never skip security requirements.

## 🔧 Process Questions

### Getting Started

**Q: Where do I start?**

A: Follow this sequence:
1. Gather business requirements
2. Create BRD (business objectives, scope, stakeholders)
3. Get BRD approved
4. Create FSD (detailed functional specs)
5. Review FSD with team
6. Create HLD (technical architecture)
7. Create Architecture Diagrams
8. Define NFRs (throughout the process)

**Q: How long does documentation take?**

A: Varies widely based on project size:
- **Small project**: 1-2 weeks
- **Medium project**: 3-4 weeks
- **Large enterprise project**: 2-3 months

Factor in review cycles and iterations.

**Q: Can I use AI to help?**

A: Yes! AI can:
- Generate initial drafts from business requirements
- Suggest architecture patterns
- Create diagram descriptions
- Fill in template sections

Always review AI output for accuracy and relevance.

### Documentation Process

**Q: How often should documents be updated?**

A: Update when:
- Requirements change
- Design decisions change
- New features added
- Implementation reveals gaps
- After each major milestone

Keep documentation current—outdated docs are worse than no docs.

**Q: Who owns the documentation?**

A: Ownership typically:
- **BRD**: Business Analyst or Product Owner
- **FSD**: Business Analyst or Product Owner
- **HLD**: Solution Architect or Technical Lead
- **NFR**: Architect, Security Team, QA Team

Entire team contributes and maintains.

**Q: How do I handle changes?**

A: 
1. Document the change request
2. Assess impact on existing documentation
3. Update affected documents
4. Update version numbers
5. Review and approve changes
6. Communicate to stakeholders
7. Update related documents

### Quality and Review

**Q: How do I know if documentation is good enough?**

A: Good documentation:
- Answers the questions readers will have
- Is complete (no TBDs or placeholders)
- Is accurate and technically correct
- Is consistent across all documents
- Is reviewed and approved by stakeholders
- Passes the "new team member" test

**Q: Who should review documentation?**

A: Different audiences:
- **BRD**: Business stakeholders, sponsors, product owner
- **FSD**: Product owner, developers, QA team
- **HLD**: Architects, senior developers, DevOps
- **NFR**: Security team, architects, QA, compliance

**Q: What if stakeholders disagree?**

A: 
1. Document different viewpoints
2. Facilitate discussion to resolve
3. Escalate to decision-maker if needed
4. Document final decision and rationale
5. Get formal sign-off

## 🛠️ Technical Questions

### Tools and Formats

**Q: Why Markdown instead of Word?**

A: Markdown offers:
- Version control friendly (plain text)
- Easy to diff and merge
- Platform independent
- Simple syntax
- Convertible to PDF, HTML, Word

Use Word if your organization requires it.

**Q: What tools do you recommend?**

A:
- **Editing**: VS Code, Typora, Obsidian
- **Diagrams**: Draw.io, PlantUML, Mermaid, Lucidchart
- **Collaboration**: GitHub, GitLab, Confluence
- **Version Control**: Git
- **Conversion**: Pandoc (for PDF/Word export)

**Q: How do I convert Markdown to PDF?**

A: Several options:
```bash
# Using Pandoc
pandoc input.md -o output.pdf

# Using markdown-pdf (npm)
npm install -g markdown-pdf
markdown-pdf input.md

# Using VS Code extensions
# Install "Markdown PDF" extension
```

### Integration

**Q: Can I integrate with Jira/Azure DevOps?**

A: Yes, several approaches:
- Link requirements in docs to Jira tickets
- Use Jira/ADO for requirements tracking
- Keep design docs in repos
- Use Confluence for wikis (import Markdown)
- Automate with APIs

**Q: How do I link requirements to code?**

A: 
- Use requirement IDs in code comments
- Reference requirements in commit messages
- Use traceability matrix
- Link requirements in issue tracking
- Use code annotations or decorators

## 🌍 Industry-Specific Questions

**Q: Are these templates suitable for [specific industry]?**

A: The templates are industry-agnostic but may need customization:
- **Healthcare**: Add HIPAA compliance sections
- **Finance**: Add PCI-DSS, SOX compliance
- **Government**: Add specific regulatory requirements
- **E-commerce**: Emphasize PCI-DSS, GDPR

Adapt to your industry's needs.

**Q: What about compliance requirements?**

A: The templates include sections for:
- GDPR (data privacy)
- HIPAA (healthcare)
- PCI-DSS (payment cards)
- SOC 2 (security)
- ISO 27001 (information security)
- WCAG (accessibility)

Add specific requirements for your domain.

## 🚀 Advanced Questions

**Q: How do I scale documentation for microservices?**

A:
- Create system-level HLD for overall architecture
- Create service-level HLD for each microservice
- Use API contracts as interfaces
- Document service dependencies
- Maintain architecture decision records (ADRs)

**Q: What about API documentation?**

A: 
- Use OpenAPI/Swagger for REST APIs
- Use GraphQL schema for GraphQL APIs
- Include API specs in FSD
- Reference from HLD
- Consider separate API documentation

**Q: How do I handle multi-phase projects?**

A:
- Create overall project BRD
- Create phase-specific documents
- Update incrementally
- Maintain traceability
- Review and consolidate after each phase

## 📞 Support Questions

**Q: Where can I get help?**

A:
- Review documentation in this repository
- Check examples (if available)
- Open GitHub Issues for bugs
- Use GitHub Discussions for questions
- Consult with experienced team members

**Q: How do I contribute?**

A: See [CONTRIBUTING.md](../CONTRIBUTING.md) for:
- How to submit improvements
- Template contribution guidelines
- Code review process
- Recognition for contributors

**Q: Can I use this commercially?**

A: Yes! The templates are licensed under MIT License:
- Free to use commercially
- Free to modify
- Free to distribute
- Attribution appreciated but not required

## 📝 Still Have Questions?

If your question isn't answered here:

1. Check the [README.md](../README.md) for overview
2. Review [TEMPLATE_USAGE_GUIDE.md](TEMPLATE_USAGE_GUIDE.md) for detailed usage
3. See [BEST_PRACTICES.md](BEST_PRACTICES.md) for recommendations
4. Open a [GitHub Discussion](https://github.com/siddjoshi/AI-SDLC/discussions)
5. Create a [GitHub Issue](https://github.com/siddjoshi/AI-SDLC/issues) if you found a problem

---

**We're here to help!** Don't hesitate to ask questions.
