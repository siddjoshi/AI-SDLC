# Documentation Directory

This directory contains comprehensive guides and generated documentation for AI-SDLC projects.

## 📂 Directory Structure

```
docs/
├── README.md                    # This file
├── TEMPLATE_USAGE_GUIDE.md      # Detailed guide on using templates
├── BEST_PRACTICES.md            # Best practices for SDLC documentation
├── FAQ.md                       # Frequently Asked Questions
├── diagrams/                    # Architecture diagrams (generated)
│   ├── system-context.md
│   ├── container-diagram.md
│   ├── component-diagram.md
│   ├── deployment-diagram.md
│   ├── data-flow.md
│   └── sequence-diagrams.md
├── BRD.md                       # Business Requirements Document (generated)
├── Functional_Spec.md           # Functional Specification (generated)
├── HLD.md                       # High-Level Design (generated)
└── NFR.md                       # Non-Functional Requirements (generated)
```

## 📚 Documentation Guides

### [Template Usage Guide](TEMPLATE_USAGE_GUIDE.md)
A comprehensive guide on how to effectively use the AI-SDLC templates. Includes:
- When to use each template
- Step-by-step instructions for filling templates
- Document relationships
- Quality checklist
- Tips for AI-assisted documentation

### [Best Practices](BEST_PRACTICES.md)
Best practices for creating and maintaining SDLC documentation. Covers:
- Documentation principles
- Writing best practices
- Diagram guidelines
- Security documentation
- Review and QA processes
- Maintenance strategies

### [FAQ](FAQ.md)
Frequently asked questions about AI-SDLC templates and processes. Includes:
- General questions about AI-SDLC
- Template-specific questions
- Process and workflow questions
- Technical questions about tools
- Industry-specific guidance

## 📝 Generated Documentation

When you use the AI-SDLC templates to document a project, the following files will be created in this directory:

### Business Requirements Document (BRD)
**File**: `BRD.md`

Captures business context, objectives, and high-level requirements. Created first in the documentation workflow.

### Functional Specification Document (FSD)
**File**: `Functional_Spec.md`

Details functional requirements, user stories, and system behavior. Created after BRD approval.

### High-Level Design Document (HLD)
**File**: `HLD.md`

Defines technical architecture and design approach. Created after FSD is complete.

### Architecture Diagrams
**Directory**: `diagrams/`

Visual representations of system architecture including:
- System Context Diagram
- Container Diagram
- Component Diagram
- Deployment Diagram
- Data Flow Diagram
- Sequence Diagrams

### Non-Functional Requirements (NFR)
**File**: `NFR.md`

Comprehensive non-functional requirements covering security, performance, accessibility, and quality attributes.

## 🚀 Quick Start

### For New Projects

1. **Copy templates from `/templates` directory**
   ```bash
   cp templates/BRD_Template.md docs/BRD.md
   cp templates/Functional_Spec_Template.md docs/Functional_Spec.md
   cp templates/HLD_Template.md docs/HLD.md
   cp templates/NFR_Template.md docs/NFR.md
   ```

2. **Follow the documentation workflow**
   - Start with BRD
   - Create FSD after BRD approval
   - Design HLD based on FSD
   - Create architecture diagrams
   - Define NFRs throughout the process

3. **Refer to guides**
   - Use [Template Usage Guide](TEMPLATE_USAGE_GUIDE.md) for detailed instructions
   - Follow [Best Practices](BEST_PRACTICES.md) for quality documentation
   - Check [FAQ](FAQ.md) for common questions

### For AI-Assisted Documentation

1. **Review [AGENTS.md](../AGENTS.md)** in the root directory for AI agent workflow

2. **Provide business requirements** to AI agent

3. **AI generates documentation** in this directory following the template structure

4. **Review and refine** AI-generated content

## 📋 Quality Checklist

Before finalizing documentation, ensure:

- [ ] All documents complete (no TBD items)
- [ ] Cross-references accurate
- [ ] Diagrams consistent with text
- [ ] Requirements have unique IDs
- [ ] Stakeholder approval obtained
- [ ] Version numbers updated
- [ ] Documents reviewed by appropriate teams

## 🔗 Document Relationships

```
BRD (Business Context)
  ↓
  Drives
  ↓
FSD (Functional Specs)
  ↓
  Informs
  ↓
HLD (Technical Design)
  ↓
  Visualized by
  ↓
Architecture Diagrams

NFR (Quality Attributes)
  ↓
  Constrains
  ↓
All Documents
```

## 🛠️ Maintenance

### Version Control

All documentation should be:
- Version controlled with Git
- Updated when requirements or design changes
- Reviewed regularly for accuracy
- Archived when superseded

### Update Schedule

Review and update documentation:
- When requirements change
- After design decisions
- At milestone completion
- During retrospectives
- Before major releases

## 📞 Need Help?

- **Template Usage**: See [TEMPLATE_USAGE_GUIDE.md](TEMPLATE_USAGE_GUIDE.md)
- **Best Practices**: See [BEST_PRACTICES.md](BEST_PRACTICES.md)
- **Questions**: See [FAQ.md](FAQ.md)
- **Issues**: Report on [GitHub Issues](https://github.com/siddjoshi/AI-SDLC/issues)
- **Discussions**: Join [GitHub Discussions](https://github.com/siddjoshi/AI-SDLC/discussions)

## 📄 License

Documentation created using AI-SDLC templates inherits the project's MIT License unless otherwise specified.

---

**Ready to start documenting?** Check out the [Template Usage Guide](TEMPLATE_USAGE_GUIDE.md) to get started!
