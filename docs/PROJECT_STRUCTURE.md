# Project Structure

Version: 1.0.0

Status: Stable

---

# Overview

Visual Blueprint consists of two primary areas:

1. Home
2. Editor

Users always begin at Home.

Projects are opened inside the Editor.

---

# Application Layout

Desktop

┌──────────────┬──────────────────────┐
│ Sidebar      │ Main Content         │
└──────────────┴──────────────────────┘

---

Mobile

┌───────────────────────────┐
│ Header                    │
├───────────────────────────┤
│ Main Content              │
└───────────────────────────┘

Sidebar becomes an overlay drawer.

---

# Header

Visible globally.

Height:

56px

---

## Left Section

Contains:

- Sidebar Toggle
- Logo
- Application Name

---

## Center Section

Home:

Search Bar

Editor:

Hidden

Search must not occupy space while hidden.

---

## Right Section

Contains:

- Import
- Export
- Theme Toggle
- Settings

---

# Sidebar

Desktop:

Permanent

---

Mobile:

Overlay Drawer

---

# Sidebar Sections

## Navigation

Contains:

- Home
- Settings

---

## Projects

Displays all projects.

Each project item contains:

- Project Name
- Active Indicator
- Three Dot Menu

---

## Project Menu

Actions:

- Rename
- Duplicate
- Delete

---

## Active Project

The opened project must be visually highlighted.

Only one project may be active.

---

## Sidebar Collapse

Expanded:

280px

Collapsed:

72px

Collapsed State:

- Icons visible
- Labels hidden
- Tooltips enabled

State persists between sessions.

---

# Home

Purpose:

Project Management

---

# Home Sections

## Welcome

Displays:

- Product Name
- Short Description

---

## Quick Actions

Contains:

- New Project
- Import Project

---

## Project List

Displays all projects.

---

# Project Card

Displays:

- Project Name
- Last Modified
- Project Menu

---

# Multi Select Mode

Supports:

- Delete Selected
- Duplicate Selected

Rename only available when one project is selected.

---

# Empty State

Displayed when no projects exist.

Contains:

- Illustration
- Create Project Button
- Import Project Button

---

# Editor

Purpose:

Visual Workspace

Contains:

- Canvas
- Minimap
- Zoom Controls
- Save Status

---

# Canvas

Infinite Workspace.

Supports:

- Pan
- Zoom
- Selection
- Connections
- Groups

---

# Node Library

Purpose:

Node Creation

---

## Open Methods

Desktop:

Shift + A

---

Mobile:

Double Tap Empty Canvas

---

# Node Library Layout

Appears near cursor.

Contains:

Search Field

Node List

---

# Supported Nodes

- Text Node
- Note Node
- Checklist Node
- Link Node
- Image Node
- File Node
- Group Node

---

# Node Search

Search starts immediately when typing.

Search field receives focus automatically.

---

# Command Palette

Future Reserved.

Not part of Version 1.0.

---

# Asset Manager

Purpose:

Manage project assets.

---

# Asset Manager Features

View Assets

Search Assets

Replace Assets

Delete Assets

---

# Asset Categories

Images

Files

---

# Asset Preview

Images:

Thumbnail

---

Files:

File Icon

File Name

File Size

---

# Search System

Home Search:

Search projects only.

---

Editor Search:

Reserved for future versions.

Not included in Version 1.0.

---

# Minimap

Location:

Bottom Right

---

Displays:

- Nodes
- Groups
- Viewport

---

Updates:

Real Time

---

Can be hidden.

---

# Zoom Controls

Location:

Near Minimap

---

Displays:

Current Zoom %

---

Editable

Users may type values directly.

---

Limits

Minimum:

25%

Maximum:

300%

---

# Save Status

Location:

Bottom Left

---

Visible On

Desktop

Mobile

---

Examples

Saved 19:54

● Saved

---

# Context Menus

Used for:

- Nodes
- Projects
- Assets

---

Requirements

Stay inside viewport.

Close on outside click.

---

# Modals

Used only for destructive actions.

Examples:

Delete All Projects

Reset Application

---

Node creation must never use modal dialogs.

---

# Responsive Rules

Desktop

Keyboard First

---

Tablet

Hybrid

---

Mobile

Touch First

---

# Mobile Requirements

Must support:

- Node Creation
- Node Editing
- Connections
- Groups
- Import
- Export
- Settings

No desktop-only features allowed.

---

# Layout Requirements

Must not contain:

- Horizontal Scrolling
- Overlapping Components
- Hidden Controls
- Dead Buttons
- Placeholder Content

Every visible component must have a purpose.