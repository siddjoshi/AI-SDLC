---
mode: agent
---

# GitHub Epic Generation Instructions

## Task Definition

Create GitHub Issues as Epics based on the `/docs/Epics.md` and `/docs/HLD.md` (High-Level Design)files. Each epic should be properly structured, labeled, and formatted according to industry standards for agile development and GitHub project management.

## Prerequisites

Before generating epics, ensure:
- [ ] `/docs/Epics.md` file exists and contains well-defined epic descriptions
- [ ] GitHub repository access is available
- [ ] Proper labels exist in the repository (create if missing)

## Epic Creation Standards

### Epic Structure Format

Each GitHub Issue representing an Epic must follow this structure:

```markdown
# Epic: [Epic Title]

## Epic Summary
Brief description of what this epic aims to achieve (1-2 sentences)

## Business Value
Explain the business value and why this epic is important to stakeholders

## User Stories Overview
High-level user stories that will be part of this epic:
- As a [user type], I want [functionality] so that [benefit]
- As a [user type], I want [functionality] so that [benefit]

## Acceptance Criteria
- [ ] Criterion 1: Clear, testable condition
- [ ] Criterion 2: Clear, testable condition
- [ ] Criterion 3: Clear, testable condition

## Definition of Done
- [ ] All user stories completed and tested
- [ ] Documentation updated
- [ ] Security requirements met
- [ ] Performance requirements met
- [ ] Accessibility requirements met (WCAG 2.1 AA)
- [ ] Code review completed
- [ ] Integration testing passed

## Dependencies
- Dependency on Epic: [Link to related epic]
- External dependency: [Description]

## Assumptions
- Assumption 1: [Description]
- Assumption 2: [Description]

## Constraints
- Technical constraint: [Description]
- Business constraint: [Description]

## Success Metrics
- Metric 1: [How success will be measured]
- Metric 2: [Quantifiable outcome]

## Technical Notes
[Any technical considerations, architecture notes, or implementation guidance]

## Risks and Mitigation
- Risk: [Description] | Mitigation: [Strategy]
- Risk: [Description] | Mitigation: [Strategy]

## Estimated Effort
- Story Points: [Estimate]
- Time Frame: [Duration estimate]
- Team Size: [Number of developers needed]
```

## Required Labels

Each epic issue must have the following labels:

### Primary Labels
- `epic` - Identifies this as an epic-level issue
- `priority:high|medium|low` - Business priority level
- `effort:small|medium|large|x-large` - Estimated effort level

### Category Labels (choose appropriate ones)
- `feature` - New functionality
- `enhancement` - Improvement to existing functionality
- `infrastructure` - Technical infrastructure work
- `security` - Security-related work
- `performance` - Performance optimization
- `accessibility` - Accessibility improvements
- `integration` - Third-party integration work

### Domain Labels (choose appropriate ones)
- `frontend` - UI/UX related work
- `backend` - Server-side work
- `database` - Data layer work
- `api` - API development
- `mobile` - Mobile application work
- `devops` - DevOps and deployment

### Status Labels
- `status:planned` - Epic is planned but not started
- `status:in-progress` - Epic is actively being worked on
- `status:blocked` - Epic is blocked by dependencies
- `status:review` - Epic is in review phase

## Epic Generation Workflow

### Step 1: Parse Epics.md
1. Read and analyze the `/docs/Epics.md` file
2. Extract each epic definition including:
   - Epic title and description
   - Business objectives
   - Key requirements
   - Dependencies
   - Success criteria

### Step 2: Create Epic Issues
For each epic in the Epics.md file:

1. **Create GitHub Issue** with the epic structure format
2. **Set Title** using pattern: `Epic: [Epic Name]`
3. **Apply Labels** according to the labeling standards
4. **Set Milestone** if applicable
5. **Assign Epic Owner** if specified
6. **Link Dependencies** to other epics or issues

### Step 3: Quality Validation
Ensure each created epic:
- [ ] Has clear, measurable acceptance criteria
- [ ] Includes proper business value statement
- [ ] Contains realistic effort estimates
- [ ] Has appropriate labels applied
- [ ] Links to related epics or dependencies
- [ ] Follows the standard epic template structure

## Industry Standards Compliance

### Agile/Scrum Standards
- Follow SAFe (Scaled Agile Framework) epic guidelines
- Align with Scrum guide principles
- Use standard story point estimation (1, 2, 3, 5, 8, 13, 21)

### Epic Size Guidelines
- **Small Epic:** 1-3 months, 20-50 story points
- **Medium Epic:** 3-6 months, 50-100 story points
- **Large Epic:** 6-12 months, 100-200 story points
- **X-Large Epic:** Should be broken down into smaller epics

### INVEST Criteria
Ensure each epic is:
- **Independent:** Can be developed independently
- **Negotiable:** Details can be negotiated
- **Valuable:** Provides clear business value
- **Estimable:** Can be reasonably estimated
- **Small:** Appropriately sized for development team
- **Testable:** Has clear acceptance criteria

## Automation Instructions

When generating epics programmatically:

1. **Read Epics File:** Parse `/docs/Epics.md` systematically
2. **Extract Information:** Pull out key data points for each epic
3. **Apply Template:** Use the standard epic structure for each issue
4. **Create Issues:** Use GitHub API to create issues with proper formatting
5. **Apply Labels:** Automatically apply appropriate labels based on epic content
6. **Link Related Items:** Create relationships between dependent epics
7. **Validate Creation:** Confirm all epics were created successfully

## Error Handling

- If `/docs/Epics.md` is missing, prompt user to create it first
- If required labels don't exist, create them before generating epics
- If epic descriptions are incomplete, flag for manual review
- If dependencies can't be resolved, create issues without links and note in comments

## Success Criteria

Epic generation is successful when:
- [ ] All epics from `/docs/Epics.md` are created as GitHub Issues
- [ ] Each epic follows the standard structure template
- [ ] All required labels are applied correctly
- [ ] Dependencies between epics are properly linked
- [ ] Epic owners are assigned where specified
- [ ] All epics pass the INVEST criteria validation
- [ ] No duplicate epics are created
- [ ] All technical notes and constraints are properly documented

## Post-Generation Tasks

After epic creation:
1. Review all created epics for completeness
2. Ensure epic hierarchy and dependencies are correct
3. Validate that effort estimates align with team capacity
4. Confirm that success metrics are measurable
5. Schedule epic refinement sessions with stakeholders
6. Create epic roadmap based on priorities and dependencies

## Templates and References

### Epic Template Location
The epic template structure should be consistent across all generated issues.

### Reference Standards
- JIRA Epic standards
- Azure DevOps Epic best practices
- SAFe Epic definition guidelines
- GitHub Issues best practices

### Documentation Links
- Link to `/docs/BRD.md` for business context
- Link to project roadmap for timeline context
- Link to technical architecture for implementation guidance