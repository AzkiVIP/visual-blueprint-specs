# Asset System

Version: 1.0.0

Status: Stable

---

# Overview

The Asset System manages all files and images used inside Visual Blueprint projects.

Assets are stored separately from nodes.

Nodes reference assets using Asset IDs.

This architecture improves:

- Performance
- Reusability
- Storage Efficiency
- Export Reliability

---

# Design Principles

## Single Asset Source

An asset should exist only once inside a project.

Multiple nodes may reference the same asset.

---

## Node Independence

Nodes do not own files.

Nodes only reference assets.

---

## Export Compatibility

Assets must remain compatible with:

- AIBP
- AIBPZ

---

## Local First

Assets are stored locally.

No cloud storage is required.

---

# Asset Types

Version 1.0 supports:

## Images

- PNG
- JPG
- JPEG
- WEBP
- SVG

---

## Documents

- PDF
- DOCX
- TXT

---

## Archives

- ZIP

---

## Generic Files

Unknown file types should be accepted whenever technically possible.

---

# Asset Structure

Example:

{
  "id": "asset_001",
  "type": "image",
  "name": "homepage.png",
  "size": 245781,
  "mimeType": "image/png",
  "createdAt": "2026-08-17T12:00:00Z"
}

---

# Required Fields

## id

Unique identifier.

Must never change.

---

## type

Asset category.

Examples:

image

file

---

## name

Original file name.

---

## size

Stored in bytes.

---

## mimeType

Original MIME type.

---

## createdAt

Creation timestamp.

---

# Asset IDs

Format:

asset_xxxxx

Example:

asset_001

asset_002

asset_003

IDs must be unique within a project.

---

# Asset Storage

Assets are stored separately from:

- Nodes
- Groups
- Connections

Nodes reference assets through asset IDs.

Example:

{
  "assetId": "asset_001"
}

---

# Image Assets

Used by:

- Image Node
- Note Node Attachments

---

# File Assets

Used by:

- File Node
- Note Node Attachments

---

# Asset References

Nodes must reference assets by ID.

Never by file path.

Bad:

{
  "path": "images/photo.png"
}

Good:

{
  "assetId": "asset_001"
}

---

# Embedded Asset References

Supported inside Markdown.

Example:

![Wireframe](asset://asset_001)

---

File Example:

[Download Spec](asset://asset_002)

---

# Missing Assets

Missing assets must never crash the project.

Display:

Missing Asset

or

Missing File

depending on asset type.

---

# Asset Upload

Supported Sources:

## Local File

User selects file.

---

## Drag and Drop

Supported.

---

## URL

Images only.

Version 1.0.

---

# Asset Validation

Before accepting an asset:

Validate:

- File Exists
- File Size
- MIME Type

Reject corrupted uploads.

---

# Asset Replacement

Users may replace assets.

Asset ID remains unchanged.

References remain valid.

---

# Asset Removal

When deleting an asset:

System must verify:

Is asset referenced?

---

If referenced:

Display confirmation.

Example:

This asset is used by 3 nodes.

Delete anyway?

---

# Duplicate Assets

Version 1.0 does not automatically merge duplicate assets.

Future optimization may add deduplication.

---

# Asset Manager

Version 1.0 includes a simple Asset Manager.

Capabilities:

- View Assets
- Search Assets
- Replace Assets
- Delete Assets

---

# Asset Preview

Images:

Thumbnail Preview

---

Files:

File Icon

File Name

File Size

---

# Export Rules

## AIBP

Exports:

- Asset References

Does NOT export:

- Asset Files

Result:

Assets may become unavailable.

---

## AIBPZ

Exports:

- Asset References
- Asset Files

Result:

Fully portable project.

---

# Import Rules

## AIBP

Restore:

- References

Assets may be missing.

---

## AIBPZ

Restore:

- References
- Files

No missing assets expected.

---

# Project Bundle Structure

Example:

project.aibpz

├── project.aibp
├── metadata.json
└── assets/
    ├── images/
    └── files/

---

# Performance Requirements

Asset operations must remain responsive.

Target:

Asset Preview < 200ms

Asset Upload < 1s for common files

Asset Search Instant

---

# Security

Assets must never execute code.

Uploaded files are treated as data only.

Executable files must not be automatically run.

---

# Future Expansion

Reserved for:

- Asset Tags
- Asset Collections
- Asset Versioning
- Asset Deduplication
- Cloud Asset Storage

These features are not part of Version 1.0.