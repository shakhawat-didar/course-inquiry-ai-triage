# Test Plan

Use fictional test records and a non-production copy of the workflow. Record the actual route, Sheets row, Slack notification, email behavior, and HTTP response for every case.

| Case | Input / setup | Expected behavior to verify |
|---|---|---|
| Hot lead | Valid phone/message; model score 7–10 | Hot lead Slack alert and Hot sheet row |
| Medium lead | Valid fields; model score 4–6 | Medium sheet row and Gmail node behavior verified |
| Low lead | Valid fields; score 1–3; non-spam | Low/Other row with complete mapped columns |
| Spam | Model intent `spam` | Spam sheet row; no sales follow-up |
| Complaint | Intent `complaint` or `needs_human: true` | Support escalation in Slack and all-runs log |
| Missing phone | Omit `phone` | Validation failure logged and HTTP 400 |
| Missing message | Omit `message` | Validation failure logged and HTTP 400 |
| Invalid model JSON | Simulate empty or malformed model response | Fallback is logged and caller receives a deliberate error response |
| Missing email | Valid phone/message but no email; force medium score | Workflow handles the case safely without an unhandled Gmail failure |
| Sheets failure | Revoke/disable test credential | Failure is visible and does not silently appear successful |
| Slack failure | Invalid test channel/credential | Failure is visible and recoverable |
| Duplicate request | Send same request twice | Confirm whether duplicates should be accepted or deduplicated |

## Test evidence log

For each run, record:
- Date/time
- Case ID (no real customer data)
- n8n execution status
- Expected route / actual route
- Sheets write successful?
- Slack alert correct?
- Gmail operation and result
- HTTP status/body
- Notes / fix needed

Do not mark a case as passed until the live execution has been checked.
