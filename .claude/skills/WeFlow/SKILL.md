```markdown
# WeFlow Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and common workflows used in the WeFlow project—a TypeScript codebase built with Vite and Electron. You'll learn how to contribute features, maintain dependencies, update CI/CD workflows, and follow the project's code style and testing practices.

## Coding Conventions

### File Naming

- Use **camelCase** for file names.
  - Example: `insightService.ts`, `settingsPage.tsx`

### Import Style

- Use **relative imports** for modules.
  ```typescript
  import { getConfig } from '../services/config';
  import { Insight } from './insightService';
  ```

### Export Style

- Use **named exports**.
  ```typescript
  // Good
  export function getConfig() { ... }
  export const INSIGHT_TYPE = 'ai';

  // Avoid default exports
  ```

### Commit Messages

- Prefix with `fix`, `feat`, or `chore` when possible.
- Freeform after prefix.
- Keep messages concise (~45 characters).
  - Example: `feat: add AI insights config option`

## Workflows

### AI Insights Feature Development
**Trigger:** When you want to add or enhance AI insights functionality  
**Command:** `/ai-insight-feature`

1. Edit or create `electron/services/insightService.ts` for core AI insights logic.
2. Update configuration in both `electron/services/config.ts` and `src/services/config.ts`.
3. Expose new settings or UI in `src/pages/SettingsPage.tsx`.
4. Optionally, update `electron/main.ts` or `electron/preload.ts` for IPC or integration.
5. Open a pull request and merge.

**Example:**
```typescript
// electron/services/insightService.ts
export function generateInsight(data: InputData): Insight {
  // AI logic here
}
```
```typescript
// src/pages/SettingsPage.tsx
import { INSIGHT_TYPE } from '../../electron/services/insightService';
// Add new setting to UI
```

---

### Package.json Maintenance
**Trigger:** When you need to fix build issues, update repository info, or change dependencies  
**Command:** `/update-package-json`

1. Edit `package.json` to update fields such as `repository`, `dependencies`, or build config.
2. Optionally, open a pull request and merge.

**Example:**
```json
// package.json
{
  "dependencies": {
    "some-new-package": "^1.2.3"
  }
}
```

---

### GitHub Actions Workflow Update
**Trigger:** When you need to fix or enhance CI/CD pipelines  
**Command:** `/update-ci-workflow`

1. Edit one or more files under `.github/workflows/` (e.g., `release.yml`, `dev-daily-fixed.yml`, `preview-nightly-main.yml`).
2. Optionally, open a pull request and merge.

**Example:**
```yaml
# .github/workflows/release.yml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      # ...more steps
```

---

### Feature Development with Merge
**Trigger:** When you develop a feature or fix a bug that spans multiple files/services  
**Command:** `/feature-pr`

1. Edit or create multiple related source files (e.g., services, pages, configs).
2. Push commits.
3. Open a pull request and merge.

**Example:**
```typescript
// src/services/newFeature.ts
export function doSomething() { ... }

// src/pages/NewFeaturePage.tsx
import { doSomething } from '../services/newFeature';
```

## Testing Patterns

- Test files follow the `*.test.*` pattern (e.g., `insightService.test.ts`).
- The specific testing framework is not specified, but typical usage in TypeScript projects includes Jest or Vitest.
- Place tests alongside the files they test or in a dedicated `__tests__` directory.

**Example:**
```typescript
// insightService.test.ts
import { generateInsight } from './insightService';

test('should generate correct insight', () => {
  expect(generateInsight(sampleData)).toEqual(expectedInsight);
});
```

## Commands

| Command                | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| /ai-insight-feature    | Start or update AI insights feature development              |
| /update-package-json   | Update dependencies or project metadata in package.json      |
| /update-ci-workflow    | Update or fix GitHub Actions CI/CD workflows                |
| /feature-pr            | Begin a multi-file feature or bugfix implementation & merge  |
```
