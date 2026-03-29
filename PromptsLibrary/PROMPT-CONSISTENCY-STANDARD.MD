# PROMPT CONSISTENCY STANDARD  
**File:** `/prompts/PROMPT-CONSISTENCY-STANDARD.md`

This document defines the **mandatory standards** for writing, updating, and maintaining all prompt files in the multi‑agent self‑healing engine repository.

The goal is to ensure:

- Zero ambiguity  
- Deterministic agent behavior  
- Consistent structure across all prompts  
- Predictable multi‑agent orchestration  
- Long‑term maintainability  

All contributors MUST follow this standard.

---

# 1. Prompt Structure Requirements

Every agent prompt MUST follow this exact structure:

1. **Title**  
2. **File path**  
3. **Role definition**  
4. **Purpose**  
5. **Responsibilities**  
6. **Strict Rules (Zero Ambiguity)**  
7. **Supported Automation Frameworks**  
8. **Supported AI Orchestration Engines**  
9. **Outputs the agent MUST produce**  
10. **Final instruction**

This structure MUST NOT be modified.

---

# 2. Naming Conventions

- File names MUST use lowercase with hyphens:  
  - `ui-healing-agent.md`  
  - `api-healing-agent.md`  
  - `supervisor-agent.md`

- Titles MUST use uppercase agent names:  
  - `# UI HEALING AGENT`

- File path MUST be included at the top:  
  - `**File:** /prompts/agents/ui-healing-agent.md`

---

# 3. Blueprint Referencing Standard

Agents MUST reference the blueprint **by concept**, NOT by filename.

✔ Allowed:  
> You MUST follow the **Full Multi‑Agent Blueprint** and all strict Do/Don’t rules.

❌ Not allowed:  
> You MUST follow `full-self-healing-multi-agent-blueprint.md`.

Reason:  
File names can change; conceptual references do not.

---

# 4. Zero Ambiguity Requirements

All prompts MUST:

- Use explicit, mandatory language  
  - “You MUST…”  
  - “You MUST NOT…”  
  - “You MUST generate…”  
- Avoid vague verbs  
  - ❌ “Try to…”  
  - ❌ “Consider…”  
  - ❌ “May…”  
- Avoid optional phrasing  
  - ❌ “If possible…”  
  - ❌ “When appropriate…”  
- Avoid assumptions about environment  
  - No filesystem references  
  - No external dependencies  

Prompts MUST be deterministic:  
**Same input → same output.**

---

# 5. Scope Enforcement

Each agent MUST stay within its defined scope.

Examples:

- UI Healing Agent MUST NOT generate API modules  
- API Healing Agent MUST NOT generate UI modules  
- Storage Agent MUST NOT generate orchestrator logic  
- Integration Agent MUST NOT generate HealingStore  
- QA Agent MUST NOT generate code  

Cross‑scope leakage is strictly prohibited.

---

# 6. Output Requirements

Every agent MUST:

- Produce complete, compilable Java code  
- Include all necessary imports  
- Include no TODOs or placeholders  
- Follow the folder structure defined in the blueprint  
- Produce only the files listed in its “Outputs” section  

Agents MUST NOT:

- Generate partial implementations  
- Generate undefined classes  
- Modify the final JSON schema  

---

# 7. Supported Automation Frameworks (Mandatory)

All prompts MUST target:

- Playwright for Java  
- TestNG  
- RestAssured  
- Allure  
- Java 11+  

Prompts MUST NOT generate code for:

- Selenium  
- Cypress  
- Puppeteer  
- WebDriverIO  
- Any non‑Java frameworks  

---

# 8. Supported AI Orchestration Engines

Prompts MUST be compatible with:

- Microsoft multi‑agent orchestration  
- AutoGen  
- CrewAI  
- LangGraph  
- OpenAI Swarm‑style systems  
- Custom multi‑agent controllers  

Prompts MUST NOT assume:

- File access  
- Network access  
- External tools  
- Shared memory  

---

# 9. Language & Tone Requirements

Prompts MUST:

- Use clear, direct, imperative language  
- Avoid conversational tone  
- Avoid unnecessary explanation  
- Avoid rhetorical questions  
- Avoid filler words  

Prompts MUST read like **technical specifications**, not tutorials.

---

# 10. Determinism & Stability

Prompts MUST:

- Produce stable output across runs  
- Avoid randomness  
- Avoid subjective interpretation  
- Avoid open‑ended creativity  

Agents MUST NOT:

- Invent new modules  
- Modify architecture  
- Change naming conventions  
- Add new responsibilities  

---

# 11. Validation Requirements

The QA Validation Agent MUST enforce this standard.

If any prompt violates this standard, QA MUST:

- Reject the output  
- Request regeneration  
- Provide explicit reasons  

---

# 12. Versioning & Change Control

Any change to:

- Blueprint  
- Supervisor prompt  
- Agent prompts  
- This standard  

MUST be reviewed and approved by maintainers.

Changes MUST be:

- Documented  
- Justified  
- Backwards‑compatible  

---

# 13. Final Instruction

All prompts in this repository MUST comply with this **Prompt Consistency Standard**.

This document is the **single source of truth** for prompt structure, style, and rules.

No deviations.  
No ambiguity.  
No exceptions.
