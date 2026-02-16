**Title:** Detect active workflows that are missing an Error Workflow

---

Automatically checks your active n8n workflows and raises an alert if any trigger-based workflow has no error handler configured.

## How it works

1. Runs on a daily schedule (default: 9am)
2. Fetches all workflows via the n8n API
3. Skips archived workflows and workflows tagged `skip-monitoring`
4. Detects workflows that have trigger nodes (schedule, webhook, email, chat, etc.)
5. Checks whether `settings.errorWorkflow` is configured
6. Throws a single error listing all missing workflows

## Setup

1. Add your **n8n API credential** to **Get Active Workflows**
2. Tag this workflow with `skip-monitoring` so it does not alert on itself
3. Configure an **Error Workflow** for this monitor so alerts are delivered
4. Activate the workflow

## Customization

- **Schedule:** adjust trigger timing in **Daily Check at 9am**
- **Exclusion tag:** change `skipTag` in **Check Error Handlers**
- **Trigger scope:** update the `triggerTypes` array if you want stricter/looser checks
