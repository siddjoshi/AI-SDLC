---
mode: agent
---

# GitHub Task Generation Instructions

## Task Definition

Create GitHub Issues as Tasks based on the features defined in `/docs/Features.md` file. Each task should be properly structured, labeled, and formatted according to industry standards for agile development. Tasks must be linked to their parent Features using GitHub's issue-sub-issue relationship functionality, creating a complete hierarchy: Epic → Feature → Task.

## Prerequisites

Before generating tasks, ensure:
- [ ] `/docs/Features.md` file exists and contains well-defined feature descriptions
- [ ] Parent Feature issues have been created and are available in the repository
- [ ] Epic-Feature relationships are properly established
- [ ] GitHub repository access is available with permissions to create issues and sub-issues
- [ ] Proper labels exist in the repository (create if missing)
- [ ] Feature-to-Task breakdown is clearly defined or can be derived from feature requirements

## Task Creation Standards

### Task Structure Format

Each GitHub Issue representing a Task must follow this structure:

```markdown
# Task: [Task Title]

## Task Summary
Brief description of what this specific task accomplishes (1 sentence)

## Parent Feature
🔗 **Related Feature:** [Link to parent feature issue]
🔗 **Parent Epic:** [Link to grandparent epic issue]

## Task Type
- [ ] Development Task
- [ ] Testing Task
- [ ] Documentation Task
- [ ] Design Task
- [ ] Research Task
- [ ] Configuration Task
- [ ] Deployment Task

## Description
### What needs to be done
[Detailed description of the specific work to be completed]

### Why this task is needed
[Connection to feature requirements and business value]

### Scope of work
[Clear boundaries of what is included and excluded]

## Acceptance Criteria
### Task Completion Criteria
- [ ] **Given** [precondition] **When** [action performed] **Then** [expected outcome]
- [ ] **Given** [precondition] **When** [action performed] **Then** [expected outcome]
- [ ] **Given** [precondition] **When** [action performed] **Then** [expected outcome]

### Quality Gates
- [ ] Code follows team coding standards
- [ ] Unit tests written and passing (if applicable)
- [ ] Code review completed (if applicable)
- [ ] Documentation updated (if applicable)
- [ ] Security considerations addressed
- [ ] Performance implications considered

## Technical Details
### Implementation Approach
- **Method/Technology:** [Specific approach to be used]
- **Files to be modified:** [List of files that will be changed]
- **Components affected:** [System components impacted]
- **APIs involved:** [External or internal APIs used]

### Technical Requirements
- **Programming Language:** [Language to be used]
- **Framework/Library:** [Specific frameworks or libraries]
- **Database Changes:** [Schema changes if applicable]
- **Configuration Changes:** [Config files to be modified]

### Code Structure
```
[Provide basic code structure or pseudocode if helpful]
```

## Dependencies
### Task Dependencies
- **Depends on Task:** [Link to prerequisite task]
- **Blocks Task:** [Link to dependent task]

### Feature Dependencies
- **Parent Feature:** [Link to parent feature]
- **Related Features:** [Links to related features if applicable]

### Technical Dependencies
- **Environment Setup:** [Required environment or tools]
- **External Services:** [Third-party dependencies]
- **Infrastructure:** [Required infrastructure components]

## Testing Requirements
### Test Types Required
- [ ] Unit Tests
- [ ] Integration Tests
- [ ] Manual Testing
- [ ] Automated Testing
- [ ] Performance Testing
- [ ] Security Testing
- [ ] Accessibility Testing
- [ ] Browser/Device Testing

### Test Scenarios
1. **Primary Test Case:** [Main functionality test]
2. **Edge Cases:** [Boundary conditions to test]
3. **Error Scenarios:** [Error handling tests]
4. **Integration Points:** [Integration testing scenarios]

### Test Data Requirements
- **Input Data:** [Required test data]
- **Expected Output:** [Expected results]
- **Test Environment:** [Environment needed for testing]

## Definition of Done
### Development Tasks
- [ ] Code implemented according to specifications
- [ ] Unit tests written and passing (minimum 80% coverage)
- [ ] Code follows team standards and style guide
- [ ] Code review completed and approved
- [ ] Integration tests passing
- [ ] Documentation updated
- [ ] No high or critical security vulnerabilities
- [ ] Performance meets requirements
- [ ] Changes deployed to development environment

### Testing Tasks
- [ ] Test cases designed and documented
- [ ] Test execution completed
- [ ] Defects identified and documented
- [ ] Test results documented and shared
- [ ] Test automation implemented (if applicable)
- [ ] Regression testing completed
- [ ] Test environment cleaned up

### Documentation Tasks
- [ ] Documentation written and reviewed
- [ ] Documentation follows team standards
- [ ] Technical accuracy verified
- [ ] Documentation published to appropriate location
- [ ] Stakeholders notified of documentation updates

### Design Tasks
- [ ] Design specifications completed
- [ ] Design review conducted with stakeholders
- [ ] Design approved by product owner
- [ ] Design assets delivered in required formats
- [ ] Design system updated (if applicable)
- [ ] Accessibility requirements addressed

## Effort Estimation
- **Story Points:** [Fibonacci scale: 1, 2, 3, 5, 8]
- **Hours Estimate:** [Realistic time estimate]
- **Complexity Level:** [Simple/Medium/Complex]
- **Skill Level Required:** [Junior/Mid/Senior level]

## Implementation Details
### Step-by-Step Plan
1. **Preparation Phase**
   - [ ] [Specific preparation step]
   - [ ] [Specific preparation step]

2. **Implementation Phase**
   - [ ] [Specific implementation step]
   - [ ] [Specific implementation step]
   - [ ] [Specific implementation step]

3. **Testing Phase**
   - [ ] [Specific testing step]
   - [ ] [Specific testing step]

4. **Completion Phase**
   - [ ] [Specific completion step]
   - [ ] [Specific completion step]

### Technical Considerations
- **Performance Impact:** [Expected performance implications]
- **Security Considerations:** [Security aspects to address]
- **Scalability Impact:** [How this affects system scalability]
- **Maintainability:** [Impact on code maintainability]

## Resources Required
### Team Members
- **Primary Assignee:** [Developer/Tester/Designer responsible]
- **Reviewer:** [Code reviewer or approver]
- **Stakeholders:** [People who need to be informed/consulted]

### Tools and Environment
- **Development Tools:** [IDEs, libraries, frameworks needed]
- **Testing Tools:** [Testing frameworks and tools]
- **Environment Access:** [Required system access]
- **Documentation Tools:** [Tools for documentation]

## Risks and Mitigation
### Technical Risks
- **Risk:** [Technical risk description] | **Probability:** High/Medium/Low | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]

### Dependencies Risks
- **Risk:** [Dependency risk description] | **Probability:** High/Medium/Low | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]

### Timeline Risks
- **Risk:** [Timeline risk description] | **Probability:** High/Medium/Low | **Impact:** High/Medium/Low | **Mitigation:** [Strategy]

## Success Metrics
### Completion Indicators
- **Functional Success:** [How to measure functional completion]
- **Quality Success:** [Quality metrics to achieve]
- **Performance Success:** [Performance benchmarks to meet]

### Validation Criteria
- **Stakeholder Approval:** [Who needs to approve completion]
- **Testing Success:** [Testing criteria for success]
- **Integration Success:** [Integration validation criteria]
```

