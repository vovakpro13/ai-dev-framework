# 🧠 AI Development Framework

> Standardized AI-ready context template for frontend developers working with AI agents like Cursor, Copilot, and Gemini CLI.

---

## 🚨 Problem

AI agents are powerful, but dumb without context.

They don’t know:
- how your project is structured,
- what styling system you use,
- where your logic lives,
- how your APIs are defined.

❌ Without context, they generate spaghetti.

✅ With this framework, you can give them structure, rules, and logic — just like a real teammate.

---

## 🎯 Purpose

**AI Development Framework** helps you:
- build a complete AI context for any frontend project (React, TypeScript),
- define all rules and conventions,
- guide an AI agent through a Q&A session,
- automatically generate a `AGENT_CONTEXT.md` file the agent can use to code like you.

---

## 📦 What’s Included

```
ai-framework/
├── rules/           # Architecture, code, styling, API, state, etc.
├── examples/        # Good / bad code samples
├── prompts/         # Generation prompts (component, hook, store...)
├── templates/       # Rule and prompt templates
├── agent/           # Agent guide, question flow, context builder
├── AGENT_CONTEXT.md # Generated per project
├── README.md        # This file
```

---

## ⚙️ How It Works

1. You clone this repo
2. You open an AI agent (Cursor / Gemini CLI / Copilot)
3. You ask it to read `/agent/README.md`
4. It walks you through all the key project decisions
5. It builds your custom `AGENT_CONTEXT.md`
6. You plug this file into the agent → AI now codes your way.

---

## 🚀 Quick Start

### 1. Clone the framework

```bash
git clone https://github.com/your-username/ai-framework.git
cd ai-framework
```

### 2. Launch your agent

Choose your tool below.

---

## 🤖 Agent Instructions

### 🌀 Gemini CLI

```bash
gemini
```

Then write:

```
Read ./agent/README.md and walk me through the setup.
```

➡️ Gemini will ask you structured questions and build `AGENT_CONTEXT.md`.

Use it later like:

```bash
gemini --context ./AGENT_CONTEXT.md
```

---

### 🧠 Cursor IDE

1. Open the project in Cursor
2. Move `AGENT_CONTEXT.md` into `.cursor/context/`
3. Tell Cursor:

```
Use the context from `.cursor/context/AGENT_CONTEXT.md`
```

➡️ Now all your prompts will follow your project conventions.

---

### 🤖 GitHub Copilot

> Copilot doesn't support structured context yet — but you can give it hints via comments.

1. Open `README.md` or your root `App.tsx`
2. Add this block:

```ts
// Copilot Context:
// - Structure: feature-sliced
// - State: Zustand
// - Styling: styled-components
// - Components: typed, logic-free
// - API: custom fetch hook per endpoint
```

➡️ This helps Copilot guess better within your repo structure.

---

## 📄 About `AGENT_CONTEXT.md`

After completing the Q&A, your agent will generate:

```md
# AGENT CONTEXT

## Framework
- React + TypeScript
- Zustand for state
- styled-components for styling

## Folder Structure
- feature-sliced: shared / entities / features / widgets / pages / app

## Rules
- Components: functional, separated styles
- API: typed hooks per feature
- State: colocated Zustand stores
- Business logic: in hooks, not UI
```

You can update it anytime or regenerate it through the agent flow.

---

## 🛠 Roadmap

- [ ] Auto-generate context via CLI
- [ ] Web UI for configuration
- [ ] VS Code extension
- [ ] LangChain agent support

---

## 💬 Why It Matters

This framework brings structure to AI-assisted development.

Use it to:
- Standardize how your AI works with you
- Avoid prompt chaos
- Build like a team of 3, not 1

---

## 🧠 Made for modern frontend engineers working with AI.
