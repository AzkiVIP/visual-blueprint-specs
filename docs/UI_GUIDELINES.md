# UI Guidelines

Version: 1.0.0

Status: Stable

---

# Design Philosophy

Visual Blueprint is a productivity application.

The interface must prioritize:

- Clarity
- Consistency
- Readability
- Speed

Over:

- Visual effects
- Decorations
- Trendy design patterns

---

# Design Principles

## Function First

Every visible UI element must have a purpose.

No decorative components without functionality.

---

## Consistency

Identical actions must look and behave consistently across the application.

---

## Minimal Visual Noise

Reduce unnecessary colors, effects, and distractions.

The canvas content should always be the primary focus.

---

## Responsive By Default

Every screen must be usable on:

- Desktop
- Tablet
- Mobile

No feature may be desktop-only.

---

# Visual Style

Inspired By:

- Modrinth
- Linear
- Notion
- GitHub

Not Inspired By:

- Crypto Dashboards
- Heavy Glassmorphism
- Excessive Neon Effects
- AI Slop Interfaces

---

# Color System

## Dark Theme

Background

#0A0A0A

Surface

#111111

Secondary Surface

#171717

Border

#262626

Text

#FAFAFA

Muted Text

#A1A1AA

Primary

#2563EB

Success

#16A34A

Warning

#D97706

Danger

#DC2626

---

## Light Theme

Background

#F8FAFC

Surface

#FFFFFF

Secondary Surface

#F1F5F9

Border

#E2E8F0

Text

#0F172A

Muted Text

#64748B

Primary

#2563EB

Success

#16A34A

Warning

#D97706

Danger

#DC2626

---

# Color Rules

Blue is reserved for:

- Primary Buttons
- Active States
- Focus States
- Links

Blue must not be used as a page background.

Avoid blue-tinted dark backgrounds.

---

# Typography

## Headings

Font:

Space Grotesk

Weights:

600
700

---

## Body

Font:

Inter

Weights:

400
500

---

# Font Sizes

Heading Large

32px

---

Heading Medium

24px

---

Heading Small

20px

---

Body

14px

---

Small Text

12px

---

# Spacing System

Base Unit:

4px

Allowed spacing values:

4
8
12
16
20
24
32
40
48

Avoid arbitrary spacing values.

---

# Border Radius

Small

8px

---

Medium

12px

---

Large

16px

---

Do not exceed 16px.

Avoid pill-shaped interfaces unless functionally required.

---

# Borders

Default:

1px solid Border Color

Use borders instead of excessive shadows.

---

# Shadows

Minimal usage.

Allowed:

Dropdowns

Modals

Context Menus

Avoid shadows on every component.

---

# Buttons

## Primary Button

Used for:

- Create
- Add
- Confirm
- Import

Style:

Primary Color

---

## Secondary Button

Used for:

- Cancel
- Back
- Neutral Actions

Style:

Surface + Border

---

## Danger Button

Used for:

- Delete
- Reset
- Destructive Actions

Style:

Danger Color

---

# Inputs

Must support:

- Hover
- Focus
- Disabled

Focus state uses Primary Color.

---

# Icons

Library:

Lucide

Preferred Style:

Outlined

Consistent stroke width.

---

# Sidebar

Desktop Expanded

Width:

280px

---

Desktop Collapsed

Width:

72px

Icons only.

Labels hidden.

---

Mobile

Overlay Drawer

Hidden by default.

---

# Header

Height:

56px

Must remain fixed.

Contains:

- Sidebar Toggle
- Logo
- App Name

Home Only:

- Search Bar

Editor:

- Search Hidden

---

# Home Page

Purpose:

Project Management

Contains:

- Welcome Section
- Quick Actions
- Project List

No marketing sections.

No landing page content.

No feature showcase.

---

# Project Cards

Display:

- Project Name
- Last Modified
- Three Dot Menu

Actions:

- Rename
- Duplicate
- Delete

---

# Canvas

Purpose:

Workspace

Must occupy all remaining space.

---

# Grid

Optional.

Disabled by default.

---

Dark Theme Grid

Very subtle.

Must not compete with content.

---

# Nodes

Nodes are the primary visual elements.

Priority:

Highest

---

Node Background

Surface Color

---

Node Border

Border Color

---

Selected Node

Primary Border

---

Node Shadows

Disabled by default.

Use borders for separation.

---

# Connections

Appearance:

Clean

Simple

Readable

---

Avoid:

Heavy glow

Animated particles

Excessive gradients

---

# Minimap

Position:

Bottom Right

---

Default Size

200px × 140px

---

Can be hidden.

---

# Zoom Controls

Position:

Near Minimap

---

Must display:

Current Zoom Percentage

Editable by user.

---

# Save Status

Position:

Bottom Left

Visible on:

- Desktop
- Mobile

Examples:

Saved 19:54

● Saved

---

# Context Menus

Appear near cursor.

Must never leave viewport.

Close when clicking outside.

---

# Modals

Use only when necessary.

Examples:

- Delete All Projects
- Reset Application

Avoid modal overuse.

---

# Animations

Duration:

150ms–250ms

---

Use for:

- Menus
- Dropdowns
- Sidebar

---

Do Not Animate:

- Every button
- Every hover state
- Canvas interactions

---

# Mobile Rules

Touch Target:

Minimum 44px

---

No Horizontal Scroll

Outside Canvas

---

All Core Features Must Work

Including:

- Node Creation
- Connections
- Groups
- Import
- Export
- Settings

---

# Accessibility

Minimum Contrast:

WCAG AA

---

Keyboard Navigation Required

Desktop

---

Focus Indicators Required

Interactive Elements

---

# Prohibited UI Patterns

Do Not Use:

- Heavy Glow
- Neon Effects
- Blue Background Tint
- Floating Decorative Elements
- Glassmorphism Overuse
- Auto Playing Animations
- Unnecessary Gradients
- Marketing Landing Page Sections

---

# Quality Checklist

Before Release Verify:

- No broken layouts
- No horizontal scrolling
- No overlapping components
- No inaccessible controls
- No unused buttons
- No placeholder content
- Responsive layouts function correctly
- Dark theme and light theme both work