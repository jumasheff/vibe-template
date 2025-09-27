----
-description: Product Requirements Document Creation Workflow
-globs:
-alwaysApply: false
----
# Rule: Product Requirements Document (PRD) Creation Workflow

## Goal
To guide the AI assistant in creating a comprehensive Product Requirements Document (PRD) through a structured workflow that includes understanding the product context, feature details, and Jobs to Be Done before writing the final PRD.

## Workflow Overview

This workflow follows a 4-step process:
1. **Read Product Documentation** - Understand the overall product context
2. **Read Feature Documentation** - Understand the specific feature idea
3. **Read JTBD Documentation** - Understand user needs and jobs
4. **Create PRD Document** - Generate comprehensive requirements

## Process

### Step 1: Read Product Documentation
- Check if `product-development/current-feature/[feature-slug]/product.md` exists
- If not, ask the user to provide product context or create one from template
- Read and understand:
  - Product vision and mission
  - Target users and market
  - Core value proposition
  - Technical constraints
  - Current capabilities

### Step 2: Read Feature Documentation
- Check if `product-development/current-feature/[feature-slug]/feature.md` exists
- If not, ask clarifying questions to understand the feature:

#### Feature Clarifying Questions
Provide options in letter/number lists for easy selection:

**Problem Understanding**
a) What problem does this feature solve?
b) Who experiences this problem?
c) How frequently does this problem occur?

**Feature Scope**
a) What should be the core functionality?
b) What actions should users be able to perform?
c) What should this feature NOT do?

**Users and Context**
a) Who are the primary users?
b) How will they use this feature?
c) In what situations will this feature be needed?

### Step 3: Read JTBD Documentation
- Check if `product-development/current-feature/[feature-slug]/JTBD.md` exists
- If not, ask JTBD-specific questions:

#### JTBD Clarifying Questions
**Job Identification**
a) What job are users trying to get done?
b) When does this job arise?
c) Why is this job important?

**Current Solutions**
a) How do users currently do this job?
b) What problems exist with current solutions?
c) What are users unsatisfied with?

**Success Criteria**
a) What does a successful outcome look like?
b) How should users feel?
c) What metrics indicate success?

### Step 4: Generate PRD

Based on the information gathered, generate a PRD using the template structure:

1. **Introduction/Overview**
   - Executive summary
   - Problem statement
   - Solution overview

2. **Goals and Objectives**
   - Primary goals with success metrics
   - Business objectives

3. **User Stories**
   - Epic level story
   - Detailed user stories with acceptance criteria

4. **Functional Requirements**
   - Core functionality (numbered FR-1, FR-2, etc.)
   - Input/Output requirements
   - Business rules
   - Data requirements

5. **Non-Goals (Out of Scope)**
   - Explicitly what will NOT be included
   - Future considerations

6. **Design Considerations**
   - UI/UX requirements
   - User flow
   - Accessibility

7. **Technical Considerations**
   - Architecture requirements
   - Performance requirements
   - Security requirements
   - Dependencies

8. **Success Metrics**
   - KPIs with current and target values
   - User adoption metrics
   - Quality metrics
   - Business metrics

9. **Testing Strategy**
   - Test coverage requirements
   - Test scenarios
   - UAT planning

10. **Open Questions**
    - Product questions needing clarification
    - Technical questions
    - Business questions

11. **Risks and Mitigations**
    - Priority-ranked risks with mitigation strategies

12. **Timeline and Stakeholders**
    - Development milestones
    - Team members and roles

## File Management

### Working Directory Structure
```
product-development/
├── resources/
│   └── templates/
│       ├── product.md
│       ├── feature.md
│       ├── JTBD.md
│       └── PRD-template.md
├── planned-features/
│   └── [feature-slug]/
│       ├── product.md
│       ├── feature.md
│       ├── JTBD.md
│       └── PRD.md
├── current-feature/
│   └── [feature-slug]/
│       ├── product.md (copied/edited from template)
│       ├── feature.md (created from user input)
│       ├── JTBD.md (created from user input)
│       └── PRD.md (final output)
└── completed-features/
    └── [feature-slug]/
        ├── product.md
        ├── feature.md
        ├── JTBD.md
        └── PRD.md
```

### File Lifecycle
1. Create feature folder under `planned-features/[feature-slug]/` for new PRDs
2. Copy templates to the feature folder when starting
3. Edit files based on user input
4. Generate PRD in the feature folder
5. Move entire folder to `current-feature/` when development begins
6. Move entire folder to `completed-features/` when development is complete

### Feature Status Flow
- **Planned**: Feature is documented but not yet started → `planned-features/`
- **Current**: Feature is actively being developed → `current-feature/`
- **Completed**: Feature development is finished → `completed-features/`

## Target Audience

The PRD should be written for:
- **Primary**: Junior developers who need explicit, unambiguous requirements
- **Secondary**: Product stakeholders, designers, QA engineers
- **Tertiary**: Business stakeholders and executives

## Output Requirements

- **Format**: Markdown (`.md`)
- **Location**: `product-development/planned-features/[feature-slug]/`
- **Filename**: `PRD.md`
- **Language**: English

## Completion Checklist

Before finalizing the PRD:
- [ ] All sections from template are addressed
- [ ] User stories have clear acceptance criteria
- [ ] Functional requirements are numbered and specific
- [ ] Non-goals are explicitly stated
- [ ] Success metrics have current and target values
- [ ] Open questions are documented with owners
- [ ] Risks are identified with mitigation strategies

## Important Instructions

1. **DO NOT** start implementing the PRD
2. **ALWAYS** ask clarifying questions before generating the PRD
3. **USE** the structured workflow (Product → Feature → JTBD → PRD)
4. **INCORPORATE** user feedback to improve the PRD
5. **SAVE** all documents in the appropriate directories
6. **CREATE** feature folders with descriptive slugs (e.g., `search-agent`, `user-auth`)
7. **TRACK** feature status by moving folders between planned/current/completed

## Error Handling

If any required document is missing:
1. Check if a template exists
2. Ask the user if they want to:
   a) Create from template
   b) Provide the information directly
   c) Skip that section (not recommended)

## Quality Criteria

A well-written PRD should:
- Be understandable by a junior developer
- Have no ambiguous requirements
- Include measurable success criteria
- Address all stakeholder concerns
- Provide clear scope boundaries
- Include realistic timelines