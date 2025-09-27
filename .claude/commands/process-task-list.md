# Task List Management and Implementation

Guidelines for managing and implementing task lists in the new product development workflow

## Task Implementation Protocol

### Pre-Implementation Setup
- **Location**: All task files are located at `product-development/[status]/[feature-slug]/tasks.md`
- **Context**: Always review the feature's PRD, product.md, feature.md, and JTBD.md before starting
- **Dependencies**: Check the "Dependencies & Integration Points" section before beginning any task

### Implementation Flow
- **One sub-task at a time:** Do **NOT** start the next sub‑task until you ask the user for permission and they say "yes" or "y"
- **Verify Prerequisites**: Before starting any task, confirm all prerequisites are met
- **Check Completion Criteria**: Understand what constitutes completion for each task

### Completion Protocol
1. **Sub-task Completion:**
   - When you finish a **sub‑task**, immediately mark it as completed by changing `[ ]` to `[x]`
   - Update any relevant sections (e.g., mark files as created/modified)
   - Verify completion criteria are met

2. **Parent Task Completion** (when all subtasks are `[x]`):
   - **First**: Run the project's test suite:
     - `poetry run pytest` (for Python projects)
     - `npm test` (for Node.js projects)
     - Check project-specific test commands in the Testing Strategy section
   - **Only if all tests pass**: Stage changes (`git add .`)
   - **Clean up**: Remove temporary files and temporary code
   - **Update Documentation**: Ensure any new features are documented
   - **Commit**: Use descriptive commit messages with conventional format:

     ```bash
     git commit -m "feat: implement user authentication system" \
                -m "- Add JWT token generation and validation" \
                -m "- Implement login/logout endpoints" \
                -m "- Add password hashing with bcrypt" \
                -m "- Create user session management" \
                -m "- Add comprehensive unit and integration tests" \
                -m "Completes task 2.0 from search-agent PRD"
     ```

3. **Mark Parent Task Complete**: After successful commit, mark the **parent task** as `[x]`

### Stop and Confirm
- Stop after each sub‑task completion and wait for user's go‑ahead
- Present a brief summary of what was accomplished
- Mention the next sub-task to be tackled

## Task List Maintenance

### Task Status Updates
1. **Mark Progress:**
   - Mark tasks and subtasks as completed (`[x]`) per the protocol above
   - Add new tasks as they emerge during implementation
   - Update completion criteria if requirements change

2. **File Tracking:**
   - **Core Implementation Files**: Update when files are created or significantly modified
   - **Test Files**: Track all test files created and their coverage
   - **Configuration Files**: Note any config changes needed
   - **Documentation Files**: Keep documentation current with implementation

### Section-Specific Maintenance

3. **Pre-Implementation Checklist:**
   - Mark items as complete when verified
   - Add new checklist items if discovered during implementation

4. **Dependencies & Integration Points:**
   - Update status of dependencies as they become available
   - Note any new dependencies discovered during implementation
   - Flag blocking dependencies that need attention

5. **Testing Strategy:**
   - Update test coverage percentages as tests are written
   - Mark testing milestones as complete
   - Add new test types if needed during implementation

6. **Success Criteria:**
   - Mark criteria as met when achieved
   - Add new success criteria if requirements expand

7. **Risk Mitigation:**
   - Update risk status as mitigation strategies are implemented
   - Add new risks discovered during development
   - Note resolved risks and their outcomes

## AI Implementation Instructions

### Before Starting Any Work
1. **Read Context Documents:** Review PRD, product.md, feature.md, and JTBD.md in the feature folder
2. **Understand Current State:** Check existing codebase patterns and conventions
3. **Verify Prerequisites:** Ensure all dependencies and requirements are met
4. **Identify Next Task:** Determine which sub-task should be tackled next

### During Implementation
5. **Follow Task Order:** Work through tasks in logical dependency order
6. **One Task at a Time:** Complete one sub-task completely before moving to the next
7. **Update as You Go:** Keep the task list current with progress and discoveries
8. **Test Continuously:** Run relevant tests during implementation, not just at the end

### After Each Sub-Task
9. **Mark Complete:** Change `[ ]` to `[x]` for finished sub-tasks
10. **Update Files Section:** Note any new or modified files
11. **Check Completion Criteria:** Verify the task meets its completion criteria
12. **Commit Small Changes:** For complex tasks, commit incremental progress
13. **Pause for Approval:** Stop and wait for user permission before continuing

### Parent Task Completion
14. **Run Full Test Suite:** Ensure all tests pass before marking parent task complete
15. **Update All Sections:** Refresh dependencies, risks, files, and other sections
16. **Create Meaningful Commits:** Use conventional commit format with detailed descriptions
17. **Mark Parent Complete:** Only after successful testing and commit

### Quality Assurance
18. **Follow Coding Standards:** Maintain consistency with existing codebase patterns
19. **Document Changes:** Update relevant documentation for new features
20. **Consider Integration:** Think about how changes affect other parts of the system
21. **Plan for Rollback:** Ensure changes can be safely reverted if needed

### Communication
22. **Provide Status Updates:** Give clear summaries of what was accomplished
23. **Flag Issues Early:** Communicate problems or blockers as soon as discovered
24. **Ask for Clarification:** Request guidance when requirements are unclear
25. **Suggest Improvements:** Recommend optimizations or alternative approaches when appropriate

### Error Handling
26. **Handle Test Failures:** If tests fail, fix issues before proceeding
27. **Manage Dependencies:** Address missing or broken dependencies promptly
28. **Document Workarounds:** Note any temporary solutions that need future attention
29. **Update Risk Assessment:** Modify risk mitigation strategies based on discoveries