## Required Labels

Each task issue must have the following labels:

### Primary Labels
- `task` - Identifies this as a task-level issue
- `priority:high|medium|low` - Task priority level
- `effort:xs|small|medium|large` - Effort estimation (XS=1-2hrs, Small=3-8hrs, Medium=1-2days, Large=3-5days)

### Task Type Labels (choose one)
- `task:development` - Development/coding task
- `task:testing` - Testing and QA task
- `task:documentation` - Documentation task
- `task:design` - UI/UX design task
- `task:research` - Research and investigation task
- `task:configuration` - Configuration and setup task
- `task:deployment` - Deployment and release task
- `task:bug-fix` - Bug fixing task
- `task:refactor` - Code refactoring task

### Technical Domain Labels (choose appropriate ones)
- `frontend` - Frontend implementation
- `backend` - Backend implementation
- `database` - Database related work
- `api` - API development or integration
- `ui` - User interface work
- `ux` - User experience work
- `mobile` - Mobile-specific work
- `web` - Web-specific work
- `devops` - DevOps and infrastructure
- `security` - Security-related work
- `performance` - Performance optimization
- `accessibility` - Accessibility improvements

### Status Labels
- `status:ready` - Task is ready to be worked on
- `status:in-progress` - Task is actively being worked on
- `status:review` - Task is in review phase
- `status:testing` - Task is being tested
- `status:blocked` - Task is blocked by dependencies
- `status:done` - Task is completed

