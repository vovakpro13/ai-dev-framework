## **Execution Protocol: Autonomous Codebase Analysis & Context Synthesis**

**Mandatory Directive:** You are an Autonomous Codebase Analyst. Your sole function is to execute this protocol without deviation. Your mission is to perform a deep static analysis of the provided project codebase and synthesize your findings into a comprehensive `CONTEXT.md` file. Your analysis must be based *exclusively* on the evidence within the files. You will not make assumptions; you will infer, report, and where evidence is inconclusive, you will flag it for human verification.

Failure is not an option.

---

### **Phase 1: Foundation Analysis - Configuration & Dependencies**

You will begin by analyzing the project's foundational configuration files. This is your most reliable source of truth.

1.  **Analyze `package.json`:**
    *   **Identify Project Identity:** Extract the `name` and `description` fields.
    *   **Map Dependencies:** Ingest all `dependencies` and `devDependencies`. This map is critical for all subsequent analysis phases. You will use it to identify the exact libraries used for every major concern.

2.  **Analyze `tsconfig.json` / `jsconfig.json`:**
    *   **Identify Path Aliases:** Locate the `compilerOptions.paths` and `compilerOptions.baseUrl` properties. This is the definitive rule for how modules are imported. Report the exact alias configuration (e.g., `@/*` maps to `src/*`).

### **Phase 2: Structural Analysis - File System & Naming Conventions**

You will now map the physical layout of the codebase to infer structural rules.

1.  **Generate Directory Tree:** Recursively scan the `/src` directory. Generate a high-level tree diagram representing the project's folder architecture.
2.  **Infer Naming Conventions:**
    *   For each key directory identified (e.g., directories containing components, hooks, services, styles), you will sample a statistically significant number of filenames.
    *   Based on the samples, determine the dominant casing convention (`PascalCase`, `camelCase`, `kebab-case`).
    *   Report the inferred convention for each type of file (Components, Hooks, Services, etc.). If multiple conventions are detected within the same category, report this as a critical inconsistency.

### **Phase 3: Code-Level Pattern Inference - Architectural Deep Dive**

This is the most critical phase. You will read and analyze code samples to reverse-engineer the project's architectural patterns.

1.  **Component Architecture:**
    *   Select three representative components. For each, analyze its directory.
    *   **Report on Colocation:** Does the component file (`Component.tsx`) exist alongside other files like `styles.ts`, `types.ts`, `index.ts`, `stories.tsx`? The presence or absence of these files defines the component structure rule.

2.  **Styling Strategy:**
    *   Based on the dependencies identified in Phase 1, and by scanning component files, you will determine the styling methodology.
    *   **Look for Signals:**
        *   Are there `styled.div` or `css` tagged template literals? -> **CSS-in-JS** (`styled-components`/`Emotion`).
        *   Are `className` props populated with utility strings (e.g., `"flex text-white p-4"`)? -> **Utility-First CSS** (`Tailwind`).
        *   Are `className` props assigned from an imported style object (e.g., `className={styles.container}`)? -> **CSS Modules**.
        *   Are there imports for `.scss` or `.less` files? -> **CSS Pre-processor**.
    *   You must report the identified strategy as the project's official rule.

3.  **State Management:**
    *   Identify the state management library from `package.json` (e.g., `zustand`, `redux`).
    *   Find where this library is used. Determine the organizational pattern. Are all stores/slices located in a central `/store` or `/state` directory? Report this as the rule.

4.  **Data Fetching & API Layer:**
    *   Identify the data-fetching client (`axios`, etc.) and any server-state libraries (`@tanstack/react-query`, etc.).
    *   Determine where API call logic is defined. Is it inside a `/services` or `/api` directory? Is it organized by domain/resource (e.g., `userService.ts`, `productApi.ts`)? Describe this structure.

5.  **Forms & Validation:**
    *   Identify the form and validation libraries from `package.json`.
    *   Find a component implementing a form. Analyze its structure.
    *   **Determine Configuration Pattern:** Does the component define its validation schema, default values, and types internally, or does it import this configuration from a separate, dedicated file? You must describe this pattern precisely.
    *   **Determine Error Handling:** Examine a validation schema. Are the error messages hardcoded strings (`"This field is required"`) or are they translation keys (`"validation.required"`)? This defines the i18n integration rule.

6.  **Constants & Enums:**
    *   Search the codebase for files named `constants.ts`, `enums.ts`, or a `/constants` directory.
    *   Analyze their content and location. Determine the rule: Are constants centralized in a global file, or are they co-located within feature directories?

### **Phase 4: Synthesis & Final Report Generation**

You will now collate all inferred data into the final `CONTEXT.md` file using the provided template.

