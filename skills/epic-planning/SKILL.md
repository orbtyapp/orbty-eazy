---
name: epic-planning
description: Use when creating epic structure - generates Epic INDEX.md with Kanban folders
---

# Epic Planning

## Overview

Create epic structure with INDEX.md overview and Kanban folder organization.

**Announce at start:** "I'm using the epic-planning skill to create the epic structure."

## Output

```
docs/planning/epics/E{NN}-{name}/
├── INDEX.md
├── 00-todo/
├── 01-doing/
└── 02-done/
```

## Input Required

- USER_STORIES.md (stories for this epic)
- ROADMAP.md (timeline)
- Feature grouping (what belongs in this epic)

## Epic INDEX.md Template

```markdown
# Epic: E{NN} - {Epic Title}

> **Milestone**: M{N} - {Milestone Name}
> **Status**: ⏳ In Progress | ✅ Complete
> **Progress**: {X}/{Y} tasks complete ({Z}%)

---

## Overview

### Objective
{What this epic achieves - 2-3 sentences}

### Business Value
- {Value 1}
- {Value 2}

### Success Criteria
- [ ] {Measurable criterion 1}
- [ ] {Measurable criterion 2}
- [ ] {Measurable criterion 3}

---

## User Stories

| ID | Story | Priority |
|----|-------|----------|
| US{NNN} | {Story title} | P0 |
| US{NNN} | {Story title} | P0 |
| US{NNN} | {Story title} | P1 |

---

## Tasks

### Kanban Board

| Status | Count |
|--------|-------|
| 📋 Todo | {N} |
| 🔄 Doing | {N} |
| ✅ Done | {N} |

### Task List

| ID | Title | Priority | Status | Assignee |
|----|-------|----------|--------|----------|
| E{NN}-TK01 | {Task title} | P0 | ⏳ Todo | - |
| E{NN}-TK02 | {Task title} | P0 | ⏳ Todo | - |
| E{NN}-TK03 | {Task title} | P1 | ⏳ Todo | - |

### Task Details

#### E{NN}-TK01: {Task Title}
- **Story**: US{NNN}
- **Priority**: P0
- **Estimate**: {hours}h
- **File**: [TASK_E{NN}-TK01_{name}.md](./00-todo/TASK_E{NN}-TK01_{name}.md)

#### E{NN}-TK02: {Task Title}
- **Story**: US{NNN}
- **Priority**: P0
- **Estimate**: {hours}h
- **File**: [TASK_E{NN}-TK02_{name}.md](./00-todo/TASK_E{NN}-TK02_{name}.md)

---

## Dependencies

### Depends On
| Epic/Task | Status | Notes |
|-----------|--------|-------|
| {Dependency} | ✅ | {Notes} |

### Blocks
| Epic/Task | Notes |
|-----------|-------|
| E{NN} | {Why blocked} |

---

## Timeline

| Phase | Start | End | Status |
|-------|-------|-----|--------|
| Planning | {Date} | {Date} | ✅ |
| Development | {Date} | {Date} | 🔄 |
| Testing | {Date} | {Date} | ⏳ |
| Review | {Date} | {Date} | ⏳ |

---

## Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| {Risk} | Med | High | {Strategy} |

---

## Definition of Done

Epic is complete when:
- [ ] All P0 tasks complete
- [ ] All P1 tasks complete or deferred with justification
- [ ] All success criteria met
- [ ] Code reviewed and merged
- [ ] Tests passing
- [ ] Documentation updated

---

## Notes

_Development notes, decisions, and discoveries_

---

_Created: {YYYY-MM-DD}_
_Last Updated: {YYYY-MM-DD}_
```

## Creating Epic Structure

```bash
# Create epic folder structure
EPIC="E01-foundation"
mkdir -p "docs/planning/epics/$EPIC"/{00-todo,01-doing,02-done}
```

## Naming Conventions

### Epic ID
- Format: `E{NN}` (e.g., E01, E02)
- Sequential numbering
- No gaps in sequence

### Epic Folder
- Format: `E{NN}-{kebab-case-name}`
- Examples: `E01-foundation`, `E02-authentication`, `E03-core-features`

### Task ID
- Format: `E{NN}-TK{NN}` (e.g., E01-TK01)
- Sequential within epic
- Reference in commits: `feat(auth): implement login (E01-TK03)`

## Task Movement

When task status changes:

```bash
# Start working on task
mv 00-todo/TASK_E01-TK01_setup.md 01-doing/

# Complete task
mv 01-doing/TASK_E01-TK01_setup.md 02-done/
```

Update INDEX.md:
- Update task status in table
- Update progress count
- Update Kanban counts

## Remember

- One epic = one logical grouping of features
- Keep epics focused (5-10 tasks)
- First epic is usually "Foundation"
- Map every task to a user story
- Update progress as tasks move
