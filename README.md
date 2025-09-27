# Vibe Template

A template for thoughtful, product centric vibe coding. It provides a structured workflow for product ideation, planning, and implementation.

## Workflow

This template provides a structured workflow for product development, guided by the commands in the `.claude` directory. The process is designed to move features from ideation to completion in a clear and organized manner, using the `product-development` directory to track progress.

I am hopeful that this workflow will enforce thoughtful vibe-coding.

The workflow consists of four main phases:

### 1. JTBD Creation (`create-jtbd.md`)

This is the foundational first step where you brainstorm and define the user's problem.

-   **Goal**: To deeply understand the user's needs and motivations before considering any solution.
-   **Process**: An interactive command guides you through the "Jobs to Be Done" framework, asking questions to help you articulate the core problem, user context, and desired outcomes.
-   **Outcome**: A `JTBD.md` document that serves as the source of truth for the user's needs.
-   **Location**: This work happens in the `product-development/planned-features/` directory.

### 2. PRD Creation (`create-prd.md`)

With a clear understanding of the problem, this phase translates the "why" from the JTBD into the "what" of a feature.

-   **Goal**: To create a comprehensive **Product Requirements Document (PRD)** that defines the solution.
-   **Process**: This command consumes the `JTBD.md` and other context documents (`product.md`, `feature.md`) to generate a detailed specification.
-   **Outcome**: A detailed `PRD.md` is generated.
-   **Location**: This work happens in the `product-development/planned-features/` directory.

### 3. Task Generation (`generate-tasks.md`)

Once a PRD is complete and approved, a detailed implementation plan is created.

-   **Goal**: To break down the PRD into actionable steps for a developer.
-   **Process**: The command reads the PRD and all its supporting documents to generate a step-by-step guide.
-   **Outcome**: A `tasks.md` file is created, listing all parent and sub-tasks required for implementation.
-   **Location**: The `tasks.md` file is saved in the same directory as the PRD it was generated from.

### 4. Implementation (`process-task-list.md`)

This phase involves writing the code to bring the feature to life, following the generated task list.

-   **Goal**: To implement the feature methodically, one task at a time.
-   **Process**: The developer (or AI) follows the `tasks.md` file, marking tasks as complete and running tests after each major step.
-   **Outcome**: A fully implemented and tested feature.
-   **Location**: The feature's folder is moved from `planned-features/` to `current-feature/` during active development, and finally to `completed-features/` upon completion.

## Recommended MCP Servers

-   **serena**: [https://github.com/oraios/serena](https://github.com/oraios/serena) - Serena enhances developer productivity by providing a powerful, language-aware toolkit that enables AI agents to deeply understand, semantically search, and safely edit code within a developer's local environment.
-   **context7**: [https://github.com/upstash/context7](https://github.com/upstash/context7) - Context7 improves AI coding accuracy by providing LLMs with direct access to up-to-date, version-specific library documentation and code examples, eliminating reliance on outdated training data.
