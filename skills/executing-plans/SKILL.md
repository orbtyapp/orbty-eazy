---
name: executing-plans
description: Use when you have a written implementation plan to execute in a separate session with review checkpoints
---

# Executing Plans

## Overview

Load plan, review critically, execute tasks in batches, report for review between batches.

**Core principle:** Batch execution with checkpoints for architect review.

**Announce at start:** "I'm using the executing-plans skill to implement this plan."

## The Process

### Step 1: Load and Review Plan
1. Read plan file
2. Review critically - identify any questions or concerns about the plan
3. If concerns: Raise them with your human partner before starting
4. If no concerns: Create TodoWrite and proceed

### Step 2: Check Specialist

Before executing each task, check the `Specialist` field in TASK.md metadata:

```
Read TASK.md → Check Specialist field
  │
  ├── Specialist: none (or not specified)
  │     → Execute directly (Step 3)
  │
  └── Specialist: frontend-design
        → Delegate to frontend-design skill
        → frontend-design reads design docs as constraints
        → frontend-design executes the task
        → Continue to next task
```

**REQUIRED:** When delegating to a specialist:
1. Announce: "This task has Specialist: frontend-design. Delegating to frontend-design skill."
2. **INVOKE SUB-SKILL:** Use `orbty-eazy:frontend-design`
3. Let the specialist complete the task
4. Mark task as completed after specialist finishes

### Step 3: Execute Batch
**Default: First 3 tasks (non-specialist tasks)**

For each task without specialist delegation:
1. Mark as in_progress
2. Follow each step exactly (plan has bite-sized steps)
3. Run verifications as specified
4. Mark as completed

### Step 4: Report
When batch complete:
- Show what was implemented
- Show verification output
- Say: "Ready for feedback."

### Step 5: Continue
Based on feedback:
- Apply changes if needed
- Execute next batch
- Repeat until complete

### Step 6: Complete Development

After all tasks complete and verified:
- Announce: "I'm using the finishing-a-development-branch skill to complete this work."
- **REQUIRED SUB-SKILL:** Use orbty-eazy:finishing-a-development-branch
- Follow that skill to verify tests, present options, execute choice

## When to Stop and Ask for Help

**STOP executing immediately when:**
- Hit a blocker mid-batch (missing dependency, test fails, instruction unclear)
- Plan has critical gaps preventing starting
- You don't understand an instruction
- Verification fails repeatedly

**Ask for clarification rather than guessing.**

## When to Revisit Earlier Steps

**Return to Review (Step 1) when:**
- Partner updates the plan based on your feedback
- Fundamental approach needs rethinking

**Don't force through blockers** - stop and ask.

## Remember
- Review plan critically first
- Follow plan steps exactly
- Don't skip verifications
- Reference skills when plan says to
- Between batches: just report and wait
- Stop when blocked, don't guess
