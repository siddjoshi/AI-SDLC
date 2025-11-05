---
mode: agent
---

# GitHub Feature Generation Instructions

## Task Definition

Create GitHub Issues as Features based on the `/docs/Features.md` file. Each feature should be properly structured, labeled, and formatted according to industry standards for agile development. Features must be linked to their parent Epics using GitHub's issue-sub-issue relationship functionality.

## Prerequisites

Before generating features, ensure:
- [ ] `/docs/Features.md` file exists and contains well-defined feature descriptions
- [ ] Parent Epic issues have been created and are available in the repository
- [ ] GitHub repository access is available with permissions to create issues and sub-issues
- [ ] Proper labels exist in the repository (create if missing)
- [ ] Epic-to-Feature mapping is clearly defined in the Features.md file

## Feature Creation Standards

### Feature Structure Format

Each GitHub Issue representing a Feature must follow this structure:

```markdown
# Feature: [Feature Title]

## Feature Summary
Brief description of what this feature provides to users (1-2 sentences)

## Parent Epic
🔗 **Related Epic:** [Link to parent epic issue]

## Business Value
- **User Benefit:** How this feature benefits end users
- **Business Impact:** How this feature supports business objectives
- **Priority Justification:** Why this feature is prioritized at this level

## User Stories
### Primary User Stories
- As a [user type], I want [functionality] so that [benefit]
- As a [user type], I want [functionality] so that [benefit]

### Secondary User Stories (if applicable)
- As a [user type], I want [functionality] so that [benefit]

## Functional Requirements
### Core Functionality
1. **Requirement 1:** [Detailed functional requirement]
2. **Requirement 2:** [Detailed functional requirement]
3. **Requirement 3:** [Detailed functional requirement]

### User Interface Requirements
- UI Element 1: [Description and behavior]
- UI Element 2: [Description and behavior]
- Responsive design requirements
- Accessibility requirements (WCAG 2.1 AA)

### Data Requirements
- Input data: [What data is required]
- Output data: [What data is produced]
- Data validation rules
- Data persistence requirements

## Acceptance Criteria
### Functional Acceptance Criteria
- [ ] **Given** [initial condition] **When** [action] **Then** [expected result]
- [ ] **Given** [initial condition] **When** [action] **Then** [expected result]
- [ ] **Given** [initial condition] **When** [action] **Then** [expected result]

### Non-Functional Acceptance Criteria
- [ ] Performance: [Specific performance requirements]
- [ ] Security: [Security requirements and validations]
- [ ] Accessibility: [WCAG 2.1 AA compliance checkpoints]
- [ ] Browser compatibility: [Supported browsers and versions]
- [ ] Mobile responsiveness: [Mobile device requirements]

## Definition of Done
- [ ] Feature implementation completed
- [ ] Unit tests written and passing (minimum 80% coverage)
- [ ] Integration tests passing
- [ ] User acceptance testing completed
- [ ] Security testing completed
- [ ] Performance testing meets requirements
- [ ] Accessibility testing passed (WCAG 2.1 AA)
- [ ] Code review completed and approved
- [ ] Documentation updated (user and technical)
- [ ] Feature deployed to staging environment
- [ ] Product owner sign-off received

## Technical Implementation Notes
### Architecture Considerations
- [Technical approach and design patterns]
- [Database schema changes if applicable]
- [API endpoints and contracts]
- [Third-party integrations required]

### Technology Stack
- Frontend: [Technologies and frameworks]
- Backend: [Technologies and frameworks]
- Database: [Database changes or additions]
- External Services: [APIs, services, or tools needed]

## Dependencies
### Feature Dependencies
- **Depends on Feature:** [Link to prerequisite feature]
- **Blocks Feature:** [Link to dependent feature]

### Technical Dependencies
- Library/Framework: [Name and version]
- Infrastructure: [Required infrastructure changes]
- Third-party Service: [External service dependencies]

### Epic Dependencies
- **Parent Epic:** [Link to parent epic]
- **Related Epics:** [Links to related epics if applicable]

## Assumptions
1. **Technical Assumption:** [Description and validation needed]
2. **Business Assumption:** [Description and validation needed]
3. **User Assumption:** [Description and validation needed]

## Constraints
### Technical Constraints
- Technology limitation: [Description and impact]
- Performance constraint: [Specific limitations]
- Security constraint: [Security requirements and limitations]

### Business Constraints
- Budget constraint: [Financial limitations]
- Timeline constraint: [Delivery deadlines]
- Resource constraint: [Team or skill limitations]

## Success Metrics
### Key Performance Indicators (KPIs)
- **Usage Metric:** [How feature adoption will be measured]
- **Performance Metric:** [Performance benchmarks]
- **Business Metric:** [Business value measurement]

### Analytics and Monitoring
- Events to track: [User interaction events]
- Dashboards to create: [Monitoring dashboards needed]
- Alerts to set up: [Performance or error alerts]

## Testing Strategy
### Test Types Required
- [ ] Unit Testing (Backend)
- [ ] Unit Testing (Frontend)
- [ ] Integration Testing
- [ ] API Testing
- [ ] UI/UX Testing
- [ ] Performance Testing
- [ ] Security Testing
- [ ] Accessibility Testing
- [ ] Browser Compatibility Testing
- [ ] Mobile Testing

### Test Scenarios
1. **Happy Path:** [Primary use case testing]
2. **Edge Cases:** [Boundary condition testing]
3. **Error Handling:** [Error scenario testing]
4. **Performance:** [Load and stress testing]

## Risks and Mitigation
### Technical Risks
- **Risk:** [Technical risk description] | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]
- **Risk:** [Technical risk description] | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]

### Business Risks
- **Risk:** [Business risk description] | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]
- **Risk:** [Business risk description] | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]

## Estimated Effort
- **Story Points:** [Fibonacci scale: 1, 2, 3, 5, 8, 13]
- **Development Time:** [Estimated hours/days]
- **Testing Time:** [Estimated testing effort]
- **Total Time:** [End-to-end delivery estimate]
- **Team Members Required:** [Developers, testers, designers needed]

## Implementation Plan
### Phase 1: Foundation
- [ ] [Task 1]
- [ ] [Task 2]

### Phase 2: Core Development
- [ ] [Task 1]
- [ ] [Task 2]

### Phase 3: Testing & Refinement
- [ ] [Task 1]
- [ ] [Task 2]
```

