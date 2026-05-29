---
name: ai-insights-feature-development
description: Workflow command scaffold for ai-insights-feature-development in WeFlow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /ai-insights-feature-development

Use this workflow when working on **ai-insights-feature-development** in `WeFlow`.

## Goal

Implements or updates the AI insights feature, including service logic, configuration, and settings UI.

## Common Files

- `electron/services/insightService.ts`
- `electron/services/config.ts`
- `src/services/config.ts`
- `src/pages/SettingsPage.tsx`
- `electron/main.ts`
- `electron/preload.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or create electron/services/insightService.ts for core logic.
- Edit electron/services/config.ts and src/services/config.ts for configuration changes.
- Update src/pages/SettingsPage.tsx to expose new settings or UI.
- Optionally update electron/main.ts or electron/preload.ts for IPC or integration.
- Merge via pull request.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.