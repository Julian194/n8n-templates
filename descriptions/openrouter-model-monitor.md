**Title:** Monitor OpenRouter model IDs used in workflows and flag deprecated ones

---

Scans all n8n workflows for OpenRouter model references and checks them against the live models.dev catalog, so outdated model IDs are caught before runtime failures.

## How it works

1. Runs weekly (and can also be run manually)
2. Fetches all workflows from the n8n API
3. Extracts model IDs from:
   - LangChain OpenRouter nodes
   - HTTP Request nodes calling `openrouter.ai`
   - OpenAI-compatible nodes that use provider-style model IDs (e.g. `anthropic/...`)
4. Fetches the current OpenRouter model catalog from `https://models.dev/api.json`
5. Compares discovered model IDs to currently available IDs
6. Raises an error with exact workflow + node locations when unavailable IDs are found

## Setup

1. Add your **n8n API credential** to **Get All Workflows**
2. Set an **Error Workflow** in this workflow's settings for alert delivery
3. Activate the workflow

## Customization

- **Schedule:** change **Weekly Check** cadence
- **Scanner scope:** adjust extraction rules in **Extract OpenRouter Models**
- **Alert format:** customize the message in **Format Error Message**