## Required Labels

Each feature issue must have the following labels:

### Primary Labels
- `feature` - Identifies this as a feature-level issue
- `priority:high|medium|low` - Business priority level
- `effort:small|medium|large` - Estimated effort level (mapped from story points)

### Category Labels (choose appropriate ones)
- `enhancement` - Improvement to existing functionality
- `new-feature` - Brand new functionality
- `user-interface` - UI/UX related work
- `api` - API development work
- `integration` - Third-party integration
- `performance` - Performance optimization
- `security` - Security-related feature
- `accessibility` - Accessibility improvements

### Domain Labels (choose appropriate ones)
- `frontend` - Frontend implementation required
- `backend` - Backend implementation required
- `fullstack` - Both frontend and backend work
- `database` - Database changes required
- `mobile` - Mobile-specific implementation
- `web` - Web-specific implementation

### Status Labels
- `status:planned` - Feature is planned but not started
- `status:ready` - Feature is ready for development
- `status:in-progress` - Feature is actively being developed
- `status:review` - Feature is in review phase
- `status:testing` - Feature is in testing phase
- `status:blocked` - Feature is blocked by dependencies

### Team Labels (assign as appropriate)
- `team:frontend` - Frontend team assignment
- `team:backend` - Backend team assignment
- `team:fullstack` - Full-stack team assignment
- `team:qa` - QA team involvement required

## Feature Generation Workflow

