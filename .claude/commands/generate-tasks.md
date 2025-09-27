----
-description:
-globs:
-alwaysApply: false
----
# Rule: Generating a Task List from a PRD

## Goal

To guide an AI assistant in creating a detailed, step-by-step task list in Markdown format based on an existing Product Requirements Document (PRD). The task list should guide a developer through implementation.

## Output

- **Format:** Markdown (`.md`)
- **Location:** Same directory as the PRD: `product-development/[status]/[feature-slug]/`
- **Filename:** `tasks.md`

## Process

### Phase 0: Context Gathering
1. **Receive PRD Reference:** The user points the AI to a specific PRD file in the product-development structure
2. **Identify Feature Location:** Determine the feature slug and status (planned/current/completed) from the file path
3. **Read All Context Documents:** Read the complete feature documentation set:
   - `product.md` - Product context and constraints
   - `feature.md` - Feature description and initial requirements
   - `JTBD.md` - Jobs to be done analysis
   - `PRD.md` - Detailed product requirements
4. **Assess Current State:** Review the existing codebase to understand:
   - Existing infrastructure and architectural patterns
   - Related components that can be leveraged or need modification
   - Testing patterns and conventions
   - Deployment and integration patterns

### Phase 1: High-Level Planning
5. **Generate Parent Tasks:** Based on comprehensive analysis, create main high-level tasks required to implement the feature
6. **Identify Dependencies:** Map out dependencies between tasks and external systems
7. **Estimate Complexity:** Provide rough complexity estimates for each parent task
8. **Present to User:** Show high-level tasks with context: "I have generated the high-level implementation plan based on the complete feature documentation. Ready to generate detailed sub-tasks? Respond with 'Go' to proceed."
9. **Wait for Confirmation:** Pause for user approval before proceeding

### Phase 2: Detailed Breakdown
10. **Generate Sub-Tasks:** Break down each parent task into actionable sub-tasks with:
    - Clear completion criteria
    - Dependencies and prerequisites
    - Testing requirements
    - Integration considerations
11. **Identify Relevant Files:** List files that need creation or modification, categorized by:
    - Core implementation files
    - Test files
    - Configuration files
    - Documentation files
12. **Create Testing Strategy:** Outline comprehensive testing approach
13. **Plan Integration & Deployment:** Include tasks for integration and deployment

### Phase 3: Output Generation
14. **Generate Final Output:** Combine all information into the structured format
15. **Save Task List:** Save as `tasks.md` in the same feature directory as the PRD

## Output Format

The generated task list _must_ follow this structure:

