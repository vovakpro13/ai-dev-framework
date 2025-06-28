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
## ⚙️ How to Start Creating Your AI Context

To begin creating your custom AI context, open your AI agent (Cursor, Gemini CLI, Copilot) and start it with the following prompt:

```
Read and execute instructions in /agent/README.md
```

This command will trigger a step-by-step dialog in the agent to configure your project’s rules and structure.

---

## 🤖 What to Do After the Context Is Created

After the agent asks all the questions and generates the `AGENT_CONTEXT.md` file, you need to place this file in the appropriate location depending on your AI agent:

### 🌀 Gemini CLI

- Place the `AGENT_CONTEXT.md` file in the root of your project (where you run gemini)
- Use it with the `--context` flag, for example:
```
gemini –context ./AGENT_CONTEXT.md
```
**Or alternatively**, create a file named `GEMINI.md` in the project root and copy instructions from `AGENT_CONTEXT.md`:

Then, Gemini will automatically load the context file when starting.

---

### 🧠 Cursor IDE

- Copy or move the `AGENT_CONTEXT.md` file into the `.cursor/context/` folder
- Activate the agent in the IDE and tell it:
```
Use the context from .cursor/context/AGENT_CONTEXT.md
```

---

### 🤖 GitHub Copilot

- Copilot does not currently support context files directly
- Instead, add a comment with a brief description of your rules at the top of important files (e.g., `README.md` or `App.tsx`):

```ts
// Copilot Context:
// - Structure: feature-sliced
// - State: Zustand
// - Styling: styled-components
// - Components: typed, logic-free
// - API: custom fetch hook per endpoint
```
This helps Copilot better understand your project context.

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
