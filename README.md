# n8n Templates

Reusable n8n workflows for monitoring, error handling, and utilities.

## Workflows

| Workflow | Description | Purpose |
|---|---|---|
| `global-error-handler-v2.json` | [`descriptions/global-error-handler-v2.md`](descriptions/global-error-handler-v2.md) | Central error workflow with GitHub issue dedup + notification flow |
| `monitor-missing-error-handlers.json` | [`descriptions/monitor-missing-error-handlers.md`](descriptions/monitor-missing-error-handlers.md) | Detect active workflows that do not have an Error Workflow configured |
| `monitor-scheduled-workflow-health.json` | [`descriptions/monitor-scheduled-workflow-health.md`](descriptions/monitor-scheduled-workflow-health.md) | Detect scheduled/polling workflows that silently stopped running |
| `openrouter-model-monitor.json` | [`descriptions/openrouter-model-monitor.md`](descriptions/openrouter-model-monitor.md) | Find deprecated OpenRouter model IDs used across workflows |
| `sequential-prompts.json` | [`descriptions/sequential-prompts.md`](descriptions/sequential-prompts.md) | Example looped prompt execution with shared AI memory |
| `timezone-lookup-german.json` | [`descriptions/timezone-lookup-german.md`](descriptions/timezone-lookup-german.md) | Resolve timezone from city/country (German input compatible) |

## Notes

- Workflow descriptions follow a consistent format: **Title**, **How it works**, **Setup**, **Customization**.
- Replace placeholder values (e.g. repo names, usernames, topics) before production use.
