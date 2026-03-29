# Developer Onboarding Guide
Welcome to the Multi‑Agent Self‑Healing Engine Prompt System.

This guide helps new contributors understand:

- What the system does
- How the agents work
- How to run the workflow
- How to safely modify prompts
- How to extend the system

---

# 🚀 1. What This System Does

This project defines a **multi‑agent prompt architecture** that generates a complete **Self‑Healing Automation Framework** for:

- Playwright (UI automation)
- Java
- TestNG
- RestAssured (API automation)
- Allure (reporting)

The system uses **multiple specialized agents** that collaborate to produce:

- SmartLocator engine
- Healing modules
- Orchestrator
- BasePage + PlaywrightManager
- API schema drift handlers
- Workflow healing
- Tests
- Diagrams
- Final JSON codebase

---

# 🧠 2. How the Multi‑Agent System Works

### Agents:

| Agent | Responsibility |
|-------|----------------|
| Supervisor | Orchestration, merging, validation |
| UI Healing Agent | SmartLocator + UI modules |
| API Healing Agent | Schema drift + data healing |
| Storage Agent | HealingStore persistence |
| Integration Agent | Orchestrator + BasePage + Manager |
| Workflow Agent | Multi‑step flow healing |
| QA Validation Agent | Rule enforcement + completeness |

Each agent has its own prompt under `/prompts/agents`.

---

# 🔄 3. Workflow Summary

1. Supervisor loads the blueprint
2. Supervisor assigns tasks to worker agents
3. Worker agents generate their modules
4. Supervisor collects outputs
5. QA agent validates everything
6. Supervisor merges final JSON
7. Final codebase is produced

See `/prompts/blueprint/full-multi-agent-blueprint.md` for details.

---

# 🧭 4. Running the Multi‑Agent Workflow

You can use:

- AutoGen
- CrewAI
- LangGraph
- Microsoft multi‑agent orchestration patterns

Steps:

1. Load the **Supervisor Agent** with the blueprint
2. Register all worker agents
3. Start the workflow
4. Inspect the final JSON output

---

# 🛠 5. How to Modify Prompts Safely

### ✔ Always check the blueprint
It defines the system contract.

### ✔ Modify only one agent at a time
Keep responsibilities isolated.

### ✔ Validate with the QA agent
Ensure:

- No missing modules
- No placeholders
- No rule violations

### ✔ Keep prompts deterministic
Avoid vague instructions like:

- “Do something like…”
- “Generate whatever is needed…”

### ✔ Maintain output structure
The final JSON must always match the required schema.

---

# 🧪 6. Testing Your Changes

After modifying prompts:

1. Run the multi‑agent workflow
2. Ensure all modules are generated
3. Ensure the Supervisor merges correctly
4. Ensure the QA agent approves
5. Inspect the final JSON for completeness

---

# ⚠️ 7. Known Limitations

The self‑healing engine **cannot** automatically detect or fix:

- Business logic failures
- Authentication/session issues
- Backend outages
- Visual/layout regressions
- Randomized DOM structures
- Parallel execution race conditions
- Semantic API changes
- Incorrect test assertions
- Infrastructure instability

See `/prompts/limitations/failure-detection-limitations.md`.

---

# 🌱 8. Recommended First Tasks for New Contributors

- Improve agent prompts for clarity
- Add new diagrams
- Enhance QA validation rules
- Add examples to the blueprint
- Improve Storage Agent persistence logic

---

# 🎉 Welcome Aboard

You’re now ready to contribute to one of the most advanced prompt‑driven automation architectures.

If you need help, open an issue or reach out to the maintainers.
