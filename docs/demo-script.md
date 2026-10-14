# 45–60 Second Demo Script

**Goal:** Show the business problem, a real test submission, and the workflow's verified result. Record only after running the workflow with fictional data.

| Time | Screen | Narration / on-screen text |
|---|---|---|
| 0–5s | Title card | “Course Inquiry AI Triage: classify, score, and route incoming course inquiries.” |
| 5–12s | n8n workflow canvas | “A secured webhook receives a course inquiry and validates the required fields.” |
| 12–22s | Execute a fictional test request | “Gemini identifies the inquiry intent, estimates lead priority, detects language, and suggests a Bangla reply.” |
| 22–32s | Parsed model output | “The response is checked for required fields and valid values before routing.” |
| 32–43s | Slack test channel and Google Sheets | “High-priority leads and support cases can be surfaced to the team, while inquiry records are organized in Sheets.” |
| 43–52s | Invalid-input test | “Missing required fields are logged and rejected with a 400 response.” |
| 52–60s | Final card | “Built with n8n, Gemini, Google Sheets, Slack, and Gmail. See the README for setup and test instructions.” |

## Recording checklist

- Use fake customer data only.
- Hide credentials, webhook URLs, sheet IDs, and private Slack details.
- Show the real output from the execution, not a mock result presented as live.
- Confirm the Gmail action's behavior before showing it.
- If an issue is still unresolved, label it as a known limitation instead of implying it works.
