# Node Specification

Version: 1.0.0

Status: Stable

---

# Overview

Nodes are the core building blocks of Visual Blueprint.

Everything inside a project is represented as nodes.

Examples:

- Requirements
- Documentation
- Images
- Files
- Checklists
- References

All nodes must:

- Be movable
- Be selectable
- Be renameable
- Be deletable
- Support autosave
- Support undo/redo
- Support connections
- Work on desktop and mobile

---

# Shared Node Structure

All nodes follow the same structure.

Header

- Node Icon
- Node Title
- Node Type Indicator

Body

- Node Content

Footer

- Input Connector
- Output Connector

---

# Common Node Actions

Available on all nodes:

Rename
Duplicate
Delete

---

# Rename

Shortcut:

F2

Behavior:

- Select node
- Press F2
- Title enters edit mode

Enter:
Save

Escape:
Cancel

Click outside:
Save and exit

---

# Duplicate

Shortcut:

Ctrl + D

Creates a copy of the selected node.

---

# Delete

Shortcut:

Delete

or

Shift + X

---

# Text Node

Type:

text

Purpose:

Short information blocks.

Examples:

- Requirements
- Notes
- Ideas
- Labels

---

# Text Node UI

Compact.

Small default height.

Focused on quick editing.

---

# Text Node Content

Supports Markdown Lite.

Supported:

# Heading

## Heading

**Bold**

*Italic*

- Lists

[Links](https://...)

`Inline Code`

---

# Text Node Toolbar

Visible while editing.

Buttons:

Bold
Italic
Heading
List
Link
Code

Toolbar inserts syntax automatically.

Users should not be required to remember Markdown syntax.

---

# Text Node Limits

Recommended:

Up to 1,000 words.

Use Note Node for larger content.

---

# Note Node

Type:

note

Purpose:

Long-form documentation.

Examples:

- PRD
- Roadmap
- Technical Notes
- Research

---

# Note Node UI

Larger node.

Resizable.

Supports:

Edit Mode
Preview Mode
Split Mode

---

# Markdown Support

Full Markdown.

Supported:

Headings

Lists

Checklists

Tables

Links

Images

Code Blocks

Quotes

Horizontal Rules

---

# Toolbar

Buttons:

Bold
Italic
Heading 1
Heading 2
Heading 3

Bullet List

Numbered List

Checklist

Link

Code

Quote

Table

Image

Horizontal Rule

---

# Preview Mode

Renders Markdown.

Must match GitHub-style rendering as closely as possible.

---

# Checklist Node

Type:

checklist

Purpose:

Task tracking.

---

# UI

List of items.

Example:

☐ Research

☑ Design

☐ Testing

---

# Features

Add Item

Delete Item

Reorder Item

Mark Complete

---

# Autosave

Every checkbox change is saved automatically.

---

# Link Node

Type:

link

Purpose:

Store URLs and references.

---

# UI

Displays:

Title

URL

Domain Preview

---

# Actions

Open Link

Copy Link

Edit URL

---

# Validation

Must contain a valid URL.

---

# Image Node

Type:

image

Purpose:

Store visual references.

---

# Sources

Upload File

Image URL

---

# Supported Formats

PNG

JPG

JPEG

WEBP

SVG

---

# UI

Image Preview

Replace Image

Remove Image

Open Full View

---

# Missing Assets

If exported as .aibp:

Display:

Missing Asset

Image not included in this project file.

---

# File Node

Type:

file

Purpose:

Store file attachments.

---

# Supported Formats

PDF

DOCX

TXT

ZIP

PNG

JPG

WEBP

Other generic files

---

# UI

File Icon

File Name

File Size

---

# Actions

Download

Replace

Remove

---

# Missing Assets

If asset not available:

Display:

Missing File

This file was not included in the imported project.

---

# Group Node

Type:

group

Purpose:

Organize related nodes.

---

# UI

Container Area

Group Title

Resize Handles

---

# Features

Manual Resize

Auto Resize

Collapse

Expand

---

# Behavior

Nodes inside a group:

Move together

Remain associated

Persist after save/load

---

# Auto Resize

Enabled by default.

Group expands when:

- New node enters
- Existing node grows

---

# Connections

All nodes support connections.

Except:

Group Node

Groups cannot connect.

---

# Connection Points

Input

Output

---

# Rules

Allowed:

Node A → Node B

Not Allowed:

Node A → Node A

---

# Multiple Connections

Supported.

One node may connect to multiple nodes.

---

# Selection

Single Click

Select node

---

Ctrl + Click

Multi Select

---

Ctrl + A

Select All

---

# Mobile Behavior

Tap

Select node

---

Double Tap

Edit content

---

Long Press

Context menu

---

# Future Node Types

Reserved.

Potential future additions:

Code Node

Database Node

API Node

Embed Node

Template Node

AI Context Node

These are not part of Version 1.0.0.