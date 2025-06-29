
# AI-Driven Frontend Context Generation

This repository contains a methodology and a set of master prompts for generating comprehensive context files (`CONTEXT.md`) for frontend projects. The goal is to solve a critical problem in modern development: **ensuring that all contributors—both human and AI—adhere to a project's specific architecture, conventions, and best practices.**

## The Problem: The High Cost of Inconsistency

In any software project, consistency is key to maintainability, scalability, and efficient collaboration. However, as teams grow and AI agents become more prevalent as coding assistants, enforcing these unwritten rules becomes incredibly difficult.

-   **Human developers** have different habits, may be new to a project, or might simply forget a specific convention.
-   **AI agents** are powerful but lack inherent knowledge of your project's unique architecture. Without explicit, detailed instructions, they generate generic code that pollutes the codebase with inconsistencies, requiring significant time and effort to refactor.

The result is a chaotic codebase with mixed patterns, making it hard to understand, debug, and build upon.

## The Solution: The `CONTEXT.md` File

The solution is to create a single source of truth—a `CONTEXT.md` file—that acts as a "digital rulebook" for the project. This document explicitly defines everything from the technology stack and folder structure to architectural patterns for forms, styling, and state management.

This repository provides two powerful prompts to generate this crucial file, catering to different project needs.

---

## The Prompts

This project offers two distinct methods for generating your `CONTEXT.md` file.

### 1. The AI-Guided Interview (`CONTEXT_INTERVIEW_PROMPT.md`)

This is a master prompt designed for a collaborative session between a developer and a conversational AI (like Gemini, ChatGPT, Claude, etc.). It turns the AI into a "Senior React Architect" that guides the developer through a structured interview.

#### **How to Use It:**

1.  **Copy the entire content** of the `CONTEXT_INTERVIEW_PROMPT.md` file.
2.  **Paste it into a new conversation** with your chosen Large Language Model (LLM).
3.  **Answer the AI's questions.** The AI will act as a consultant, asking you about your project's technology choices, structure, and patterns, while also suggesting best practices.
4.  **Review the generated draft.** After the interview, the AI will produce a `CONTEXT.md` file. You can then request further refinements until it perfectly matches your project's standards.

**Best for:**
*   New projects where standards are still being defined.
*   Teams that want to collaboratively establish their rules.
*   Developers who want expert suggestions on best practices.

### 2. The Autonomous Agent Analysis (`CONTEXT_AUTONOMOUS_PROMPT.md`)

This is an execution protocol for an autonomous AI agent that has **direct access to your project's file system**. It instructs the agent to act as a "Codebase Analyst," reverse-engineering the project's conventions by reading and analyzing the code directly.

#### **How to Use It:**

1.  **Provide the agent with access** to your project's root folder.
2.  **Use the entire content** of `CONTEXT_AUTONOMOUS_PROMPT.md` as the agent's primary instruction or system prompt.
3.  **Run the agent.** It will follow the detailed analysis plan: reading `package.json`, analyzing file structures, and inferring architectural patterns from the code itself.
4.  **Review the auto-generated file.** The agent will produce a `CONTEXT.md` file populated with its findings. It will automatically flag any areas where the rules were unclear or inconsistent, marking them with `[ANALYST_NOTE: ...]` for human review.

**Best for:**
*   Existing projects with an established but undocumented codebase.
*   Quickly onboarding a new developer or AI agent to a mature project.
*   Auditing a codebase for architectural inconsistencies.

---

## Our Vision

By establishing a clear, machine-readable context, we can unlock a new level of synergy between human developers and AI agents. This `CONTEXT.md` file acts as the ultimate bridge, enabling AI to become a true extension of your team—one that understands, respects, and perfectly replicates your project's unique DNA.
