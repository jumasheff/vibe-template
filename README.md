# Vibe Template

A template for thoughtful, product centric vibe coding. It provides a structured workflow for product ideation, planning, and implementation.

## Workflow

This template provides a structured workflow for product development, guided by the commands in the `.claude` directory. The process is designed to move features from ideation to completion in a clear and organized manner, using the `product-development` directory to track progress.

The workflow consists of three main phases:

### 1. PRD Creation (`create-prd.md`)

This is the initial phase where a feature idea is fleshed out into a comprehensive **Product Requirements Document (PRD)**.

-   **Goal**: To define the "why" and "what" of a feature before any code is written.
-   **Process**: It starts by gathering context from several documents:
    -   `product.md`: High-level context about the product.
    -   `feature.md`: Specific details about the feature idea.
    -   `JTBD.md`: "Jobs to Be Done" analysis to understand user needs.
-   **Outcome**: A detailed `PRD.md` is generated.
-   **Location**: This work happens in the `product-development/planned-features/` directory.

### 2. Task Generation (`generate-tasks.md`)

Once a PRD is complete and approved, a detailed implementation plan is created.

-   **Goal**: To break down the PRD into actionable steps for a developer.
-   **Process**: The command reads the PRD and all its supporting documents to generate a step-by-step guide.
-   **Outcome**: A `tasks.md` file is created, listing all parent and sub-tasks required for implementation.
-   **Location**: The `tasks.md` file is saved in the same directory as the PRD it was generated from.

### 3. Implementation (`process-task-list.md`)

This phase involves writing the code to bring the feature to life, following the generated task list.

-   **Goal**: To implement the feature methodically, one task at a time.
-   **Process**: The developer (or AI) follows the `tasks.md` file, marking tasks as complete and running tests after each major step.
-   **Outcome**: A fully implemented and tested feature.
-   **Location**: The feature's folder is moved from `planned-features/` to `current-feature/` during active development, and finally to `completed-features/` upon completion.

This structured approach ensures that every feature is well-defined, planned, and executed, aligning with the principles of "thoughtful vibe coding."

I am hopeful that this workflow will enforce thoughtful vibe-coding.

## Recommended MCP Servers

-   **serena**: [https://github.com/oraios/serena](https://github.com/oraios/serena)
-   **context7**: [https://github.com/upstash/context7](https://github.com/upstash/context7)
