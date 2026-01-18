---
name: task-planning
description: Use when creating task documents - generates TASK.md skeletons with metadata and acceptance criteria
---

# Task Planning

## Overview

Create task skeletons with rich metadata, acceptance criteria, and placeholders for TDD implementation steps.

**Announce at start:** "I'm using the task-planning skill to create task documents."

## Output

`docs/planning/epics/E{NN}-{name}/00-todo/TASK_E{NN}-TK{NN}_{name}.md`

## Input Required

- Epic INDEX.md (context)
- USER_STORIES.md (acceptance criteria source)
- Technical context (from architecture docs)

## TASK.md Template

```markdown
# TASK: E{NN}-TK{NN} - {Title}

> **Project:** {Project Name}
> **Epic:** [E{NN} - {Epic Title}](../INDEX.md)
> **Story:** [US{NNN}](../../USER_STORIES.md#us{nnn})

---

## Metadata

| Field        | Value                |
|--------------|----------------------|
| **Priority** | P0 / P1 / P2 / P3    |
| **Status**   | ⏳ Todo              |
| **Estimate** | {hours}h             |
| **Assignee** | TBD                  |
| **Specialist** | none / frontend-design |
| **Created**  | {YYYY-MM-DD}         |

---

## Objective

{What this task achieves - 1-2 sentences, derived from user story}

---

## Acceptance Criteria

- [ ] {Criterion 1 - specific, testable}
- [ ] {Criterion 2 - specific, testable}
- [ ] {Criterion 3 - specific, testable}

---

## Technical Context

### Approach
{High-level technical approach - 2-3 sentences}

### Dependencies

| Dependency | Type | Status |
|------------|------|--------|
| {Task/Service} | Internal/External | ✅ Ready / ⏳ Pending |

### Risks

| Risk | Mitigation |
|------|------------|
| {Potential issue} | {How to handle} |

---

## Files

| Action | Path | Notes |
|--------|------|-------|
| Create | `src/path/to/new-file.ts` | {purpose} |
| Modify | `src/path/to/existing.ts` | {what changes} |
| Test   | `tests/path/to/test.spec.ts` | {test focus} |

---

## Implementation Steps

<!--
IMPORTANT: This section is populated by orbty-eazy:writing-plans skill.
Do NOT fill this in during task planning.
When ready to implement, use writing-plans to enrich with TDD steps.
-->

_To be added when ready for implementation. Use `orbty-eazy:writing-plans` to enrich this task._

---

## Verification

| Check | Command | Expected |
|-------|---------|----------|
| Tests pass | `npm test` | ✅ All green |
| Types check | `npm run typecheck` | ✅ No errors |
| Lint clean | `npm run lint` | ✅ No warnings |
| Build works | `npm run build` | ✅ Success |

---

## Definition of Done

- [ ] All acceptance criteria met
- [ ] Tests written and passing
- [ ] No lint/type errors
- [ ] Code reviewed
- [ ] Documentation updated (if applicable)
- [ ] Committed with conventional message

---

## Notes

<!-- Discoveries, learnings, or blockers during implementation -->

---

_Created: {YYYY-MM-DD}_ | _Last Updated: {YYYY-MM-DD}_
```

## Task Naming Convention

### File Name
`TASK_E{NN}-TK{NN}_{kebab-case-title}.md`

Examples:
- `TASK_E01-TK01_project-setup.md`
- `TASK_E01-TK02_database-schema.md`
- `TASK_E02-TK01_user-authentication.md`

### Task ID
`E{NN}-TK{NN}`
- Epic number (2 digits)
- Task number within epic (2 digits)

## Priority Guidelines

| Priority | Meaning | Examples |
|----------|---------|----------|
| **P0** | Critical path, blocks others | Project setup, core schema |
| **P1** | Important for milestone | Key features, auth |
| **P2** | Valuable but not urgent | Nice-to-have features |
| **P3** | Future consideration | Enhancements, optimizations |

## Estimation Guidelines

| Estimate | Meaning |
|----------|---------|
| 1-2h | Small change, single file |
| 2-4h | Feature implementation |
| 4-8h | Complex feature, multiple files |
| 8h+ | Consider breaking into smaller tasks |

## Creating Multiple Tasks

When creating tasks for an epic, batch create:

1. List all tasks needed for the epic
2. Create skeleton for each
3. Ensure sequential numbering
4. Update Epic INDEX.md with task list

## Task Lifecycle

```
00-todo/TASK_*.md  →  01-doing/TASK_*.md  →  02-done/TASK_*.md
     │                      │                      │
     └─ writing-plans       └─ executing-plans     └─ complete
        enriches task          implements code
```

## Integration with writing-plans

When ready to implement a task:

1. Pick task from `00-todo/`
2. Invoke `orbty-eazy:writing-plans`
3. writing-plans reads task metadata and acceptance criteria
4. writing-plans adds Implementation Steps with:
   - Exact file paths
   - TDD steps (test → implement → verify → commit)
   - Complete code
   - Verification commands
5. Task is ready for `orbty-eazy:executing-plans`

## Specialist Field

The `Specialist` field enables skill-chain delegation during execution.

### Valid Values

| Value | Description |
|-------|-------------|
| `none` | Default. Task executed by executing-plans directly |
| `frontend-design` | UI/UX tasks. Delegates to frontend-design skill |

### When to Use `frontend-design`

Set `Specialist: frontend-design` for tasks involving:
- Component creation (buttons, forms, modals, cards)
- Page layouts and templates
- Styling and theming
- Animations and micro-interactions
- Responsive design
- UI refactoring

### Execution Flow

```
executing-plans reads TASK.md
  ├── Specialist: none → Execute directly
  └── Specialist: frontend-design → Delegate to frontend-design skill
        └── frontend-design loads design docs as constraints
```

## Remember

- Task skeleton = WHAT (requirements)
- Implementation steps = HOW (added by writing-plans)
- Keep tasks focused (2-8 hours)
- Every task traces to a user story
- Leave Implementation Steps empty during planning
- Set Specialist field for UI tasks
