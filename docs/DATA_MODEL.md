# Data Model

Product: Visual Blueprint

Version: 1.0.0

Status: Stable

---

# Purpose

This document defines the official data structures used throughout Visual Blueprint.

All systems must use these structures consistently.

This document is the source of truth for:

- Storage
- Autosave
- Import
- Export
- Recovery
- AIBP
- AIBPZ

---

# Entity Overview

Visual Blueprint consists of:

- Project
- Node
- Connection
- Group
- Asset
- Settings
- Metadata

Relationships:

Project
├── Nodes
├── Connections
├── Assets
├── Settings
└── Metadata

---

# ID Rules

All IDs must be unique.

IDs must never change after creation.

---

## Project ID

Format:

project_xxxxxxxx

Example:

project_a1b2c3d4

---

## Node ID

Format:

node_xxxxxxxx

Example:

node_a1b2c3d4

---

## Connection ID

Format:

connection_xxxxxxxx

Example:

connection_a1b2c3d4

---

## Asset ID

Format:

asset_xxxxxxxx

Example:

asset_a1b2c3d4

---

## Group ID

Groups use Node IDs.

Group Node is a node type.

No separate group ID system.

---

# Project

Represents an entire blueprint.

---

Structure

```json
{
  "id": "project_a1b2c3d4",
  "name": "Website Redesign",
  "createdAt": "2026-08-17T12:00:00Z",
  "updatedAt": "2026-08-17T12:00:00Z",
  "version": "1.0.0",
  "nodes": [],
  "connections": [],
  "assets": [],
  "settings": {},
  "metadata": {}
}
```

---

# Node

Base structure for every node.

---

Structure

```json
{
  "id": "node_a1b2c3d4",
  "type": "text",
  "title": "Requirements",
  "position": {
    "x": 120,
    "y": 340
  },
  "size": {
    "width": 320,
    "height": 240
  },
  "data": {},
  "createdAt": "2026-08-17T12:00:00Z",
  "updatedAt": "2026-08-17T12:00:00Z"
}
```

---

# Node Types

Supported:

```text
text
note
checklist
link
image
file
group
```

---

# Text Node

```json
{
  "data": {
    "content": "# Markdown Supported"
  }
}
```

---

# Note Node

```json
{
  "data": {
    "content": "Meeting notes"
  }
}
```

---

# Checklist Node

```json
{
  "data": {
    "items": [
      {
        "id": "item_1",
        "text": "Create UI",
        "checked": true
      }
    ]
  }
}
```

---

# Link Node

```json
{
  "data": {
    "url": "https://example.com",
    "label": "Reference"
  }
}
```

---

# Image Node

```json
{
  "data": {
    "assetId": "asset_a1b2c3d4"
  }
}
```

---

# File Node

```json
{
  "data": {
    "assetId": "asset_a1b2c3d4"
  }
}
```

---

# Group Node

Groups are nodes.

Groups contain child nodes.

---

Structure

```json
{
  "data": {
    "children": [
      "node_001",
      "node_002"
    ],
    "collapsed": false
  }
}
```

---

# Connection

Represents a relationship between two nodes.

---

Structure

```json
{
  "id": "connection_a1b2c3d4",
  "sourceNodeId": "node_001",
  "targetNodeId": "node_002",
  "createdAt": "2026-08-17T12:00:00Z"
}
```

---

# Connection Rules

Allowed:

Node A → Node B

---

Not Allowed:

Node A → Node A

---

Invalid references rejected.

---

# Asset

Represents any stored file.

---

Structure

```json
{
  "id": "asset_a1b2c3d4",
  "type": "image",
  "name": "wireframe.png",
  "mimeType": "image/png",
  "size": 245781,
  "createdAt": "2026-08-17T12:00:00Z"
}
```

---

# Asset Types

Supported:

```text
image
file
```

---

# Asset Storage

Assets are stored separately from nodes.

Nodes reference assets using:

```json
{
  "assetId": "asset_a1b2c3d4"
}
```

---

# Metadata

Project metadata.

---

Structure

```json
{
  "lastOpenedAt": "2026-08-17T12:00:00Z",
  "lastExportedAt": null
}
```

---

# Settings

Project-specific settings.

---

Structure

```json
{
  "showGrid": false,
  "snapToGrid": false
}
```

---

# Application Settings

Stored separately from projects.

---

Structure

```json
{
  "theme": "system",
  "language": "en",
  "sidebarCollapsed": false
}
```

---

# Recovery State

Stored separately.

Used for session restoration.

---

Structure

```json
{
  "projectId": "project_a1b2c3d4",
  "zoom": 100,
  "canvas": {
    "x": 0,
    "y": 0
  }
}
```

---

# Validation Rules

Required:

- Valid IDs
- Valid timestamps
- Existing node references
- Existing asset references

---

Reject:

- Missing IDs
- Duplicate IDs
- Broken references
- Invalid types

---

# AIBP Serialization

Must export:

- Project
- Nodes
- Connections
- Settings
- Metadata

Must NOT export:

- Asset Files

---

# AIBPZ Serialization

Must export:

- Project
- Nodes
- Connections
- Settings
- Metadata
- Asset Files

---

# Versioning

Every project must contain:

```json
{
  "version": "1.0.0"
}
```

Used for future migrations.

---

# Forward Compatibility

Unknown fields must be preserved when possible.

Import should not fail simply because a newer version contains additional fields.

---

# Data Model Stability

Version 1.0.0 structures are considered stable.

Breaking changes require:

- Migration strategy
- Version update
- Changelog entry