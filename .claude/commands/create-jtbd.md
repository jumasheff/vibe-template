# Rule: Jobs to Be Done (JTBD) Creation Workflow

## Goal
To guide a solopreneur or product developer in creating a comprehensive Jobs to Be Done (JTBD) document through an interactive, conversational process. This command serves as the foundational first step in the product development workflow.

## Workflow Overview
This workflow is designed to be a guided brainstorming session:
1.  **Initiate Feature:** Get the name/slug for the new feature idea.
2.  **Setup Directory:** Create the necessary folder structure.
3.  **Interactive Elicitation:** Ask structured questions to fill out each section of the JTBD template.
4.  **Generate Document:** Create the final `JTBD.md` file.

## Process

### Step 1: Initiate Feature
- Ask the user for a short, descriptive name for the feature (e.g., "User Authentication", "Search Agent").
- Convert this name into a URL-friendly slug (e.g., `user-authentication`, `search-agent`).

### Step 2: Setup Directory Structure
- Create a new directory under `product-development/planned-features/[feature-slug]/`.
- Copy the template from `product-development/resources/templates/JTBD.md` into this new directory.

### Step 3: Interactive Elicitation
Engage the user in a conversation to fill out the copied `JTBD.md`. Go section by section.

#### Section: Core Jobs to Be Done
- "Let's define the primary job. When a user is in a specific situation, what do they want to do, and what is their desired outcome?"
- Prompt for the `When... I want to... So I can...` job story format.
- Ask about the context: "What triggers this need? Where are they when this happens?"
- Ask about current solutions: "How do they solve this problem today? What's frustrating about it?"

#### Section: User Segments
- "Who are the different types of users that will use this? Let's think about different segments."
- "How does their need or the job's importance vary between these segments?"

#### Section: Competing Solutions
- "What are the direct competitors that solve this same job?"
- "What are the indirect alternatives? (e.g., using a spreadsheet, a notebook, or just ignoring the problem)."

#### Section: Barriers to Adoption
- "What might stop someone from using a new solution? Think about costs, learning curves, or fears."

#### Section: Opportunity Assessment
- "Based on our discussion, what needs seem to be completely unmet or poorly served by current solutions?"

### Step 4: Generate Document
- As the user provides answers, programmatically update the `JTBD.md` file in `product-development/planned-features/[feature-slug]/`.
- After completing all sections, confirm with the user that the document is ready.

## File Management

- **Input Template:** `product-development/resources/templates/JTBD.md`
- **Output File:** `product-development/planned-features/[feature-slug]/JTBD.md`

## Important Instructions
1.  **BE CONVERSATIONAL:** This is a brainstorming partner, not an interrogation. Use open-ended questions.
2.  **ONE SECTION AT A TIME:** Avoid overwhelming the user. Focus the conversation on one part of the JTBD framework at a time.
3.  **SAVE PROGRESSIVELY:** Update the `JTBD.md` file as information is gathered.
4.  **THIS IS THE FIRST STEP:** This command must be run before `create-prd`.

## Target Audience
The user of this command is a **solopreneur** or **product owner** at the earliest stage of ideation. The tone should be supportive, curious, and structured.
