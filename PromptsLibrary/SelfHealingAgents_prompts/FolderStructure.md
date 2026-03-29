# 📘 **README.md — Multi‑Agent Prompt System for Self‑Healing Engine Generation**

## 🧩 Overview

This repository contains a **multi‑agent prompt system** designed to collaboratively generate a **production‑grade Self‑Healing Automation Engine** for:

- Playwright
- Java
- TestNG
- RestAssured
- Allure

The system uses a **Supervisor Agent** and multiple **Worker Agents**, each responsible for generating a specific part of the framework. The Supervisor coordinates, validates, and merges all outputs into a final JSON codebase.

This README explains:

- Folder structure
- Agent roles
- Workflow diagrams
- State machine
- Limitations
- How to use the prompts

---

# 📁 **Folder Structure**

```
//SelfHealingAgents_prompts/
│
├── blueprint/
│   └── full-multi-agent-blueprint.md
│
├── supervisor/
│   └── supervisor-agent.md
│
├── agents/
│   ├── ui-healing-agent.md
│   ├── api-healing-agent.md
│   ├── storage-agent.md
│   ├── integration-agent.md
│   ├── workflow-agent.md
│   └── qa-validation-agent.md
│
└── limitations/
    └── failure-detection-limitations.md
```

Each file contains a **role‑specific prompt** used by a multi‑agent orchestration system (AutoGen, CrewAI, LangGraph, etc.).

---

# 🧠 **System Architecture**

The system is built around **seven agents**, each with a clear responsibility:

### **1. Supervisor Agent**
- Reads the blueprint
- Assigns tasks
- Collects outputs
- Validates via QA agent
- Merges final JSON

### **2. UI Healing Agent**
- SmartLocator
- UI healing modules
- RecoveryEngine
- Sample Page Objects

### **3. API Healing Agent**
- Schema drift detection
- Field rename mapping
- Data healing
- Sample API client/tests

### **4. Storage Agent**
- HealingStore
- JSON persistence

### **5. Integration Agent**
- SelfHealingOrchestrator
- BasePage integration
- PlaywrightManager integration

### **6. Workflow Agent**
- Multi‑step flow healing

### **7. QA Validation Agent**
- Ensures completeness
- Ensures rule compliance
- Ensures no placeholders
- Ensures folder structure correctness

---

# 🔄 **Multi‑Agent Workflow Diagram**

```
STEP 1: Supervisor loads the blueprint
--------------------------------------
Supervisor Agent
    ↓ reads full-multi-agent-blueprint.md
    ↓ extracts roles, tasks, rules


STEP 2: Supervisor assigns tasks
--------------------------------
Supervisor → UI Healing Agent: "Generate SmartLocator + UI modules"
Supervisor → API Healing Agent: "Generate schema drift modules"
Supervisor → Storage Agent: "Generate HealingStore"
Supervisor → Integration Agent: "Generate Orchestrator + BasePage"
Supervisor → Workflow Agent: "Generate WorkflowHealingModule"
Supervisor → QA Agent: "Validate everything"


STEP 3: Worker agents generate their components
------------------------------------------------
UI Agent → produces UI healing Java classes
API Agent → produces API healing Java classes
Storage Agent → produces HealingStore
Integration Agent → produces Orchestrator + BasePage + Manager
Workflow Agent → produces workflow healing module


STEP 4: Supervisor collects outputs
-----------------------------------
Supervisor receives:
    - UI modules
    - API modules
    - Storage module
    - Integration modules
    - Workflow module


STEP 5: QA Validation Agent checks everything
---------------------------------------------
QA Agent:
    - verifies no missing modules
    - verifies no placeholders
    - verifies rules followed
    - verifies folder structure
    - verifies code consistency


STEP 6: Supervisor merges all outputs
-------------------------------------
Supervisor:
    - merges all Java files
    - merges folder structure
    - merges tests
    - inserts ASCII diagram
    - produces final JSON


STEP 7: Final output returned
-----------------------------
Final JSON delivered:
    - full codebase
    - all modules
    - tests
    - diagram
    - ready to use
```

---

# 🔁 **State Machine Diagram**

```
┌──────────────────────────────────────────────────────────────┐
│                          START                                │
│                  (Blueprint Loaded)                           │
└───────────────┬───────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│                    STATE: TASK_DISPATCH                      │
│  Supervisor assigns tasks to all worker agents                │
└───────────────┬───────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│                    STATE: WORKER_EXECUTION                   │
│  UI, API, Storage, Integration, Workflow agents generate code │
└───────────────┬───────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│                    STATE: COLLECT_OUTPUTS                    │
│  Supervisor gathers all module outputs                        │
└───────────────┬───────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│                    STATE: VALIDATION                         │
│  QA Agent validates:                                          │
│   - completeness                                               │
│   - rule compliance                                            │
│   - structure correctness                                      │
│   - no placeholders                                            │
└───────────────┬───────────────────────────────────────────────┘
                │
                ├───────────► If validation fails:
                │               STATE: REWORK
                │               (Supervisor reassigns tasks)
                │               → return to WORKER_EXECUTION
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│                    STATE: MERGE_OUTPUTS                      │
│  Supervisor merges all modules into final JSON                │
└───────────────┬───────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│                    FINAL STATE: COMPLETE                     │
│  Final JSON codebase delivered                                │
└──────────────────────────────────────────────────────────────┘
```

---

# 🌳 **Graphviz DOT Diagram**

```
digraph MultiAgentSystem {
    rankdir=LR;
    node [shape=rectangle, style=filled, fillcolor="#eef2ff", fontsize=12];

    Start [label="START\n(Blueprint Loaded)", fillcolor="#d1eaff"];
    Dispatch [label="TASK_DISPATCH\n(Supervisor assigns tasks)"];
    WorkerExec [label="WORKER_EXECUTION\n(Agents generate modules)"];
    Collect [label="COLLECT_OUTPUTS\n(Supervisor gathers results)"];
    Validate [label="VALIDATION\n(QA Agent checks everything)"];
    Rework [label="REWORK\n(If validation fails)"];
    Merge [label="MERGE_OUTPUTS\n(Supervisor merges modules)"];
    Complete [label="COMPLETE\n(Final JSON delivered)", fillcolor="#c8ffd4"];

    Start -> Dispatch;
    Dispatch -> WorkerExec;
    WorkerExec -> Collect;
    Collect -> Validate;

    Validate -> Merge [label="valid"];
    Validate -> Rework [label="invalid"];

    Rework -> WorkerExec;

    Merge -> Complete;
}
```

---

# ⚠️ **Failure Detection Limitations**

The self‑healing engine **cannot** automatically detect or heal:

- Business logic failures
- Authentication/session failures
- Backend outages
- Visual/layout regressions
- Randomized DOM structures
- Parallel execution race conditions
- Semantic API changes
- Incorrect test assertions
- Infrastructure instability
- Browser‑specific rendering bugs

These require human intervention or backend fixes.

---

# 🚀 **How to Use This Prompt System**

1. Load the **Supervisor Agent** with the blueprint.
2. The Supervisor dispatches tasks to worker agents.
3. Worker agents generate their modules.
4. QA agent validates everything.
5. Supervisor merges outputs into final JSON.
6. The final JSON contains the **entire self‑healing engine codebase**.

---