---
name: using-orbty-eazy
description: Use when starting any conversation - establishes how to find and use skills, requiring Skill tool invocation before ANY response including clarifying questions
---

<EXTREMELY-IMPORTANT>
If you think there is even a 1% chance a skill might apply to what you are doing, you ABSOLUTELY MUST invoke the skill.

IF A SKILL APPLIES TO YOUR TASK, YOU DO NOT HAVE A CHOICE. YOU MUST USE IT.

This is not negotiable. This is not optional. You cannot rationalize your way out of this.
</EXTREMELY-IMPORTANT>

## How to Access Skills

**In Claude Code:** Use the `Skill` tool. When you invoke a skill, its content is loaded and presented to you—follow it directly. Never use the Read tool on skill files.

**In other environments:** Check your platform's documentation for how skills are loaded.

# Using Skills

## The Rule

**Invoke relevant or requested skills BEFORE any response or action.** Even a 1% chance a skill might apply means that you should invoke the skill to check. If an invoked skill turns out to be wrong for the situation, you don't need to use it.

```dot
digraph skill_flow {
    "User message received" [shape=doublecircle];
    "Might any skill apply?" [shape=diamond];
    "Invoke Skill tool" [shape=box];
    "Announce: 'Using [skill] to [purpose]'" [shape=box];
    "Has checklist?" [shape=diamond];
    "Create TodoWrite todo per item" [shape=box];
    "Follow skill exactly" [shape=box];
    "Respond (including clarifications)" [shape=doublecircle];

    "User message received" -> "Might any skill apply?";
    "Might any skill apply?" -> "Invoke Skill tool" [label="yes, even 1%"];
    "Might any skill apply?" -> "Respond (including clarifications)" [label="definitely not"];
    "Invoke Skill tool" -> "Announce: 'Using [skill] to [purpose]'";
    "Announce: 'Using [skill] to [purpose]'" -> "Has checklist?";
    "Has checklist?" -> "Create TodoWrite todo per item" [label="yes"];
    "Has checklist?" -> "Follow skill exactly" [label="no"];
    "Create TodoWrite todo per item" -> "Follow skill exactly";
}
```

## Red Flags

These thoughts mean STOP—you're rationalizing:

| Thought | Reality |
|---------|---------|
| "This is just a simple question" | Questions are tasks. Check for skills. |
| "I need more context first" | Skill check comes BEFORE clarifying questions. |
| "Let me explore the codebase first" | Skills tell you HOW to explore. Check first. |
| "I can check git/files quickly" | Files lack conversation context. Check for skills. |
| "Let me gather information first" | Skills tell you HOW to gather information. |
| "This doesn't need a formal skill" | If a skill exists, use it. |
| "I remember this skill" | Skills evolve. Read current version. |
| "This doesn't count as a task" | Action = task. Check for skills. |
| "The skill is overkill" | Simple things become complex. Use it. |
| "I'll just do this one thing first" | Check BEFORE doing anything. |
| "This feels productive" | Undisciplined action wastes time. Skills prevent this. |
| "I know what that means" | Knowing the concept ≠ using the skill. Invoke it. |

## Skill Priority

When multiple skills could apply, use this order:

1. **Process skills first** (brainstorming, debugging) - these determine HOW to approach the task
2. **Implementation skills second** (frontend-design, mcp-builder) - these guide execution

"Let's build X" → brainstorming first, then implementation skills.
"Fix this bug" → debugging first, then domain-specific skills.

## Skill Types

**Rigid** (TDD, debugging): Follow exactly. Don't adapt away discipline.

**Flexible** (patterns): Adapt principles to context.

The skill itself tells you which.

## User Instructions

Instructions say WHAT, not HOW. "Add X" or "Fix Y" doesn't mean skip workflows.

## Skill Catalog

### Bootstrap & Documentation

| Skill | Purpose |
|-------|---------|
| `bootstrap` | Start new projects, set up docs structure |
| `inception` | PROJECT_CHARTER, STAKEHOLDER_MAP, TECH_RADAR, KICKOFF_CHECKLIST |
| `vision` | PRODUCT_VISION, MVP_DEFINITION, TARGET_PERSONAS, VALUE_PROPOSITION |
| `architecture` | SYSTEM_OVERVIEW, API_DESIGN, DATA_MODEL, SECURITY, ADRs |
| `frontend-design` | Full Suite design docs (Docs Mode) OR UI task execution (Implementation Mode) |

### Planning

| Skill | Purpose |
|-------|---------|
| `project-planning` | Orchestrates full planning hierarchy |
| `roadmap-planning` | ROADMAP.md with milestones |
| `story-planning` | USER_STORIES.md |
| `epic-planning` | Epic INDEX.md with Kanban folders |
| `task-planning` | TASK.md skeletons with specialist field |

### Development Workflow

| Skill | Purpose |
|-------|---------|
| `brainstorming` | Turn ideas into designs through dialogue |
| `writing-plans` | Enrich TASKs with TDD implementation steps |
| `executing-plans` | Execute plans with specialist delegation |
| `test-driven-development` | TDD workflow |
| `systematic-debugging` | Debug workflow |

### Git & Review

| Skill | Purpose |
|-------|---------|
| `using-git-worktrees` | Create isolated workspaces |
| `finishing-a-development-branch` | Merge, PR, or cleanup |
| `requesting-code-review` | Request review |
| `receiving-code-review` | Handle review feedback |
| `verification-before-completion` | Verify before claiming done |

### Meta

| Skill | Purpose |
|-------|---------|
| `writing-skills` | Create or edit skills |
| `dispatching-parallel-agents` | Run independent tasks in parallel |
| `subagent-driven-development` | Execute plans with subagents |