```markdown
# Implementation Tasks: [Feature Name]

## Context
- **Feature Slug**: [feature-slug]
- **Feature Status**: [Planned/Current/Completed]
- **PRD Location**: `product-development/[status]/[feature-slug]/PRD.md`
- **Related Documents**:
  - [Product Context](product.md)
  - [Feature Description](feature.md)
  - [Jobs to be Done](JTBD.md)

## Pre-Implementation Checklist
- [ ] PRD reviewed and approved
- [ ] Technical design completed
- [ ] Dependencies identified and available
- [ ] Development environment ready
- [ ] Team capacity confirmed

## Dependencies & Integration Points
### Internal Dependencies
- [List internal systems/components this feature depends on]

### External Dependencies
- [List third-party services/APIs required]

### Blocking Dependencies
- [List any dependencies that must be completed first]

## Relevant Files

### Core Implementation Files
- `path/to/main/component.ts` - [Brief description and purpose]
- `path/to/service/handler.ts` - [Brief description and purpose]

### Test Files
- `path/to/main/component.test.ts` - Unit tests for main component
- `path/to/service/handler.test.ts` - Unit tests for service handler
- `tests/integration/feature-name.test.ts` - Integration tests

### Configuration Files
- `config/feature-settings.ts` - [Configuration needed]
- `deployment/feature-config.yml` - [Deployment configuration]

### Documentation Files
- `docs/feature-name.md` - User documentation
- `docs/api/feature-endpoints.md` - API documentation

## Implementation Tasks

- [ ] 1.0 [Parent Task Title] (Complexity: Low/Medium/High)
  - **Prerequisites**: [What needs to be done first]
  - **Completion Criteria**: [How to know when this is done]
  - [ ] 1.1 [Sub-task description with specific action]
  - [ ] 1.2 [Sub-task description with specific action]
  - [ ] 1.3 [Sub-task testing requirements]

- [ ] 2.0 [Parent Task Title] (Complexity: Low/Medium/High)
  - **Prerequisites**: [Dependencies from other tasks]
  - **Completion Criteria**: [Specific acceptance criteria]
  - [ ] 2.1 [Sub-task description]
  - [ ] 2.2 [Sub-task testing requirements]

## Testing Strategy

### Unit Testing
- [ ] Write unit tests for all core components
- [ ] Achieve >90% code coverage
- [ ] Test edge cases and error conditions

### Integration Testing
- [ ] Test feature integration with existing systems
- [ ] Test API endpoints with various inputs
- [ ] Test database interactions

### End-to-End Testing
- [ ] Test complete user workflows
- [ ] Test cross-browser compatibility (if applicable)
- [ ] Performance testing under load

### Testing Commands
- `poetry run pytest tests/unit/` - Run unit tests
- `poetry run pytest tests/integration/` - Run integration tests
- `poetry run pytest --cov=legal_search` - Run tests with coverage

## Integration & Deployment

### Pre-Deployment
- [ ] Code review completed
- [ ] All tests passing
- [ ] Documentation updated
- [ ] Security review completed (if required)

### Deployment Tasks
- [ ] Deploy to staging environment
- [ ] Run smoke tests in staging
- [ ] Deploy to production
- [ ] Monitor for errors post-deployment

### Rollback Plan
- [ ] Document rollback procedures
- [ ] Test rollback in staging
- [ ] Prepare monitoring for production issues

## Success Criteria
- [ ] All functional requirements from PRD implemented
- [ ] All tests passing with required coverage
- [ ] Performance meets specified requirements
- [ ] Security requirements satisfied
- [ ] Documentation complete and accurate
- [ ] Feature accessible to target users

## Risk Mitigation
### High Priority Risks
- **Risk**: [Description] | **Mitigation**: [Approach] | **Owner**: [Who handles this]

### Medium Priority Risks
- **Risk**: [Description] | **Mitigation**: [Approach] | **Owner**: [Who handles this]

## Notes
- Follow existing code patterns and conventions in the codebase
- Ensure backward compatibility where required
- Consider scalability and performance implications
- Update relevant documentation as you implement
```

## Interaction Model

The process follows a three-phase approach with user confirmation:

1. **Phase 0: Context Gathering** - Automatically reads all available feature documentation
2. **Phase 1: High-Level Planning** - Generates parent tasks and presents them for approval
3. **User Confirmation** - Wait for "Go" response before proceeding
4. **Phase 2: Detailed Breakdown** - Creates comprehensive task breakdown with all sections

This ensures the high-level plan aligns with user expectations before diving into implementation details.

## Quality Standards

### Task Clarity Requirements
- Each task must have clear, actionable descriptions
- Sub-tasks should be completable in 2-4 hours
- All tasks must include completion criteria
- Dependencies must be explicitly stated

### Complexity Guidelines
- **Low**: Simple implementation, existing patterns, minimal testing
- **Medium**: Moderate complexity, some new patterns, standard testing
- **High**: Complex logic, new architecture, extensive testing

### Testing Requirements
- Unit tests required for all business logic
- Integration tests for API endpoints
- End-to-end tests for user workflows
- Performance tests for critical paths

### Documentation Standards
- Code comments for complex logic
- API documentation for new endpoints
- User documentation for new features
- Architecture documentation for new patterns

## Integration with New Workflow

### Feature Status Awareness
- **Planned Features**: Tasks focus on research and planning
- **Current Features**: Tasks focus on implementation and testing
- **Completed Features**: Tasks focus on maintenance and optimization

### Cross-Document References
- Tasks should reference specific PRD sections
- Link to relevant JTBD outcomes
- Reference product constraints from product.md
- Consider feature context from feature.md

## Target Audience

Assume the primary reader of the task list is a **junior developer** who will implement the feature with awareness of the existing codebase context.

The task list also serves:
- **Secondary**: Tech leads reviewing implementation approach
- **Tertiary**: Product managers tracking progress against PRD requirements

## Error Handling

### Missing Context Documents
If any context document is missing:
1. Note the missing document in the Context section
2. Proceed with available information
3. Flag areas that need clarification
4. Recommend creating missing documents

### Incomplete PRD
If PRD lacks critical information:
1. Identify specific missing requirements
2. List assumptions made for task generation
3. Create tasks for requirement clarification
4. Flag risks associated with incomplete requirements
