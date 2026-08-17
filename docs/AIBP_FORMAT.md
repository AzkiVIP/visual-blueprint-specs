# AIBP Format Specification

Version: 1.0.0

Status: Stable

---

# Overview

AIBP (AI Blueprint Project) is the native project format used by Visual Blueprint.

The format is designed to be:

- Human readable
- Portable
- Versioned
- Extensible
- Platform independent

---

# File Extensions

## Project File

.aibp

Contains:

- Project data
- Nodes
- Groups
- Connections
- Settings

Does not contain binary assets.

---

## Project Bundle

.aibpz

ZIP-based container.

Contains:

- project.aibp
- metadata.json
- assets/

Recommended format for sharing projects.

---

# Root Structure

Example:

{
  "version": "1.0.0",
  "project": {},
  "nodes": [],
  "groups": [],
  "connections": [],
  "assets": [],
  "settings": {}
}

---

# Version

Required.

Example:

{
  "version": "1.0.0"
}

Purpose:

- Compatibility checking
- Migration support
- Future upgrades

---

# Project Object

Example:

{
  "id": "project_001",
  "name": "Website Planning",
  "createdAt": "2026-08-17T10:00:00Z",
  "updatedAt": "2026-08-17T12:00:00Z"
}

Fields:

id
string

Unique identifier.

---

name
string

Project display name.

---

createdAt
ISO timestamp

Creation date.

---

updatedAt
ISO timestamp

Last modification date.

---

# Nodes

Stores all nodes.

Example:

{
  "id": "node_001",
  "type": "text",
  "title": "Homepage",
  "position": {
    "x": 400,
    "y": 200
  },
  "size": {
    "width": 300,
    "height": 180
  },
  "data": {}
}

---

# Node Fields

id

Unique identifier.

---

type

Supported:

- text
- note
- checklist
- link
- image
- file
- group

---

title

Display name.

---

position

Canvas position.

Example:

{
  "x": 100,
  "y": 200
}

---

size

Node dimensions.

Example:

{
  "width": 300,
  "height": 200
}

---

data

Node-specific content.

---

# Text Node

Example:

{
  "type": "text",
  "data": {
    "content": "Landing page requirements"
  }
}

---

# Note Node

Example:

{
  "type": "note",
  "data": {
    "content": "Long form documentation..."
  }
}

---

# Checklist Node

Example:

{
  "type": "checklist",
  "data": {
    "items": [
      {
        "text": "Research",
        "completed": true
      },
      {
        "text": "Design",
        "completed": false
      }
    ]
  }
}

---

# Link Node

Example:

{
  "type": "link",
  "data": {
    "url": "https://example.com"
  }
}

---

# Image Node

Example:

{
  "type": "image",
  "data": {
    "assetId": "asset_001"
  }
}

Image nodes never store binary image data directly.

Assets are referenced by assetId.

---

# File Node

Example:

{
  "type": "file",
  "data": {
    "assetId": "asset_002"
  }
}

Files are referenced through assetId.

---

# Groups

Groups are stored separately.

Example:

{
  "id": "group_001",
  "title": "Authentication",
  "position": {
    "x": 100,
    "y": 100
  },
  "size": {
    "width": 600,
    "height": 400
  },
  "collapsed": false,
  "children": [
    "node_001",
    "node_002"
  ]
}

---

# Connections

Stores node relationships.

Example:

{
  "id": "connection_001",
  "source": "node_001",
  "target": "node_002"
}

Rules:

- Self-connections not allowed
- Source and target must exist

---

# Assets

Stores references to project assets.

Example:

{
  "id": "asset_001",
  "type": "image",
  "name": "hero.png",
  "path": "assets/images/hero.png",
  "size": 254812
}

---

Supported Asset Types

Images:

- PNG
- JPG
- JPEG
- WEBP

Files:

- PDF
- DOCX
- TXT
- ZIP

---

# Settings

Project-specific settings.

Example:

{
  "theme": "system",
  "showGrid": true,
  "snapToGrid": true,
  "showMinimap": true
}

---

# Metadata

Stored inside metadata.json for .aibpz.

Example:

{
  "bundleVersion": "1.0.0",
  "exportedAt": "2026-08-17T12:00:00Z",
  "exportedBy": "Visual Blueprint"
}

---

# AIBPZ Structure

Example:

My Project.aibpz

├── project.aibp
├── metadata.json
└── assets/
    ├── images/
    │   ├── hero.png
    │   └── banner.jpg
    │
    └── files/
        ├── spec.pdf
        └── assets.zip

---

# Compatibility Rules

Applications must:

- Ignore unknown fields
- Preserve unknown fields when saving
- Validate required fields
- Reject corrupted project files

---

# Future Expansion

Reserved for:

- Comments
- Tags
- Templates
- Plugins
- Collaboration
- Cloud Sync

Applications must not remove reserved sections.