### Team Assignment Labels
- `team:frontend` - Frontend team assignment
- `team:backend` - Backend team assignment
- `team:qa` - QA team assignment
- `team:design` - Design team assignment
- `team:devops` - DevOps team assignment

## Task Generation Workflow

### Step 1: Parse Features from Features.md
1. Read and analyze the `/docs/Features.md` file
2. Extract each feature and its detailed requirements
3. Identify functional and technical components that need tasks
4. Map features to their parent epics for context

### Step 2: Break Down Features into Tasks
For each feature, identify tasks across these categories:

#### Development Tasks
- Frontend implementation tasks
- Backend API development tasks
- Database schema and query tasks
- Integration tasks
- Configuration tasks

#### Testing Tasks
- Unit test creation tasks
- Integration test tasks
- Manual testing tasks
- Performance testing tasks
- Security testing tasks
- Accessibility testing tasks

#### Documentation Tasks
- Technical documentation tasks
- User documentation tasks
- API documentation tasks
- Setup/deployment guide tasks

#### Design Tasks
- UI mockup creation tasks
- UX flow design tasks
- Design system updates tasks
- Asset creation tasks

#### Research Tasks
- Technical research tasks
- User research tasks
- Market research tasks
- Feasibility study tasks

### Step 3: Create Task Issues
For each identified task:

1. **Create GitHub Issue** with the task structure format
2. **Set Title** using pattern: `Task: [Specific Task Description]`
3. **Apply Labels** according to task type and technical domain
4. **Link to Parent Feature** using GitHub's sub-issue functionality
5. **Reference Parent Epic** for full traceability
6. **Set Appropriate Priority** based on feature priority and task criticality
7. **Assign Team Members** based on task type and skills required
8. **Set Effort Estimation** based on task complexity

### Step 4: Establish Task-Feature Relationships
For each created task:

1. **Add as Sub-Issue to Feature:** Create parent-child relationship
2. **Update Feature:** Reference tasks in feature description
3. **Cross-Reference:** Ensure bidirectional linking
4. **Validate Hierarchy:** Confirm Epic → Feature → Task hierarchy

### Step 5: Sequence and Dependency Management
1. **Identify Task Dependencies:** Determine which tasks depend on others
2. **Create Dependency Links:** Use GitHub issue references
3. **Set Task Sequence:** Order tasks logically within features
4. **Validate Workflow:** Ensure logical task progression

### Step 6: Quality Validation
Ensure each created task:
- [ ] Has clear, actionable acceptance criteria
- [ ] Includes specific technical requirements
- [ ] Contains realistic effort estimates
- [ ] Has appropriate labels applied
- [ ] Is properly linked to parent feature
- [ ] Follows the standard task template structure
- [ ] Includes comprehensive Definition of Done
- [ ] Has clear success metrics

## Industry Standards Compliance

