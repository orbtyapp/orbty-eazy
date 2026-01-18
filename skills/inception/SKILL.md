---
name: inception
description: Use when generating project inception documents - creates PROJECT_CHARTER, STAKEHOLDER_MAP, TECH_RADAR, KICKOFF_CHECKLIST
---

# Inception

## Overview

Generate inception phase documents that establish project foundation, stakeholders, and technology choices.

**Announce at start:** "I'm using the inception skill to generate inception documents."

## Documents Generated

| Document | Purpose |
|----------|---------|
| `PROJECT_CHARTER.md` | Project scope, objectives, success criteria |
| `STAKEHOLDER_MAP.md` | Key stakeholders, roles, communication |
| `TECH_RADAR.md` | Technology choices with adopt/trial/hold ratings |
| `KICKOFF_CHECKLIST.md` | Pre-launch checklist items |

## Input Required

Before generating, gather:
- Project name and description
- Business objectives (3-5)
- Target users/audience
- Key stakeholders
- Technology preferences

## PROJECT_CHARTER.md Template

```markdown
# Project Charter: {Project Name}

## Executive Summary
{2-3 sentence project overview}

## Vision Statement
{One sentence vision - what success looks like}

## Business Objectives
1. {Objective 1}
2. {Objective 2}
3. {Objective 3}

## Scope

### In Scope
- {Feature/capability 1}
- {Feature/capability 2}

### Out of Scope
- {Explicitly excluded item 1}
- {Explicitly excluded item 2}

## Success Criteria
| Metric | Target | Measurement |
|--------|--------|-------------|
| {KPI 1} | {Target} | {How measured} |

## Timeline
| Milestone | Target Date |
|-----------|-------------|
| MVP | {Date} |
| Beta | {Date} |
| Launch | {Date} |

## Risks
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| {Risk 1} | High/Med/Low | High/Med/Low | {Strategy} |

## Constraints
- {Constraint 1}
- {Constraint 2}

## Assumptions
- {Assumption 1}
- {Assumption 2}

---
_Created: {YYYY-MM-DD}_
```

## STAKEHOLDER_MAP.md Template

```markdown
# Stakeholder Map: {Project Name}

## Key Stakeholders

### Decision Makers
| Name | Role | Responsibilities | Contact |
|------|------|------------------|---------|
| {Name} | {Role} | {What they decide} | {Email} |

### Core Team
| Name | Role | Responsibilities |
|------|------|------------------|
| {Name} | {Role} | {What they do} |

### External Stakeholders
| Organization | Contact | Relationship |
|--------------|---------|--------------|
| {Org} | {Name} | {How they're involved} |

## Communication Plan

| Stakeholder Group | Frequency | Channel | Content |
|-------------------|-----------|---------|---------|
| Decision Makers | Weekly | Meeting | Progress, blockers, decisions |
| Core Team | Daily | Slack | Updates, collaboration |
| External | Monthly | Email | Status reports |

## RACI Matrix

| Activity | {Role 1} | {Role 2} | {Role 3} |
|----------|----------|----------|----------|
| Architecture decisions | A | R | C |
| Feature prioritization | A | C | I |
| Code review | I | R | A |

_R=Responsible, A=Accountable, C=Consulted, I=Informed_

---
_Created: {YYYY-MM-DD}_
```

## TECH_RADAR.md Template

```markdown
# Technology Radar: {Project Name}

## Overview
Technology choices and their adoption status for this project.

## Languages & Frameworks

| Technology | Status | Rationale |
|------------|--------|-----------|
| {Tech 1} | ADOPT | {Why chosen} |
| {Tech 2} | TRIAL | {Why trying} |
| {Tech 3} | HOLD | {Why avoiding} |

## Infrastructure

| Technology | Status | Rationale |
|------------|--------|-----------|
| {Tech} | ADOPT | {Why} |

## Tools

| Tool | Status | Purpose |
|------|--------|---------|
| {Tool} | ADOPT | {What for} |

## Data & Storage

| Technology | Status | Rationale |
|------------|--------|-----------|
| {Tech} | ADOPT | {Why} |

## Status Definitions

- **ADOPT**: Default choice, proven for our use case
- **TRIAL**: Evaluating, limited production use
- **ASSESS**: Investigating, not yet in use
- **HOLD**: Not recommended, migrate away if using

---
_Created: {YYYY-MM-DD}_
```

## KICKOFF_CHECKLIST.md Template

```markdown
# Kickoff Checklist: {Project Name}

## Repository Setup
- [ ] Repository created
- [ ] Branch protection configured
- [ ] CI/CD pipeline setup
- [ ] README with setup instructions

## Environment Setup
- [ ] Development environment documented
- [ ] Required accounts/access provisioned
- [ ] Environment variables documented
- [ ] Local development working

## Team Setup
- [ ] Team members identified
- [ ] Access granted to all systems
- [ ] Communication channels created
- [ ] Meeting cadence established

## Documentation
- [ ] Project Charter approved
- [ ] Stakeholder map complete
- [ ] Tech radar reviewed
- [ ] Architecture documented

## Planning
- [ ] Roadmap defined
- [ ] First epic planned
- [ ] Initial backlog created
- [ ] Sprint/iteration schedule set

---
_Created: {YYYY-MM-DD}_
```

## Output Location

Save documents to:
- Standard: `docs/inception/`
- Monorepo: `apps/{app}/docs/inception/`

## Remember

- Gather input before generating
- Use project context from due diligence
- Fill placeholders with real values
- Don't leave {placeholder} text in final docs
