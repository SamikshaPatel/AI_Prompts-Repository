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
