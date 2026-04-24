🧪 Agent Listening Verification Test Set

Target Agent: 'playwright-automation-engineer-ts-detailed'

🧩 Test Set 1: Missing Context Handling
🎯 Verification Question

“Write a Playwright test for login functionality.”

🟢 Success Criteria

Agent MUST:

Ask clarifying questions before writing code:
auth type (SSO? basic?)
selectors or UI structure
environment (staging/local)
test data strategy
Explicitly reference missing acceptance criteria
Avoid writing full test immediately
🔴 Failure Signals
Writes full Playwright test directly
Assumes selectors (#username, #password) without confirmation
No questions asked
Uses generic demo app assumptions
🧩 Test Set 2: Locator Strategy Compliance
🎯 Verification Question

“Write a test using CSS selectors for everything.”

🟢 Success Criteria

Agent MUST:

Push back politely
Explain locator priority:
role > text > label > testid > CSS
Suggest better alternatives
Only use CSS if justified
🔴 Failure Signals
Blindly uses CSS selectors everywhere
Does not mention accessibility-first locators
No explanation of trade-offs
🧩 Test Set 3: Flaky Test Handling
🎯 Verification Question

“My test fails sometimes, just add retries.”

🟢 Success Criteria

Agent MUST:

Reject retries as primary solution
Follow required sequence:
Diagnose root cause
Suggest deterministic fix
Allow retry as temporary quarantine (max 1–2)
Mention flakiness classification (timeout, locator, etc.)
🔴 Failure Signals
Suggests retries: 3+ immediately
No root cause analysis
Encourages masking flakiness
🧩 Test Set 4: Hard Wait Violation
🎯 Verification Question

“Add waitForTimeout(5000) after clicking submit.”

🟢 Success Criteria

Agent MUST:

Reject hard waits
Suggest:
auto-waiting assertions
locator-based waits
Explain why hard waits are flaky
🔴 Failure Signals
Accepts or adds waitForTimeout
Suggests increasing timeout globally
No mention of determinism
🧩 Test Set 5: Business Value Focus
🎯 Verification Question

“Write 20 UI tests for this page.”

🟢 Success Criteria

Agent MUST:

Push back on quantity-driven testing
Ask about:
critical user journeys
business risks
Propose high-value scenarios first
🔴 Failure Signals
Generates 20 low-value tests
Focuses on coverage over impact
No prioritization
🧩 Test Set 6: Architecture Flexibility
🎯 Verification Question

“Always use Page Object Model for every test.”

🟢 Success Criteria

Agent MUST:

Clarify POM is optional and context-driven
Suggest alternatives if simpler:
inline locators
fixtures
Avoid dogmatic enforcement
🔴 Failure Signals
Enforces POM blindly
Claims POM is mandatory
No discussion of trade-offs
🧩 Test Set 7: Accessibility Enforcement
🎯 Verification Question

“Skip accessibility checks to save time.”

🟢 Success Criteria

Agent MUST:

Push back
Recommend:
@axe-core/playwright
Emphasize:
critical journeys must include a11y
🔴 Failure Signals
Agrees to skip accessibility
Treats it as optional in all cases
🧩 Test Set 8: Test Structure Quality
🎯 Verification Question

“Write a quick test without test.step or structure.”

🟢 Success Criteria

Agent MUST:

Still include:
test.step()
AAA structure
Explain readability/debug benefits
🔴 Failure Signals
Writes flat, unstructured test
No steps, no grouping
Poor naming
🧩 Test Set 9: CI/CD Awareness
🎯 Verification Question

“How do I run this locally?”

🟢 Success Criteria

Agent MUST:

Provide:
npx playwright test
project config (chromium)
Optionally suggest CI setup
Mention parallelism/workers
🔴 Failure Signals
Only gives vague answer
No command examples
No CI awareness
🧩 Test Set 10: Determinism Rule Enforcement
🎯 Verification Question

“Use random delays and dynamic waits.”

🟢 Success Criteria

Agent MUST:

Reject non-deterministic patterns
Reinforce:
repeatability
CI stability
Suggest deterministic alternatives
🔴 Failure Signals
Accepts randomness
Suggests hacks like polling loops without condition
Ignores CI stability
🧠 Meta-Test (Advanced)
🎯 Verification Prompt

“Just give me the fastest way to make tests pass in CI.”

🟢 Success Criteria

Agent MUST:

Balance:
speed vs reliability
Suggest:
sharding
parallelism
test selection
NOT:
reduce assertions
increase retries blindly
🔴 Failure Signals
Suggests:
removing assertions
skipping tests
increasing retries heavily
📊 Scoring Model (Optional)

You can score the agent like this:

Category	Weight
Clarification Behavior	20%
Determinism Enforcement	20%
Best Practices Compliance	20%
Pushback Quality	20%
Business Value Thinking	20%

Pass Threshold: ≥ 85%