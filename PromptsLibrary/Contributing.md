# Contributing to the Multi‑Agent Self‑Healing Engine Prompt System

Thank you for your interest in contributing.  
This project uses a **multi‑agent architecture** to generate a complete, production‑grade **Self‑Healing Automation Engine** for Playwright + Java + TestNG + RestAssured + Allure.

This document explains how to contribute safely, consistently, and effectively.

---

## 🧩 Project Structure

All prompts live under the `/<type>_prompts` directory:


Each file defines the behavior of a specific agent in the system.

---

## 🧠 Contribution Principles

### ✔ Follow the Blueprint
All contributions must remain consistent with:

- The **full multi-agent blueprint**
- The **strict Do/Don't rules**
- The **output format requirements**
- The **agent responsibilities**

### ✔ Maintain Determinism
Prompts must produce:

- Predictable output
- No randomness
- No ambiguous instructions

### ✔ Keep Prompts Modular
Each agent prompt must:

- Define a single role
- Avoid overlapping responsibilities
- Avoid referencing internal implementation details of other agents

### ✔ No Placeholder Code
Prompts must never instruct agents to generate:

- TODOs
- Stubs
- Partial implementations
- “Fill this later” sections

### ✔ No Direct Code Modification
Agents generate code — they do not modify existing code.  
All healing logic must be **data‑driven**, not code‑rewriting.

---

## 🔄 Contribution Workflow

### 1. Fork the repository
Create your own working copy.

### 2. Create a feature branch
Use descriptive names:

