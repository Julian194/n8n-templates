**Title:** Capture every workflow failure once, notify instantly, and deduplicate in GitHub Issues

---

Global error workflow for n8n that sends immediate push alerts and opens (or updates) GitHub issues without creating duplicate noise.

## How it works

1. Triggered by n8n's **Error Trigger** when any workflow fails
2. Formats a structured error payload (workflow, node, error type, execution link)
3. Sends an instant **ntfy** push notification
4. Builds stable dedup fingerprints from normalized error content
5. Searches recent GitHub issues for matching fingerprints/titles
6. Creates a new issue if no match exists, or comments on an existing issue
7. Throttles duplicate comments (30-minute cooldown)

## Setup

1. Set your **GitHub credential** on GitHub API nodes
2. Replace `your-org/your-ops-repo` in:
   - the GitHub node repository settings
   - the `repo` variable in **Build Dedup Query**
3. Replace the ntfy topic URL in **Ntfy Notification** (`https://ntfy.sh/your-n8n-alerts`)
4. Set this workflow as the **Error Workflow** in your other workflows (or globally)
5. Activate the workflow

## Customization

- **Dedup window:** change `sinceDate` logic (default: last 14 days)
- **Comment cooldown:** change `dedupCommentWindowMinutes` (default: 30)
- **Normalization rules:** adjust replacements in `normalize()` for your error patterns
- **Notification channels:** keep ntfy only, or add Slack/email nodes as needed
