Note:  to be updated as per your project structure and needs. This is just a sample template to get started with defining global instructions for all agents in the repository.
---

# copilot-instructions.md

## 🧭 Purpose

This file defines **global governance rules** for all AI agents (Copilot/LLM-based) operating in this repository.

It ensures:

* Consistent behavior across agents
* Controlled file generation
* Clear separation of responsibilities
* High-quality, deterministic outputs

---

## ⚖️ Instruction Priority (Conflict Resolution)

When instructions conflict, follow this priority order:

1. **User Prompt (Highest Priority)**
2. **Agent-Specific Instruction Files (agents/*.md)**
3. **This Global File (copilot-instructions.md)**

Agents MUST NOT override higher-priority instructions.

---

## 🏗️ Project Structure

All agents MUST respect the repository structure:

* `tests/` → Playwright UI/E2E tests (`*.spec.ts`)
* `api-tests/` → API test cases (`*.api.ts`)
* `pages/` → Page Object Models
* `fixtures/` → Test data builders & fixtures
* `utils/` → Shared utilities/helpers
* `docs/` → QA strategy, plans, documentation
* `.github/workflows/` → CI/CD pipelines

### Rules

* Do NOT create new top-level folders without explicit instruction
* Do NOT move files across directories unless instructed
* Keep UI and API concerns strictly separated

---

## 📁 File Generation Rules (STRICT)

### Allowed File Types

* `*.spec.ts` → UI/E2E tests only
* `*.api.ts` → API tests only
* `*.fixture.ts` → Fixtures / data builders
* `*.page.ts` → Page Objects
* `*.util.ts` → Utilities

### Naming Conventions

* Use **kebab-case** for file names

    * Example: `login.spec.ts`, `user-profile.api.ts`
* Test files must reflect feature/page name

### Hard Constraints

* NEVER create files outside defined folders
* NEVER overwrite existing files unless explicitly instructed
* NEVER generate duplicate files for the same feature
* ALWAYS produce complete, runnable code (no placeholders unless asked)

---

## 🤖 Agent Scope Definition (applyTo)

Agents MUST operate ONLY within their defined scope.

---

### 🧪 Playwright Automation Agent

**applyTo:** `tests/**/*.ts`

**Scope:**

* UI/E2E test creation using Playwright (TypeScript)
* Test debugging and stabilization
* Locator strategy improvements
* CI execution optimization

**Out of Scope:**

* API test creation
* Backend logic changes
* Product feature design

---

### 🔌 API Testing Agent

**applyTo:** `api-tests/**/*.ts`

**Scope:**

* API test case design and validation
* Request/response assertions
* Schema and contract validation

**Out of Scope:**

* UI automation
* Playwright test generation

---

### 📊 QA Manager / Strategy Agent

**applyTo:** `docs/**/*.md`

**Scope:**

* Test strategy
* Risk analysis
* Planning and documentation

**Out of Scope:**

* Writing executable test code

---

## 🧱 Output Standards

All agents MUST:

* Produce **production-ready code**
* Use **TypeScript strict mode**
* Avoid unnecessary comments
* Prefer clarity over verbosity
* Follow project conventions consistently

### Code Quality Expectations

* Deterministic and repeatable
* CI-stable (no flaky patterns)
* Readable and maintainable

---

## 🚫 Global Quality Rules (NON-NEGOTIABLE)

### General

* DO NOT assume missing context → ask questions
* DO NOT invent APIs, selectors, or flows
* DO NOT introduce new frameworks without instruction

### UI Testing (Playwright)

* NO `waitForTimeout()` or hard-coded delays
* Use auto-waiting assertions (`await expect(...)`)
* Prefer locator priority:

    1. Role
    2. Text
    3. Label
    4. data-testid
    5. CSS/XPath (last resort)

### Flakiness

* DO NOT hide flakiness with retries
* Retries allowed: **max 1–2 (temporary only)**
* Always suggest root cause fixes first

### Test Design

* Tests MUST validate business behavior (not implementation details)
* Avoid redundant or low-value tests
* Prefer high-impact scenarios over volume

---

## 🧪 Determinism Rule

All generated tests MUST be:

* Deterministic
* Repeatable
* Independent
* Free from race conditions

---

## ⚙️ Execution Awareness

Agents MUST assume:

* Tests run in CI (headless mode)
* Parallel execution is enabled
* Environment may vary (local, CI, staging)

### Therefore:

* Avoid environment-specific assumptions
* Do not rely on shared state between tests

---

## 🔐 Safety & Stability Guardrails

* Do NOT modify CI/CD pipelines unless explicitly asked
* Do NOT commit large artifacts (e.g., Playwright traces)
* Do NOT disable or skip tests permanently
* Do NOT bypass assertions to “make tests pass”

---

## 🧠 When in Doubt

Agents MUST:

* Ask concise clarifying questions
* State assumptions explicitly if forced to proceed
* Prefer correctness over speed

---

## 🚀 Consistency Rules (Anti-Drift)

* Do NOT introduce new patterns without justification
* Do NOT mix UI and API logic in the same test
* Do NOT deviate from folder structure
* Maintain consistency with existing codebase patterns

---

## 📌 Summary

This file enforces:

* Clear **agent boundaries**
* Strict **file system discipline**
* High **test quality standards**
* Reliable **CI-ready outputs**

Agents that do not follow these rules are considered **non-compliant**.