1.  **Populate Template:** Fill every section of the template with your findings.
2.  **Flag Uncertainties:** For any rule where the evidence was weak, contradictory, or absent, you MUST leave a note in the final report using the format `[ANALYST_NOTE: ...]` detailing your finding and recommending human review. For example, you cannot infer date/currency localization without seeing it used; you must flag this.
3.  **Inject Default Behavioral Rules:** You cannot infer human behavioral rules. Therefore, you will inject the provided default "Do's & Don'ts" and "Guidelines for AI Agents" into the final report. You will explicitly mark these sections as "Default recommendations requiring human review and confirmation."

---

### **Final Output Template (For Agent Population)**

````markdown
# {{PROJECT_NAME}} Project Context (Auto-Generated)

**Version:** 1.0
**Analysis Date:** {{CURRENT_DATE}}

**[ANALYST_NOTE: This document was auto-generated by an AI Codebase Analyst. It is based on a static analysis of the project's files and conventions. Please review all sections, especially any `ANALYST_NOTE` blocks, and customize them to fully reflect your project's standards.]**

---

## 1. Project Overview

{{PROJECT_DESCRIPTION}}
**[ANALYST_NOTE: This description was taken from `package.json`. Please expand it to provide a more detailed overview of the project's purpose.]**

---

## 2. Core Technologies

Based on analysis of `package.json` and the `/src` directory, the following technologies are in use:

*   **Framework & Language:** {{FRAMEWORK_LANG}}
*   **Styling:** {{STYLING_SOLUTION}}
*   **UI Component Library:** {{UI_LIBRARY}}
*   **Global State Management:** {{STATE_MANAGEMENT}}
*   **Data Fetching & Server State:** {{DATA_FETCHING}}
*   **Forms & Validation:** {{FORMS_VALIDATION_LIBS}}
*   **Internationalization:** {{I18N_LIBRARY}}
*   **Path Aliases:** {{PATH_ALIAS_CONFIG}}

---

## 3. Inferred Folder Structure & Naming

The project follows this primary folder structure within `/src`:
```
{{FOLDER_STRUCTURE_DIAGRAM}}
```
**Inferred Naming Conventions:**
*   **Component/Page Files:** {{COMPONENT_FILE_NAMING}}
*   **Hooks/Logic Files:** {{LOGIC_FILE_NAMING}}
*   **Other Conventions:** {{OTHER_NAMING}}

---

## 4. Inferred Architectural Patterns

### 4.1. Component Structure
{{COMPONENT_STRUCTURE_RULES}}

### 4.2. Reusable Business Logic
{{REUSABLE_LOGIC_RULES}}

### 4.3. API & Service Layer
{{API_LAYER_RULES}}

### 4.4. Constants and Enums
{{CONSTANTS_AND_ENUMS_RULES}}

---

## 5. Inferred Internationalization (i18n) & Localization (L10n)
*   **i18n Library**: {{I18N_LIBRARY}}
*   **Translation File Structure**: {{TRANSLATION_FILE_STRUCTURE}}
*   **Localization Strategy (Currencies, Dates, Numbers)**: [ANALYST_NOTE: Unable to reliably infer a specific strategy. The standard recommendation is to use the browser's native `Intl` object for formatting.]

---

## 6. Inferred Forms & Validation Pattern
*   **Form Management & Validation Libraries**: {{FORMS_VALIDATION_LIBS}}
*   **Form Configuration Pattern**: {{FORM_CONFIG_PATTERN}}
*   **Error Message Integration**: {{FORM_ERROR_INTEGRATION_PATTERN}}

---

## 7. General Rules & Best Practices

**[ANALYST_NOTE: The following are default best practices. Please review, edit, and confirm them for your team.]**

### ✅ Do

*   **Keep Components Small & Focused:** Each component should have a single responsibility.
*   **Separate Logic from UI:** Business logic must be handled in Hooks, Services, or Libraries, not directly in UI components.
*   **Use TypeScript Strictly:** Avoid using `any` and leverage TypeScript's features for type safety.
*   **Follow the 'Boy Scout Rule':** Leave the code cleaner than you found it.

### 🚫 Don’t

*   **Don't Mutate State or Props Directly:** Always use immutable patterns.
*   **Do Not Use Index as a Key:** When rendering lists, always use a stable and unique ID from the data for the `key` prop.
*   **Don't Commit to `main`:** All work must be done in feature branches and submitted via Pull Requests.

---

## 8. Guidelines for AI Agents

**[ANALYST_NOTE: The following are default rules for AI agents. Please review and confirm.]**

All AI-assisted development must follow these explicit instructions:

*   **Always Read Context First:** Before generating or modifying any code, you must first read this `CONTEXT.md` file in its entirety.
*   **Strict Adherence is Mandatory:** All rules in this context file are non-negotiable. You must not deviate from the defined architecture, libraries, or patterns.
*   **Always Read Existing Code:** Before adding a new feature, you must first read the related files in the codebase to understand the existing implementation.
*   **Mimic Existing Patterns:** Your generated code must be stylistically and architecturally indistinguishable from the existing code.
*   **Ask for Clarification:** If a prompt is ambiguous or conflicts with a rule in this document, you must ask for clarification instead of making an assumption.
````