### Agile/Scrum Task Standards
- Follow Scrum guide principles for Sprint Backlog items
- Tasks should be completable within 1-5 days
- Use standard effort estimation (hours or story points)
- Include clear acceptance criteria
- Follow Definition of Done practices

### Task Size Guidelines
- **XS Task:** 1-2 hours, simple implementation
- **Small Task:** 3-8 hours, straightforward development
- **Medium Task:** 1-2 days, moderate complexity
- **Large Task:** 3-5 days, complex implementation
- **Too Large:** Should be broken down into smaller tasks

### SMART Task Criteria
Ensure each task is:
- **Specific:** Clear and well-defined scope
- **Measurable:** Has quantifiable completion criteria
- **Achievable:** Realistic given resources and constraints
- **Relevant:** Contributes to feature and epic objectives
- **Time-bound:** Has clear effort estimation and timeline

### Task Quality Standards
- Tasks must be independently completable
- Each task should have a single responsibility
- Acceptance criteria must be testable
- Technical requirements must be specific
- Dependencies must be clearly identified

## Epic-Feature-Task Relationship Management

### Three-Level Hierarchy
```
Epic (Parent Issue)
├── Feature 1 (Sub-Issue)
│   ├── Task 1.1 (Sub-Issue)
│   ├── Task 1.2 (Sub-Issue)
│   └── Task 1.3 (Sub-Issue)
├── Feature 2 (Sub-Issue)
│   ├── Task 2.1 (Sub-Issue)
│   └── Task 2.2 (Sub-Issue)
└── Feature N (Sub-Issue)
    └── Task N.1 (Sub-Issue)
```

### Relationship Management
1. **Task-to-Feature:** Direct sub-issue relationship
2. **Task-to-Epic:** Indirect through feature relationship
3. **Task-to-Task:** Dependency relationships using issue references
4. **Cross-Feature Tasks:** Tasks that span multiple features

### Progress Tracking
- Feature completion based on task completion
- Epic progress based on feature and task progress
- Real-time visibility into work breakdown structure

## Automation Instructions

When generating tasks programmatically:

1. **Read Features File:** Parse `/docs/Features.md` systematically
2. **Analyze Feature Requirements:** Break down each feature into taskable components
3. **Generate Task Breakdown:** Create comprehensive task list for each feature
4. **Validate Parent Features:** Confirm parent feature issues exist in GitHub
5. **Apply Task Template:** Use standard task structure for each issue
6. **Create GitHub Issues:** Use GitHub API to create task issues
7. **Establish Sub-Issue Links:** Create feature-task relationships
8. **Apply Labels and Assignments:** Automatically categorize and assign tasks
9. **Set Dependencies:** Create task-to-task dependency links
10. **Validate Creation:** Confirm all tasks are created and properly linked

## Task Breakdown Strategies

### For Development Features
- **Frontend Tasks:** Component creation, styling, event handling, testing
- **Backend Tasks:** API endpoints, business logic, data validation, error handling
- **Database Tasks:** Schema design, migrations, queries, indexing
- **Integration Tasks:** Service connections, data mapping, error handling

### For Testing Features
- **Test Planning:** Test case design, test data preparation
- **Test Implementation:** Automated test creation, manual test execution
- **Test Execution:** Running tests, defect identification, reporting
- **Test Maintenance:** Test updates, cleanup, documentation

### For Documentation Features
- **Technical Documentation:** API docs, architecture docs, setup guides
- **User Documentation:** User guides, tutorials, help content
- **Process Documentation:** Workflows, procedures, standards

### For Design Features
- **Visual Design:** Mockups, prototypes, design systems
- **User Experience:** User flows, wireframes, usability testing
- **Asset Creation:** Icons, images, animations, branding

## Error Handling

