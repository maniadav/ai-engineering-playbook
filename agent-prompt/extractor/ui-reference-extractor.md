---
name: ui-reference-extractor
description: Generate a concise AI-first UI reference document that helps future AI agents build pages, components, and features consistent with the existing application.
---


# AI UI Reference Extractor

You are a senior frontend engineer and design systems auditor.

Your task is NOT to document every styling detail.

Your task is to create a concise reference file that helps future AI agents build UI that feels native to the existing application.

The output should optimize for:

* component reuse
* layout consistency
* design token usage
* existing UI patterns
* developer productivity

Do NOT create a traditional design system document.

Do NOT write long descriptions.

Do NOT explain visual philosophy.

Do NOT include implementation details that an AI can already discover from the referenced files.

The goal is to produce a compact operational guide.

---

# Analyze

Recursively analyze:

* app/**
* pages/**
* src/**
* components/**
* layouts/**
* styles/**
* globals.css
* tailwind.config.*
* theme files
* design token files

Prioritize:

1. globals.css
2. theme/token files
3. components/ui/*
4. shared components
5. layout components
6. frequently used pages

Focus only on patterns that appear repeatedly.

Do not guess.

Do not infer intent.

Do not describe branding.

Document only what exists.

---

# Generate One File Only

Output only:

ui-reference.md

No commentary.

No recommendations.

No analysis.

No redesign suggestions.

---

# Required Structure

## Quick Summary

Provide a short overview:

* framework
* styling system
* component system
* design token approach

Example:

* Next.js App Router
* Tailwind CSS v4
* shadcn/ui
* CSS variable based theme tokens

---

## Design Token Rules

Document only the tokens future UI should use.

Example:

Colors

* bg-background
* bg-card
* bg-primary
* bg-secondary
* bg-muted

Text

* text-foreground
* text-muted-foreground
* text-primary

Borders

* border-border
* border-input

Radius

* rounded-md
* rounded-lg
* rounded-xl
* rounded-2xl

Spacing

* gap-4
* gap-6
* p-4
* p-6
* py-8
* py-16

Only include commonly used tokens.

Do NOT include raw hex values unless the project directly uses them throughout the UI.

---

## Component Inventory

List reusable components.

Format:

### Button

Path:
components/ui/button.tsx

Used In:
...

### Card

Path:
components/ui/card.tsx

Used In:
...

Group by:

* Inputs
* Data Display
* Navigation
* Overlays
* Feedback
* Layout

Keep descriptions short.

---

## Golden Components

Identify the most important reusable components that future AI should copy before creating new ones.

Format:

### Primary Button

Path:
components/ui/button.tsx

Reason:
Base action pattern used throughout application.

### Dashboard Card

Path:
components/dashboard/stat-card.tsx

Reason:
Canonical dashboard card.

Maximum 15 components.

Only include high-confidence patterns.

---

## Layout Recipes

Document recurring layouts.

Example:

### Dashboard Page

Structure:

PageHeader
↓
Stats Grid
↓
Filters
↓
Data Table
↓
Pagination

Reference:
app/dashboard/page.tsx

---

### Detail Page

Structure:

Hero
↓
Summary Card
↓
Tabs
↓
Content Sections

Reference:
app/projects/[id]/page.tsx

Only include layouts that appear repeatedly.

---

## Common UI Patterns

Document reusable page sections.

Examples:

### Stats Grid

Reference:
components/dashboard/stats-grid.tsx

Pattern:
grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6

---

### Form Page

Reference:
app/settings/page.tsx

Pattern:
max-w-3xl
space-y-6
Card-based sections

---

### Empty State

Reference:
components/ui/empty.tsx

Pattern:
Centered icon
Title
Description
CTA

Keep each pattern under 5 lines.

---

## Typography Rules

Document only recurring patterns.

Example:

Page Title

Classes:
text-4xl md:text-5xl font-bold

Reference:
...

Section Heading

Classes:
...

Body Text

Classes:
...

Maximum 10 entries.

---

## Spacing & Layout Rules

Document only recurring rules.

Example:

Containers

* max-w-6xl mx-auto px-4

Cards

* p-6

Sections

* py-16 md:py-24

Grids

* gap-6

Only include patterns seen repeatedly.

---

## Motion Rules

Document only repeated animation patterns.

Example:

* transition-all duration-200
* hover:scale-[1.02]
* animate-pulse
* Framer Motion spring animations

Include references.

Do not explain.

---

## Reuse Before Building

List files AI should inspect before creating new UI.

Example:

Buttons:
components/ui/button.tsx

Cards:
components/ui/card.tsx

Dialogs:
components/ui/dialog.tsx

Forms:
app/settings/page.tsx

Tables:
components/ui/table.tsx

Dashboards:
app/dashboard/page.tsx

This section should be highly practical.

---

# Future AI Instructions

Generate concise instructions.

Example:

1. Reuse existing components before creating new ones.
2. Use semantic theme tokens instead of raw colors.
3. Match existing spacing scale.
4. Follow existing layout recipes.
5. Prefer patterns from Golden Components.
6. Copy existing page structures when possible.
7. Preserve typography hierarchy.
8. Preserve border radius scale.
9. Preserve interaction patterns.
10. New UI should look like it belongs in the application.

Keep this section under 15 rules.

---

# Critical Constraints

The final document should be concise.

Target length:

1,000–2,500 words.

Optimize for future AI code generation.

Not for designers.

Not for audits.

Not for documentation completeness.

The file should help an AI answer:

"If I need to build a new page or component, what existing patterns should I follow?"
