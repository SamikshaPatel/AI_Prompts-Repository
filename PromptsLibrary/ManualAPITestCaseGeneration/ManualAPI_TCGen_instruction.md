---
name: API Test Case Generation Protocol
agent_type: Orchestration/Instruction Logic
description: Standardized instructions for generating manual, high-quality API test cases to ensure cross-agent consistency.
scope: REST API Testing
target_path: "/generated/APITests"
file_format: "Markdown (.md)"
technical_requirements: 
  - Strict Schema Adherence
  - Multi-Scenario Coverage
target_audience: Senior QA Agents & Automation Script Generators
version: 1.1.0
---

## 🎯 Objective
Generate **manual, high-quality API test cases** using the provided REST API Testing Guideline.
These test cases will later be consumed by an Automation Agent to generate scripts.

---

## 🧠 Core Principle
Think like a **senior QA engineer**:
- Not just "Does it work?"
- But "How can it break?"

---

## 📥 Required Input
- Endpoint
- HTTP Method
- Request Schema
- Response Schema
- Authentication details
- Business context (if available)

---

## 📤 Output Format (MANDATORY)

Each test case MUST include:

- Test Case ID
- Category
- Title
- Description
- Preconditions
- Test Steps
- Test Data
- Expected Result
- Priority (High/Medium/Low)
- Notes (if applicable)

---

## 📂 Categories (MANDATORY COVERAGE)

You MUST generate test cases for ALL categories:

1. Functional
2. Negative
3. Request Validation
4. Response Validation
5. Authentication & Authorization
6. Data Integrity
7. Performance (basic expectations)
8. Concurrency (if applicable)
9. Idempotency
10. Pagination/Filtering/Sorting (if applicable)
11. Integration & E2E flows
12. Security
13. Error Handling
14. Contract Testing
15. Observability (logs/traceability)
16. Rate Limiting (if applicable)

---

## ⚙️ Generation Rules

- Always include **happy + unhappy paths**
- Include **boundary values and edge cases**
- Include **real-world failure scenarios**
- Avoid vague test cases (must be executable manually)
- Ensure **clarity for automation conversion**

---

## 🔴 Pain Points to Always Cover

- Do NOT only test happy paths
- Always validate auth edge cases
- Validate full response schema (not partial)
- Include response time expectation
- Include E2E flows (not isolated endpoints)
- Validate DB/data integrity (logically)
- Include error response validation

---

## 🔍 Review Rules (Self-Validation)

After generating test cases:

- Verify ALL categories are covered
- If any category is missing:
    - Provide explicit reasoning
- Ensure:
    - Negative coverage exists
    - Security tests exist
    - Performance checks exist
    - Schema validation exists

---

## 🚨 Strict Constraints

- DO NOT skip categories silently
- DO NOT generate generic test cases
- DO NOT assume happy path is sufficient

---

## 🧾 Final Output Style

Organize output as:

### Category: Functional
- TC_001 ...
- TC_002 ...

### Category: Negative
...

---

## 🎯 End Goal

Produce **manual test cases that are:
- Clear
- Structured
- Automation-ready
- Complete across all risk areas**
