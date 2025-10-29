# Quick Reference Guide

## 🚀 Getting Started in 5 Minutes

### For Manual Use

```bash
# 1. Clone the repository
git clone https://github.com/siddjoshi/AI-SDLC.git
cd AI-SDLC

# 2. Copy templates you need
cp templates/BRD_Template.md docs/BRD.md
cp templates/Functional_Spec_Template.md docs/Functional_Spec.md
cp templates/HLD_Template.md docs/HLD.md
cp templates/NFR_Template.md docs/NFR.md

# 3. Start filling out templates
# Open docs/BRD.md in your editor and start documenting!
```

### For AI-Assisted Use

1. Provide your business requirement
2. Request "Plan and Design" documentation
3. Review and refine generated documentation

## 📚 Templates at a Glance

| Template | Purpose | When to Use | Output |
|----------|---------|-------------|--------|
| **BRD** | Business requirements and objectives | Project start | `docs/BRD.md` |
| **FSD** | Detailed functional specifications | After BRD approval | `docs/Functional_Spec.md` |
| **HLD** | Technical architecture and design | After FSD completion | `docs/HLD.md` |
| **Architecture Diagrams** | Visual system representations | During HLD | `docs/diagrams/*.md` |
| **NFR** | Quality attributes and constraints | Throughout process | `docs/NFR.md` |

## 📋 Documentation Workflow

```
1. BRD          →  Define business needs
   ↓
2. FSD          →  Specify features and functions
   ↓
3. HLD          →  Design technical architecture
   ↓
4. Diagrams     →  Visualize architecture
   ↓
5. NFR          →  Define quality requirements
```

## 🔑 Key Sections Quick Reference

### Business Requirements Document (BRD)
- Executive Summary
- Business Objectives
- Stakeholders
- Scope (in/out)
- Business Process (As-Is/To-Be)
- High-Level Requirements
- Cost-Benefit Analysis
- Risks

### Functional Specification Document (FSD)
- System Overview
- Feature Specifications
- User Stories
- UI Specifications
- Data Models
- API Specifications
- Error Handling
- Testing Requirements

### High-Level Design Document (HLD)
- Architecture Style
- Technology Stack
- System Layers
- Component Design
- Data Design
- Security Design
- Performance Design
- Deployment Architecture

### Non-Functional Requirements (NFR)
- Security (Authentication, Authorization, Encryption, Compliance)
- Performance (Response Time, Throughput, Scalability)
- Accessibility (WCAG 2.1 Level AA)
- Quality Attributes (Availability, Reliability, Maintainability)

## ✅ Quality Checklist (Quick)

Before finalizing:
- [ ] All sections complete
- [ ] Requirements have IDs
- [ ] Acceptance criteria defined
- [ ] Diagrams included
- [ ] Reviewed by team
- [ ] Stakeholder approval

## 🛠️ Essential Tools

- **Markdown Editor**: VS Code, Typora, Obsidian
- **Diagrams**: Draw.io, PlantUML, Mermaid
- **Version Control**: Git
- **Collaboration**: GitHub, GitLab, Confluence

## 📖 Common Commands

```bash
# Create project structure
mkdir -p my-project/docs/diagrams

# Copy all templates
cp templates/*.md my-project/docs/

# Convert Markdown to PDF
pandoc docs/BRD.md -o BRD.pdf

# Check for TBDs
grep -r "TBD\|TODO" docs/
```

## 🔗 Quick Links

- **Full Documentation**: [README.md](README.md)
- **Template Guide**: [docs/TEMPLATE_USAGE_GUIDE.md](docs/TEMPLATE_USAGE_GUIDE.md)
- **Best Practices**: [docs/BEST_PRACTICES.md](docs/BEST_PRACTICES.md)
- **FAQ**: [docs/FAQ.md](docs/FAQ.md)
- **Contributing**: [CONTRIBUTING.md](CONTRIBUTING.md)

## 💡 Pro Tips

1. **Start with BRD** - It's the foundation for everything else
2. **Be Specific** - Vague requirements lead to vague solutions
3. **Include Examples** - They clarify complex concepts
4. **Update Often** - Keep documentation current
5. **Review Early** - Get feedback before too much work is done

## 🎯 Document Priorities

**Must Have:**
- Business objectives (BRD)
- Core functional requirements (FSD)
- System architecture (HLD)
- Security requirements (NFR)

**Should Have:**
- Detailed feature specs (FSD)
- Performance targets (NFR)
- Architecture diagrams
- API specifications (FSD)

**Nice to Have:**
- Process flow diagrams
- Detailed UI mockups
- Comprehensive error scenarios
- Migration strategy

## 📊 Requirement Priority Levels

- **High**: Critical for project success
- **Medium**: Important but not critical
- **Low**: Desirable but optional

## 🔒 Security Essentials

Always document:
1. Authentication mechanism
2. Authorization model
3. Data encryption (at rest & in transit)
4. Input validation
5. Security logging
6. Compliance requirements

## ⚡ Performance Essentials

Always specify:
1. Response time targets
2. Throughput requirements
3. Concurrent user capacity
4. Resource limits (CPU, memory)
5. Scalability approach

## ♿ Accessibility Essentials

Always include:
1. WCAG compliance level (AA recommended)
2. Keyboard navigation support
3. Screen reader compatibility
4. Color contrast requirements
5. Alternative text for images

## 🆘 Quick Help

**Question Type** | **Resource**
---|---
How to use templates? | [Template Usage Guide](docs/TEMPLATE_USAGE_GUIDE.md)
Best practices? | [Best Practices](docs/BEST_PRACTICES.md)
Specific questions? | [FAQ](docs/FAQ.md)
Found a bug? | [GitHub Issues](https://github.com/siddjoshi/AI-SDLC/issues)
General discussion? | [GitHub Discussions](https://github.com/siddjoshi/AI-SDLC/discussions)

## 📞 Need More Help?

1. Check the [FAQ](docs/FAQ.md) first
2. Review the [Template Usage Guide](docs/TEMPLATE_USAGE_GUIDE.md)
3. Read [Best Practices](docs/BEST_PRACTICES.md)
4. Open a [GitHub Discussion](https://github.com/siddjoshi/AI-SDLC/discussions)

---

**Ready to document?** Start with the [BRD Template](templates/BRD_Template.md)!
