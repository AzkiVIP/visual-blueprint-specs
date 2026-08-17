# Storage System

Version: 1.0.0

Status: Stable

---

# Philosophy

Visual Blueprint follows a Local First architecture.

User data belongs to the user.

No account is required.

No cloud service is required.

The application must remain fully functional offline.

---

# Storage Layers

## IndexedDB

Primary storage system.

Stores:

- Projects
- Nodes
- Groups
- Connections
- Assets
- Project Metadata

Must be used for all project data.

---

## LocalStorage

Stores lightweight preferences only.

Examples:

- Theme
- Language
- Sidebar State
- Last Opened Project

Must never store project content.

---

# Autosave

Autosave is mandatory.

There is no manual save button.

---

## Autosave Triggers

Project:

- Create
- Rename
- Delete
- Duplicate

Nodes:

- Create
- Delete
- Rename
- Move
- Resize
- Content Change

Groups:

- Create
- Delete
- Rename
- Resize

Connections:

- Create
- Delete

Assets:

- Add
- Replace
- Remove

Settings:

- Change

---

## Autosave Rules

Save only when data changes.

Do not save continuously.

Recommended debounce:

300ms

---

# Recovery System

If the browser closes unexpectedly:

Restore:

- Last Opened Project
- Zoom Level
- Canvas Position
- Selection State

---

# Project Formats

## AIBP

Extension:

.aibp

Purpose:

Project Data Only

Contains:

- Project
- Nodes
- Groups
- Connections
- Settings

Does NOT contain:

- Images
- Files

---

## AIBPZ

Extension:

.aibpz

Purpose:

Full Project Bundle

Contains:

- Project
- Nodes
- Groups
- Connections
- Settings
- Images
- Files
- Metadata

Recommended for sharing.

---

# Asset Storage

Supported:

Images:

- PNG
- JPG
- JPEG
- WEBP
- SVG

Documents:

- PDF
- DOCX
- TXT

Archives:

- ZIP

---

# Missing Assets

When importing .aibp:

Missing assets must not crash the project.

Display:

Missing Asset

or

Missing File

---

# Data Integrity

Every save operation must validate:

- Node IDs
- Group IDs
- Asset IDs
- Connection IDs

Invalid references must be rejected.

---

# Performance Targets

Project Load:

< 2 seconds

Autosave:

Non-blocking

Import:

Responsive

Export:

Responsive