# API Test Case Generator - Implementation Guide

This guide provides technical instructions for integrating the modular prompt library into various AI environments. It ensures that the **Senior API QA Engineer** persona and the **Testing Protocol** are correctly applied to generate high-quality, automation-ready test cases.

---

## 1. Simple LLM Interface (Gemini, ChatGPT, Copilot, Claude)

When using a standard chat interface, you must establish "Session Grounding" by providing the rules before the task.

* **Step 1 (The Foundation):** Copy and paste the entire content of `instruction.md` into the chat. This ensures the model understands the **16 mandatory categories** (Functional, Negative, Security, etc.) and the **Happy/Unhappy path** rules.
* **Step 2 (The Persona):** Paste the content of `api_test_case_generator_agent_prompt.md`. This adopts the **Senior API QA Engineer (15+ years experience)** mindset and activates the specific **Mindset** for failure scenarios.
* **Step 3 (The Task):** Provide your API details (Endpoint, Method, Schema).
* **Protocol:** Explicitly instruct the model: *"Use the file naming convention `API_Test_Cases_[Name]_[Timestamp].md` for your output and ensure all 16 categories are present or explained."*

---

## 2. Multi-Agent Frameworks (CrewAI, AutoGen)

These frameworks allow you to map the YAML metadata directly into the agent's class attributes for better autonomy.

* **Agent Identity:** Map the `name`, `agent_role`, and `description` from the metadata in `api_test_case_generator_agent_prompt.md` to the Agent's `role` and `goal` parameters.
* **Knowledge/Backstory:** Use the content of `instruction.md` as the `backstory` for the agent. This prevents the agent from falling back on generic testing behaviors and forces adherence to the **Strict Constraints**.
* **Tool Configuration:** Ensure the agent is equipped with a `File_Writer_Tool` (or equivalent). Configure the tool's base path to `/generated/APITests` as defined in the **File Storage Instructions**.
* **Execution:** Assign a `Task` that points to the **Output Requirements** in the prompt file to ensure all fields like TC_ID, Preconditions, and Test Data are included in the final Markdown file.

---

## 3. Orchestration Platforms (Flowise, LangFlow)

In visual orchestration tools, the files act as the "System Message" grounding for the LLM node.

* **System Message Injection:** Connect a "Text File" or "Document Loader" node containing `instruction.md` directly to the **System Message** input of your Chat Model.
* **Prompt Grounding:** Use a "Custom Prompt Template" node that references the agent's mindset: *"Act as the Senior API QA Engineer defined in the agent prompt. You are strictly governed by the 16-category testing protocol."*
* **File Persistence:** If using a Flowise "Tool Agent," add a tool that can write to the local directory `/generated/APITests`.
* **Self-Review Loop:** If your platform supports loops, add a conditional node that checks for the **Self-Review (MANDATORY)** criteria defined in the agent prompt before finalizing the output.

---

## 📂 File Repository Reference

| File | Primary Use | Key Data Points |
| :--- | :--- | :--- |
| `api_test_case_generator_agent_prompt.md` | **Identity/Role** | Persona, Mindset, Field Requirements, Self-Review Rules |
| `instruction.md` | **Protocol/Logic** | 16 Categories, File Naming (Timestamp), Error Handling Rules |
| `/generated/APITests` | **Output Path** | Standardized location for all generated `.md` test suites |

---
