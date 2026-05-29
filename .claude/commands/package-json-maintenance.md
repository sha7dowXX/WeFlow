---
name: package-json-maintenance
description: Workflow command scaffold for package-json-maintenance in WeFlow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /package-json-maintenance

Use this workflow when working on **package-json-maintenance** in `WeFlow`.

## Goal

Updates project metadata, dependencies, or build configuration in package.json, often for release, build, or dependency fixes.

## Common Files

- `package.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit package.json to update fields (repository, dependencies, build config, etc).
- Optionally merge via pull request.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.