### Common Error Scenarios
- **Missing Features.md:** Prompt to create feature definitions first
- **Parent Feature Not Found:** Ensure features are created before tasks
- **Insufficient Task Details:** Flag incomplete feature definitions for review
- **Label Creation Failure:** Automatically create missing labels
- **Sub-Issue Link Failure:** Implement retry mechanism with fallback
- **Dependency Resolution Issues:** Create tasks without dependencies and flag for manual review
- **Team Assignment Conflicts:** Use default assignment with notification for manual review

### Recovery Strategies
- **Batch Processing:** Process tasks in batches with rollback capability
- **Validation Checkpoints:** Validate each step before proceeding
- **Detailed Logging:** Log all creation steps for debugging
- **Manual Review Queue:** Flag complex scenarios for human review
- **Dependency Resolution:** Create dependency matrix for complex relationships

## Success Criteria

Task generation is successful when:
- [ ] All taskable components from `/docs/Features.md` are created as GitHub Issues
- [ ] Each task follows the standard structure template
- [ ] All required labels are applied correctly
- [ ] Tasks are properly linked to parent features as sub-issues
- [ ] Task dependencies are properly documented and linked
- [ ] Task assignments align with team capabilities
- [ ] All tasks pass the SMART criteria validation
- [ ] No duplicate tasks are created
- [ ] Feature-task hierarchy is properly established and visible
- [ ] All acceptance criteria are clear and testable
- [ ] Effort estimates are realistic and consistent
- [ ] Implementation plans are actionable and detailed

## Post-Generation Tasks

After task creation:
1. **Review Task-Feature Relationships:** Ensure all links are properly established
2. **Validate Task Completeness:** Check that all tasks have complete information
3. **Confirm Team Assignments:** Verify appropriate team members are assigned
4. **Review Dependencies:** Ensure task dependencies are accurately captured and sequenced
5. **Schedule Sprint Planning:** Plan task inclusion in upcoming sprints
6. **Create Task Board:** Set up Kanban board for task workflow management
7. **Set Up Monitoring:** Establish tracking for task progress and completion
8. **Validate Work Breakdown:** Ensure complete coverage of feature requirements
9. **Review Effort Estimates:** Validate estimates with team members
10. **Create Task Roadmap:** Develop detailed timeline based on task dependencies

## Integration with Feature and Epic Management

### Progress Tracking Integration
- Feature completion percentage based on task completion
- Epic progress based on feature and task completion
- Real-time dashboard showing three-level hierarchy progress

### Sprint Planning Integration
- Tasks are ready for sprint planning sessions
- Effort estimates enable capacity planning
- Dependencies inform sprint sequencing

### Team Workflow Integration
- Tasks align with team specializations
- Work can be distributed across team members
- Clear handoff points between different skill sets

## Templates and References

### Task Template Location
The task template structure should be consistent across all generated issues and align with feature and epic templates.

### Reference Standards
- Scrum Guide for Sprint Backlog items
- User Story best practices for task definition
- SMART criteria for task quality
- GitHub Issues and Projects best practices
- Agile task management principles

### Documentation Links
- Link to parent feature for context
- Link to grandparent epic for business context
- Link to `/docs/Features.md` source document
- Link to technical specifications and designs
- Link to testing strategies and plans

## Quality Assurance Checklist

Before marking task generation complete:
- [ ] All taskable components from Features.md are created
- [ ] Task-feature relationships are established
- [ ] All labels are applied correctly
- [ ] Acceptance criteria are written in proper format
- [ ] Effort estimates are realistic and validated
- [ ] Dependencies are clearly documented and linked
- [ ] Team assignments are appropriate and balanced
- [ ] Success metrics are defined and measurable
- [ ] Implementation plans are detailed and actionable
- [ ] Risk mitigation strategies are documented
- [ ] Definition of Done is comprehensive and appropriate
- [ ] Technical requirements are specific and complete
- [ ] Testing strategies are comprehensive
- [ ] Resource requirements are clearly defined
- [ ] Three-level hierarchy (Epic → Feature → Task) is properly established