### Step 1: Parse Features.md
1. Read and analyze the `/docs/Features.md` file
2. Extract each feature definition including:
   - Feature title and description
   - Parent epic relationship
   - User stories and requirements
   - Technical specifications
   - Dependencies and constraints

### Step 2: Map Features to Epics
1. **Identify Parent Epic:** Match each feature to its parent epic
2. **Validate Epic Exists:** Ensure parent epic issue exists in GitHub
3. **Get Epic Issue Number:** Retrieve the GitHub issue number for the parent epic
4. **Prepare Sub-Issue Relationship:** Ready the feature for linking as a sub-issue

### Step 3: Create Feature Issues
For each feature in the Features.md file:

1. **Create GitHub Issue** with the feature structure format
2. **Set Title** using pattern: `Feature: [Feature Name]`
3. **Apply Labels** according to the labeling standards
4. **Link to Parent Epic** using GitHub's sub-issue functionality
5. **Set Milestone** to match parent epic milestone
6. **Assign Feature Owner** if specified
7. **Link Dependencies** to other features or technical dependencies

### Step 4: Establish Sub-Issue Relationships
For each created feature:

1. **Add as Sub-Issue to Epic:** Use GitHub API to create parent-child relationship
2. **Update Epic:** Add feature reference to parent epic description
3. **Cross-Reference:** Ensure bidirectional linking between epic and feature
4. **Validate Hierarchy:** Confirm the epic-feature hierarchy is properly established

### Step 5: Quality Validation
Ensure each created feature:
- [ ] Has clear, testable acceptance criteria in Given/When/Then format
- [ ] Includes comprehensive functional and non-functional requirements
- [ ] Contains realistic effort estimates and implementation plan
- [ ] Has appropriate labels applied correctly
- [ ] Is properly linked to parent epic as a sub-issue
- [ ] Follows the standard feature template structure
- [ ] Includes proper testing strategy and success metrics

## Industry Standards Compliance

### Agile/Scrum Standards
- Follow SAFe (Scaled Agile Framework) feature guidelines
- Align with Scrum guide principles for product backlog items
- Use standard story point estimation (1, 2, 3, 5, 8, 13)
- Follow Definition of Ready and Definition of Done practices

### Feature Size Guidelines
- **Small Feature:** 1-2 weeks, 3-8 story points
- **Medium Feature:** 2-4 weeks, 8-13 story points
- **Large Feature:** 1-2 months, 13-21 story points
- **Too Large:** Should be broken down into smaller features

### INVEST Criteria for Features
Ensure each feature is:
- **Independent:** Can be developed and deployed independently
- **Negotiable:** Details can be refined during development
- **Valuable:** Provides clear value to users and business
- **Estimable:** Can be reasonably estimated by the development team
- **Small:** Appropriately sized for a development iteration
- **Testable:** Has clear, verifiable acceptance criteria

### User Story Standards
- Follow the "As a [user], I want [functionality], so that [benefit]" format
- Include acceptance criteria in Given/When/Then format
- Ensure stories are from the user's perspective
- Include both happy path and edge case scenarios

## Epic-Feature Relationship Management

### Sub-Issue Hierarchy
```
Epic (Parent Issue)
├── Feature 1 (Sub-Issue)
├── Feature 2 (Sub-Issue)
├── Feature 3 (Sub-Issue)
└── Feature N (Sub-Issue)
```

### Relationship Creation Process
1. **Create Feature Issue:** Standard GitHub issue creation
2. **Add Sub-Issue Relationship:** Use GitHub API or interface to link feature to epic
3. **Update Epic Progress:** Epic completion tracks sub-issue completion
4. **Maintain Traceability:** Ensure clear parent-child relationship visibility

### Dependency Management
- **Feature-to-Feature:** Use GitHub issue references and dependency labels
- **Feature-to-Epic:** Automatic through sub-issue relationship
- **Cross-Epic Dependencies:** Use issue references with clear documentation

