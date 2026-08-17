# Development Rules

Version: 1.0.0

Status: Stable

---

# Purpose

This document defines implementation rules for Visual Blueprint.

These rules apply to all code written for the project.

---

# Core Philosophy

Prioritize:

- Simplicity
- Maintainability
- Consistency

Over:

- Clever code
- Complex abstractions
- Premature optimization

---

# Technology Restrictions

Version 1.0 must use:

- HTML
- CSS
- JavaScript

---

Do Not Use:

- React
- Vue
- Angular
- Svelte
- Next.js
- Nuxt
- Backend Frameworks

Unless explicitly approved in future versions.

---

# Offline First

All core functionality must work offline.

Internet access must never be required for:

- Project Editing
- Node Editing
- Asset Management
- Import
- Export

---

# Code Organization

Business logic must be separated from UI.

Bad:

UI directly modifies storage.

Good:

UI
↓
State
↓
Storage

---

# File Size

Recommended:

< 1000 lines per file

Maximum:

2000 lines per file

If exceeded:

Refactor.

---

# Naming Conventions

Use:

camelCase

for variables and functions.

---

Use:

PascalCase

for classes.

---

Use:

kebab-case

for file names.

---

# Comments

Write comments only when they explain intent.

Do not comment obvious code.

Bad:

// increment counter
counter++;

Good:

// Prevent duplicate node IDs during import
```

---

# State Management

Single Source of Truth.

State must remain centralized.

UI reflects state.

State must not depend on UI.

---

# Error Handling

All critical operations must handle failures.

Examples:

- Import
- Export
- Storage
- Asset Loading

Errors must never crash the application.

---

# Performance

Avoid unnecessary DOM updates.

Avoid rendering loops.

Avoid excessive event listeners.

---

# Accessibility

Keyboard support required.

Focus indicators required.

Touch support required.

---

# Responsive Design

Desktop first.

Mobile fully supported.

No feature may require desktop only.

---

# Dependencies

Prefer zero dependencies.

Add dependencies only when:

- Significant value exists
- Maintenance cost is justified

---

# Breaking Changes

Never change:

- AIBP Format
- Asset IDs
- Project IDs

without migration support.

---

# Release Rule

A feature is not complete until:

- Works
- Saves
- Reloads correctly
- Functions on mobile
- Has no critical bugs