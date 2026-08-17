# Architecture

Version: 1.0.0

Status: Stable

---

# Overview

Visual Blueprint follows a layered architecture.

The goal is to keep:

- Logic separated
- UI maintainable
- Features scalable
- State predictable

---

# Core Principles

## Single Source of Truth

Application state must exist in one central location.

UI should reflect state.

UI must not become the source of truth.

---

## Separation of Concerns

Each layer has a clear responsibility.

Do not mix:

- UI
- Storage
- Project Logic
- Canvas Logic

inside the same module.

---

## Local First

All core functionality must work without internet access.

---

## Progressive Enhancement

Core features must work before optional enhancements.

Example:

Canvas works first.

Animations are secondary.

---

# Layer Structure

UI Layer
↓
Editor Layer
↓
Project Layer
↓
Storage Layer

---

# UI Layer

Responsible for:

- Sidebar
- Header
- Menus
- Modals
- Notifications
- Settings

Must not:

- Save projects directly
- Modify IndexedDB directly

All actions must go through application state.

---

# Editor Layer

Responsible for:

- Canvas
- Nodes
- Groups
- Connections
- Selection
- Minimap
- Zoom
- Pan

This is the workspace engine.

---

# Project Layer

Responsible for:

- Create Project
- Rename Project
- Delete Project
- Duplicate Project
- Import
- Export

Must not handle UI rendering.

---

# Storage Layer

Responsible for:

- IndexedDB
- Recovery
- Autosave
- Project Persistence

Must not know anything about UI.

---

# Application State

Centralized state object.

Example:

{
  "currentProject": "",
  "projects": [],
  "selectedNodes": [],
  "zoom": 100,
  "theme": "dark"
}

State is the single source of truth.

---

# Project Lifecycle

Create Project
↓
Load Project
↓
Edit Project
↓
Autosave
↓
Export (Optional)

---

# Node Lifecycle

Create Node
↓
Update State
↓
Render Node
↓
Autosave

---

# Connection Lifecycle

Create Connection
↓
Validate
↓
Store
↓
Render
↓
Autosave

---

# Group Lifecycle

Create Group
↓
Add Children
↓
Update State
↓
Render
↓
Autosave

---

# Rendering System

Rendering must be state-driven.

Bad:

Node modifies DOM directly everywhere.

Good:

State changes
↓
Renderer updates UI

---

# Autosave System

Autosave is event-driven.

Triggers:

- Node Create
- Node Delete
- Node Move
- Node Rename
- Connection Create
- Connection Delete
- Group Changes
- Asset Changes
- Project Changes

---

# Autosave Rules

Never save on every animation frame.

Save only when data changes.

Use debounce.

Recommended:

300ms

---

# Selection System

Supports:

- Single Select
- Multi Select
- Select All

Selection state stored centrally.

---

# Undo / Redo

State snapshots.

Actions tracked:

- Create
- Delete
- Move
- Rename
- Connect
- Disconnect

Must not track visual-only events.

---

# Asset System

Assets are separate from nodes.

Nodes reference assets.

Example:

Node
↓
assetId
↓
Asset Record

Benefits:

- Reusable
- Smaller project files
- Easier export

---

# Import System

Steps:

1. Read file
2. Validate format
3. Validate version
4. Load assets
5. Restore state
6. Render

---

# Export System

Steps:

1. Collect project data
2. Collect assets
3. Generate bundle
4. Export file

---

# Validation

Before save:

Validate:

- Node IDs
- Group IDs
- Connection IDs
- Asset IDs

Reject invalid references.

---

# Error Handling

Errors must never crash the editor.

If possible:

- Show notification
- Preserve project
- Continue operation

---

# Performance Targets

Project Load:
< 2 seconds

Canvas Interaction:
60 FPS target

Autosave:
Non-blocking

Zoom:
Smooth

Pan:
Smooth

---

# Mobile Architecture

Same data model.

Different interaction model.

Desktop:

- Keyboard First

Mobile:

- Touch First

No separate project format.

---

# Future Architecture

Reserved for:

- Plugin System
- Templates
- Collaboration
- Cloud Sync
- Version History

Current architecture must remain compatible with future expansion.