## Automation Instructions

When generating features programmatically:

1. **Read Features File:** Parse `/docs/Features.md` systematically
2. **Extract Feature Data:** Pull out all feature details and epic mappings
3. **Validate Epic Existence:** Confirm parent epics exist in GitHub
4. **Apply Template:** Use the standard feature structure for each issue
5. **Create GitHub Issues:** Use GitHub API to create feature issues
6. **Establish Sub-Issue Links:** Create parent-child relationships with epics
7. **Apply Labels:** Automatically apply appropriate labels based on feature content
8. **Set Assignments:** Assign features to appropriate team members
9. **Validate Creation:** Confirm all features were created and linked successfully

## Error Handling

### Common Error Scenarios
- **Missing Features.md:** Prompt user to create the file first
- **Parent Epic Not Found:** Create epic first or provide clear error message
- **Insufficient Permissions:** Ensure GitHub API permissions for issue creation and sub-issue linking
- **Label Creation Failure:** Create missing labels automatically
- **Sub-Issue Link Failure:** Retry mechanism and fallback to manual reference
- **Incomplete Feature Definition:** Flag for manual review and completion

### Recovery Strategies
- Batch processing with rollback capability
- Detailed logging of creation process
- Validation checkpoints throughout the process
- Manual verification steps for critical relationships

## Success Criteria

Feature generation is successful when:
- [ ] All features from `/docs/Features.md` are created as GitHub Issues
- [ ] Each feature follows the standard structure template
- [ ] All required labels are applied correctly
- [ ] Features are properly linked to parent epics as sub-issues
- [ ] Dependencies between features are properly documented
- [ ] Feature owners are assigned where specified
- [ ] All features pass the INVEST criteria validation
- [ ] No duplicate features are created
- [ ] Epic-feature hierarchy is properly established and visible
- [ ] All acceptance criteria are clear and testable
- [ ] Implementation plans are realistic and actionable

## Post-Generation Tasks

After feature creation:
1. **Review Feature-Epic Relationships:** Ensure all links are properly established
2. **Validate Feature Completeness:** Check that all features have complete information
3. **Confirm Team Assignments:** Verify appropriate team members are assigned
4. **Review Dependencies:** Ensure feature dependencies are accurately captured
5. **Schedule Feature Refinement:** Plan backlog refinement sessions with teams
6. **Create Feature Roadmap:** Develop timeline based on epic priorities and feature dependencies
7. **Set Up Monitoring:** Establish tracking for feature progress and completion

## Integration with Epic Management

### Epic Progress Tracking
- Epic completion percentage based on sub-issue (feature) completion
- Automatic epic status updates based on feature progress
- Epic milestone updates based on feature delivery dates

### Epic-Feature Consistency
- Feature priorities align with epic priorities
- Feature timelines support epic delivery dates
- Feature assignments support epic team allocation

## Templates and References

### Feature Template Location
The feature template structure should be consistent across all generated issues and align with epic templates.

### Reference Standards
- User Story best practices (Mike Cohn, Roman Pichler)
- SAFe Feature definition guidelines
- Scrum Product Backlog Item standards
- GitHub Issues and Projects best practices
- INVEST criteria for user stories and features

### Documentation Links
- Link to parent epic for context
- Link to `/docs/BRD.md` for business requirements
- Link to `/docs/Features.md` source document
- Link to technical architecture documentation
- Link to design specifications and mockups

## Quality Assurance Checklist

Before marking feature generation complete:
- [ ] All features from Features.md are created
- [ ] Feature-epic relationships are established
- [ ] All labels are applied correctly
- [ ] Acceptance criteria are written in proper format
- [ ] Effort estimates are realistic
- [ ] Dependencies are clearly documented
- [ ] Team assignments are appropriate
- [ ] Success metrics are defined and measurable
- [ ] Testing strategy is comprehensive
- [ ] Implementation plan is actionable
- [ ] Risk mitigation strategies are documented