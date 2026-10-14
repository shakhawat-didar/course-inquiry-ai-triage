# Workflow Review Notes

Reviewed the supplied n8n export with 21 nodes.

## Implemented in the export
- Authenticated POST webhook and validation for phone + message.
- Google Gemini prompt for intent, lead score, language, summary, Bangla suggested reply, and human escalation.
- Code-node parsing and field validation.
- Hot/medium thresholds of 7 and 4.
- Google Sheets logging, Slack support/hot-lead notifications, and a Gmail action on the medium path.

## Must verify or fix
- Rename the project to reflect Gemini, unless the model node is intentionally changed to Claude.
- Add a deliberate `Respond to Webhook` node on the successful path and on the model-error/fallback path.
- Map the `Log Low Other Inquiry` columns; the exported `columns.value` is empty.
- Confirm the Gmail node operation in n8n. Its label says “Draft,” but the export should not be treated as proof that it creates a draft.
- Validate email before the Gmail action.
- Confirm that the support escalation route is also recorded correctly in the all-runs log.
- Use a dedicated test spreadsheet and test Slack channels before production.
- The public template has had credential bindings, workflow IDs, and the original spreadsheet ID removed/replaced. Reconnect your own credentials and resources after import.
