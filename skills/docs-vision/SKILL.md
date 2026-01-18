---
name: docs-vision
description: Use when generating product vision documents - creates PRODUCT_VISION, MVP_DEFINITION, TARGET_PERSONAS, VALUE_PROPOSITION
---

# Documentation: Vision Phase

## Overview

Generate vision phase documents that define product direction, target users, and value proposition.

**Announce at start:** "I'm using the docs-vision skill to generate vision documents."

## Documents Generated

| Document | Purpose |
|----------|---------|
| `PRODUCT_VISION.md` | Product direction and goals |
| `MVP_DEFINITION.md` | Minimum viable product scope |
| `TARGET_PERSONAS.md` | User archetypes and needs |
| `VALUE_PROPOSITION.md` | Unique value and differentiation |

## Input Required

From PROJECT_CHARTER and user input:
- Product goals and objectives
- Target market/users
- Key problems being solved
- Competitive landscape
- Core features for MVP

## PRODUCT_VISION.md Template

```markdown
# Product Vision: {Product Name}

## Vision Statement
{One compelling sentence describing the future state}

## Mission
{What we do, for whom, and why it matters}

## Product Goals

### Short-term (3-6 months)
1. {Goal 1}
2. {Goal 2}

### Medium-term (6-12 months)
1. {Goal 1}
2. {Goal 2}

### Long-term (1-2 years)
1. {Goal 1}
2. {Goal 2}

## Problem Statement

### Current State
{What's broken or missing today}

### Desired State
{What the world looks like with our solution}

### Gap
{What needs to happen to get there}

## Target Market

### Primary Market
{Who benefits most}

### Secondary Markets
{Other potential users}

### Market Size
{TAM/SAM/SOM if applicable}

## Competitive Landscape

| Competitor | Strengths | Weaknesses | Our Advantage |
|------------|-----------|------------|---------------|
| {Name} | {What they do well} | {Where they fall short} | {How we're better} |

## Success Metrics

| Metric | Definition | Target |
|--------|------------|--------|
| {Metric} | {How measured} | {Goal} |

---
_Created: {YYYY-MM-DD}_
```

## MVP_DEFINITION.md Template

```markdown
# MVP Definition: {Product Name}

## MVP Goal
{What the MVP must prove/achieve}

## Core Hypothesis
{The assumption we're testing with MVP}

## Must-Have Features (P0)

| Feature | User Story | Acceptance Criteria |
|---------|------------|---------------------|
| {Feature 1} | As a {user}, I want {goal} | {How we know it works} |
| {Feature 2} | As a {user}, I want {goal} | {How we know it works} |

## Should-Have Features (P1)
_Include if time permits_

| Feature | User Story |
|---------|------------|
| {Feature} | As a {user}, I want {goal} |

## Explicitly Excluded from MVP
- {Feature/scope item 1}
- {Feature/scope item 2}

## MVP Success Criteria

| Criteria | Metric | Target |
|----------|--------|--------|
| {What matters} | {How measured} | {Threshold} |

## MVP Timeline

| Phase | Duration | Deliverable |
|-------|----------|-------------|
| Build | {weeks} | Working MVP |
| Test | {weeks} | User feedback |
| Iterate | {weeks} | Refined MVP |

## Technical Constraints

- {Constraint 1}
- {Constraint 2}

## Launch Criteria

- [ ] All P0 features complete
- [ ] Core user flows tested
- [ ] Performance acceptable
- [ ] Security reviewed
- [ ] Documentation ready

---
_Created: {YYYY-MM-DD}_
```

## TARGET_PERSONAS.md Template

```markdown
# Target Personas: {Product Name}

## Primary Persona: {Name}

### Demographics
- **Age**: {range}
- **Role**: {job title/role}
- **Technical Level**: {novice/intermediate/expert}

### Goals
- {What they want to achieve 1}
- {What they want to achieve 2}

### Pain Points
- {Current frustration 1}
- {Current frustration 2}

### Behaviors
- {How they currently solve this problem}
- {Tools they currently use}

### Quote
> "{Something they might say that captures their need}"

---

## Secondary Persona: {Name}

### Demographics
- **Age**: {range}
- **Role**: {job title/role}
- **Technical Level**: {novice/intermediate/expert}

### Goals
- {Goal 1}
- {Goal 2}

### Pain Points
- {Pain 1}
- {Pain 2}

---

## Anti-Persona: {Name}
_Who this product is NOT for_

- {Characteristic 1}
- {Characteristic 2}
- {Why they won't benefit}

---
_Created: {YYYY-MM-DD}_
```

## VALUE_PROPOSITION.md Template

```markdown
# Value Proposition: {Product Name}

## Value Proposition Statement

For {target user}
Who {has this problem/need}
Our product is a {product category}
That {key benefit}
Unlike {competition}
We {key differentiator}

## Key Benefits

### Benefit 1: {Name}
{Description of benefit and how it helps}

### Benefit 2: {Name}
{Description of benefit and how it helps}

### Benefit 3: {Name}
{Description of benefit and how it helps}

## Feature-Benefit Mapping

| Feature | Benefit | Proof Point |
|---------|---------|-------------|
| {Feature} | {What user gains} | {Evidence/metric} |

## Differentiation

### What Makes Us Different

| Aspect | Us | Competitor A | Competitor B |
|--------|----|--------------| -------------|
| {Aspect 1} | {Our approach} | {Their approach} | {Their approach} |

### Unique Advantages
1. {Advantage 1}
2. {Advantage 2}

## Messaging Framework

### Tagline
{Short memorable phrase}

### Elevator Pitch (30 seconds)
{2-3 sentence pitch}

### Key Messages
1. {Message for benefit 1}
2. {Message for benefit 2}
3. {Message for benefit 3}

---
_Created: {YYYY-MM-DD}_
```

## Output Location

Save documents to:
- Standard: `docs/vision/`
- Monorepo: `apps/{app}/docs/vision/`

## Remember

- Reference PROJECT_CHARTER for consistency
- Create realistic, research-based personas
- Be specific about MVP scope
- Clearly articulate differentiation
