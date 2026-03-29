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
