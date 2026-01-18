# Frontend Design Integration

## Summary

Integrated the `frontend-design` skill into orbty-eazy with dual-mode operation:
1. **Docs Mode**: Generates Full Suite design documentation during bootstrap
2. **Implementation Mode**: Executes UI-related tasks via specialist delegation

## Architecture

### Bootstrap Pipeline

```
/bootstrap
  → inception     (PROJECT_CHARTER, STAKEHOLDER_MAP, TECH_RADAR, KICKOFF_CHECKLIST)
  → vision        (PRODUCT_VISION, MVP_DEFINITION, TARGET_PERSONAS, VALUE_PROPOSITION)
  → architecture  (SYSTEM_OVERVIEW, API_DESIGN, DATA_MODEL, SECURITY, ADRs)
  → frontend-design (Full Suite: 7 docs + references/)
  → project-planning (ROADMAP, USER_STORIES, EPICs, TASKs)
```

### Implementation Pipeline (Specialist Delegation)

```
executing-plans
  → Read TASK.md
  → Check specialist field
  → If specialist: frontend-design → Delegate to frontend-design skill
  → frontend-design reads design docs as constraints
  → Execute with domain expertise
```

## Changes Made

### Skills Renamed (removed `docs-` prefix)

| Before | After |
|--------|-------|
| docs-bootstrap | bootstrap |
| docs-inception | inception |
| docs-vision | vision |
| docs-architecture | architecture |

### Skills Deleted

- `docs-design` - replaced by `frontend-design`

### Skills Created

- `frontend-design` - dual-mode skill for design documentation and UI task execution

### Skills Modified

| Skill | Changes |
|-------|---------|
| `bootstrap` | Updated to invoke renamed skills; invokes frontend-design for design phase |
| `task-planning` | Added `Specialist` field to TASK.md template |
| `executing-plans` | Added Step 2 for specialist detection and delegation |
| `using-orbty-eazy` | Added comprehensive skill catalog |

## Frontend-Design Skill

### Docs Mode

**Trigger:** `bootstrap` invokes after `architecture`

**Input:**
- Reads inception/vision docs automatically
- Asks 3 questions: references, brand assets, target platforms
- WebSearch for design trends
- Analyzes screenshots from `docs/design/references/`

**Output: Full Suite**
```
docs/design/
├── STYLE_GUIDE.md
├── UI_DESIGN_SYSTEM.md
├── UX_PRINCIPLES.md
├── REFERENCES.md
├── COMPONENT_SPEC.md
├── ANIMATION_GUIDE.md
├── RESPONSIVE_STRATEGY.md
└── references/
    └── .gitkeep
```

### Implementation Mode

**Trigger:** `executing-plans` detects `specialist: frontend-design` in TASK.md

**Process:**
1. Load design docs as constraints
2. Read TASK.md requirements
3. Design thinking (purpose, tone, constraints)
4. Implement production-grade UI
5. Verify against design tokens

## Specialist Pattern

The `specialist:` field in TASK.md enables extensible skill delegation:

```markdown
| Field | Value |
|-------|-------|
| Specialist | none / frontend-design |
```

Future specialists can be added following the same pattern:
- `api-design` for API endpoint tasks
- `data-modeling` for database tasks
- etc.

## Commits

- `033221d` feat: integrate frontend-design skill with specialist delegation

---
_Date: 2026-01-18_
