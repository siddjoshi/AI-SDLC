---
mode: agent
---

# GitHub Task Generation Instructions

## Task Definition

Create a **`/docs/tasks.md` file** containing all generated Tasks based on the features defined in `/docs/Features.md`.  
Each task must be properly structured, labeled, and formatted according to industry standards for agile development.  
Tasks must be **grouped under their parent Features** to maintain hierarchy:  
**Epic → Feature → Task**, with markdown-based linking between them.

> ❗ Do **not** create GitHub Issues — instead, write all generated task details to a markdown file (`tasks.md`) using the task structure template below.

## Prerequisites

Before generating the `tasks.md` file, ensure:
- [ ] `/docs/Features.md` file exists and contains well-defined feature descriptions
- [ ] Feature-to-Epic relationships are properly established
- [ ] Each feature has sufficient details to derive actionable tasks
- [ ] Proper labels and task types are identified
- [ ] Feature-to-Task breakdown is clearly defined or can be derived from feature requirements

## Output Specification

- The generated output must be a **single file named `/docs/tasks.md`**
- All tasks must follow the **Task Structure Format** defined below
- Tasks must be organized under their respective **Feature** headings
- Use markdown-based linking for relationships (e.g., `[Feature 1](../docs/Features.md#feature-1)`)

## Task Structure Format

Each task entry in `tasks.md` must follow this format:

```markdown
# Task: [Task Title]

## Task Summary
Brief description of what this specific task accomplishes (1 sentence)

## Parent Feature
🔗 **Related Feature:** [Link to parent feature section in `/docs/Features.md`]
🔗 **Parent Epic:** [Epic name or reference]

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
- **Depends on Task:** [Link to prerequisite task in this file]
- **Blocks Task:** [Link to dependent task in this file]

### Feature Dependencies
- **Parent Feature:** [Feature link from Features.md]
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

### Test Scenarios
1. **Primary Test Case:** [Main functionality test]
2. **Edge Cases:** [Boundary conditions to test]
3. **Error Scenarios:** [Error handling tests]
4. **Integration Points:** [Integration testing scenarios]

## Definition of Done
[Retain full Definition of Done content from original]

## Effort Estimation
- **Story Points:** [Fibonacci scale: 1, 2, 3, 5, 8]
- **Hours Estimate:** [Realistic time estimate]
- **Complexity Level:** [Simple/Medium/Complex]
- **Skill Level Required:** [Junior/Mid/Senior level]

## Resources Required
[Retain full resources section]

## Risks and Mitigation
[Retain full risks section]

## Success Metrics
[Retain full success metrics section]
```

## Task Generation Workflow

### Step 1: Parse Features from `/docs/Features.md`
1. Read and analyze the `/docs/Features.md` file.
2. Extract each feature and its detailed requirements.
3. Identify all functional and technical components that can be broken into tasks.
4. Map features to their parent epics.

### Step 2: Generate Tasks per Feature
For each feature:
- Identify **Development**, **Testing**, **Documentation**, **Design**, and **Research** tasks.
- Populate each task following the standard structure.
- Assign appropriate labels and metadata within markdown sections.
- Group all tasks under a heading matching their parent feature.

Example grouping in `tasks.md`:

```markdown
## Feature: User Authentication

### Tasks
- Task: Implement Login API
- Task: Create Login UI
- Task: Add Login Unit Tests
```

### Step 3: Output Formatting
- Write all task entries under a heading for their respective features.
- Preserve hierarchy using markdown headings:
  ```
  ## Epic: [Epic Name]
  ### Feature: [Feature Name]
  #### Tasks
  ```
- Each task under a feature must follow the Task Structure Format.

### Step 4: Validation
Ensure that the generated `tasks.md` file:
- [ ] Includes all tasks from every feature
- [ ] Maintains full Epic → Feature → Task hierarchy
- [ ] Uses markdown-based internal links for relationships
- [ ] Preserves all acceptance criteria and standards
- [ ] Contains no placeholders left unfilled (unless intentionally empty)

## Automation Instructions

When generating the markdown file programmatically:
1. **Read Features File:** Parse `/docs/Features.md`
2. **Analyze Requirements:** Identify taskable components
3. **Generate Structured Markdown:** Append each task entry in correct hierarchy
4. **Validate Completeness:** Confirm structure and criteria are met
5. **Save as `/docs/tasks.md`**

## Success Criteria

Task generation is successful when:
- [ ] `/docs/tasks.md` file is created successfully
- [ ] Every feature has corresponding tasks listed
- [ ] Each task follows the provided structure
- [ ] All labels, dependencies, and metadata are included
- [ ] Hierarchical organization (Epic → Feature → Task) is clearly visible

---

✅ **In summary:**  
This version replaces all *GitHub Issue creation* instructions with *Markdown file generation* instructions (`tasks.md`), while preserving your original content, intent, and structure — making it fully usable for offline or repo-based documentation workflows.
