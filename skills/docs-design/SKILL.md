---
name: docs-design
description: Use when generating design system documents - creates STYLE_GUIDE and UI_DESIGN_SYSTEM
---

# Documentation: Design Phase

## Overview

Generate design system documents that define visual language, component patterns, and UI guidelines.

**Announce at start:** "I'm using the docs-design skill to generate design documents."

## Documents Generated

| Document | Purpose |
|----------|---------|
| `STYLE_GUIDE.md` | Colors, typography, spacing, visual rules |
| `UI_DESIGN_SYSTEM.md` | Component patterns, layouts, interactions |

## Input Required

From previous phases and project context:
- Brand colors (if any)
- Typography preferences
- Existing design system (e.g., shadcn/ui, Material)
- Target platforms (web, mobile, desktop)

## STYLE_GUIDE.md Template

```markdown
# Style Guide: {Project Name}

## Brand Overview
{Brief description of visual identity}

## Colors

### Primary Palette
| Name | Hex | Usage |
|------|-----|-------|
| Primary | #3B82F6 | Main actions, links |
| Primary Dark | #1D4ED8 | Hover states |
| Primary Light | #93C5FD | Backgrounds |

### Secondary Palette
| Name | Hex | Usage |
|------|-----|-------|
| Secondary | #6B7280 | Secondary text |

### Semantic Colors
| Name | Hex | Usage |
|------|-----|-------|
| Success | #22C55E | Success states |
| Warning | #F59E0B | Warning states |
| Error | #EF4444 | Error states |
| Info | #3B82F6 | Information |

### Neutral Palette
| Name | Hex | Usage |
|------|-----|-------|
| Background | #FFFFFF | Page background |
| Surface | #F9FAFB | Card backgrounds |
| Border | #E5E7EB | Borders, dividers |
| Text | #111827 | Primary text |
| Text Muted | #6B7280 | Secondary text |

### Dark Mode
| Light | Dark | Usage |
|-------|------|-------|
| #FFFFFF | #111827 | Background |
| #111827 | #F9FAFB | Text |

## Typography

### Font Family
- **Primary**: Inter, system-ui, sans-serif
- **Monospace**: JetBrains Mono, monospace

### Type Scale
| Name | Size | Weight | Line Height | Usage |
|------|------|--------|-------------|-------|
| h1 | 2.25rem (36px) | 700 | 1.2 | Page titles |
| h2 | 1.875rem (30px) | 600 | 1.3 | Section headers |
| h3 | 1.5rem (24px) | 600 | 1.4 | Subsections |
| h4 | 1.25rem (20px) | 500 | 1.4 | Card headers |
| body | 1rem (16px) | 400 | 1.5 | Body text |
| small | 0.875rem (14px) | 400 | 1.5 | Captions |
| xs | 0.75rem (12px) | 400 | 1.5 | Labels |

## Spacing

### Scale
| Token | Value | Usage |
|-------|-------|-------|
| space-1 | 0.25rem (4px) | Tight spacing |
| space-2 | 0.5rem (8px) | Related elements |
| space-3 | 0.75rem (12px) | Default gap |
| space-4 | 1rem (16px) | Section spacing |
| space-6 | 1.5rem (24px) | Large gaps |
| space-8 | 2rem (32px) | Section dividers |

### Layout
- Container max-width: 1280px
- Content max-width: 768px
- Page padding: 1rem (mobile), 2rem (desktop)

## Border Radius

| Token | Value | Usage |
|-------|-------|-------|
| rounded-sm | 0.25rem | Subtle rounding |
| rounded | 0.5rem | Default |
| rounded-lg | 0.75rem | Cards |
| rounded-xl | 1rem | Large cards |
| rounded-full | 9999px | Avatars, pills |

## Shadows

| Token | Value | Usage |
|-------|-------|-------|
| shadow-sm | 0 1px 2px rgba(0,0,0,0.05) | Subtle elevation |
| shadow | 0 1px 3px rgba(0,0,0,0.1) | Default cards |
| shadow-lg | 0 10px 15px rgba(0,0,0,0.1) | Dropdowns, modals |

## Icons
- Icon library: {Lucide/Heroicons/etc.}
- Default size: 20px
- Stroke width: 1.5

---
_Created: {YYYY-MM-DD}_
```

## UI_DESIGN_SYSTEM.md Template

```markdown
# UI Design System: {Project Name}

## Overview
{Design system approach - custom, shadcn/ui, etc.}

## Component Library
Base: {shadcn/ui, Radix, custom, etc.}

## Layout Patterns

### Page Layout
```
┌─────────────────────────────────────┐
│            Header                   │
├─────────┬───────────────────────────┤
│         │                           │
│ Sidebar │        Content            │
│         │                           │
└─────────┴───────────────────────────┘
```

### Responsive Breakpoints
| Name | Min Width | Usage |
|------|-----------|-------|
| sm | 640px | Mobile landscape |
| md | 768px | Tablets |
| lg | 1024px | Desktop |
| xl | 1280px | Large desktop |

## Component Patterns

### Buttons

| Variant | Usage |
|---------|-------|
| Primary | Main actions |
| Secondary | Secondary actions |
| Outline | Tertiary actions |
| Ghost | Subtle actions |
| Destructive | Dangerous actions |

**Sizes**: sm, default, lg

### Forms

**Input States**:
- Default
- Focus (ring + border color)
- Error (red border + message)
- Disabled (reduced opacity)

**Validation**:
- Inline error messages
- Real-time validation on blur
- Submit validation

### Cards

| Type | Usage |
|------|-------|
| Default | Content containers |
| Interactive | Clickable items |
| Elevated | Featured content |

### Navigation

**Top Navigation**:
- Logo left
- Navigation center
- Actions right

**Sidebar**:
- Collapsible on mobile
- Icon-only collapsed state
- Grouped navigation items

### Modals & Dialogs

- Centered overlay
- Focus trap
- Escape to close
- Backdrop click to close (optional)

### Tables

- Sortable headers
- Pagination
- Row selection (optional)
- Empty state
- Loading state

### Loading States

| Type | Usage |
|------|-------|
| Spinner | Button loading |
| Skeleton | Content loading |
| Progress | Long operations |

### Empty States

- Illustration (optional)
- Title
- Description
- Action button

### Error States

- Error message
- Retry action
- Help link (optional)

## Animation

### Durations
| Token | Value | Usage |
|-------|-------|-------|
| fast | 100ms | Micro-interactions |
| normal | 200ms | Default transitions |
| slow | 300ms | Complex animations |

### Easing
- Default: ease-out
- Enter: ease-out
- Exit: ease-in

## Accessibility

### Requirements
- WCAG 2.1 AA compliance
- Keyboard navigation
- Screen reader support
- Color contrast 4.5:1 minimum
- Focus indicators visible

### Focus Management
- Visible focus ring
- Logical tab order
- Focus trap in modals

---
_Created: {YYYY-MM-DD}_
```

## Output Location

Save documents to:
- Standard: `docs/design/`
- Monorepo: `apps/{app}/docs/design/`

## Remember

- Reference actual design system in use
- Include dark mode considerations
- Ensure accessibility guidelines
- Keep in sync with implemented components
