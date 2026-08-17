# User Flows

Product: Visual Blueprint

Version: 1.0.0

Status: Stable

---

# Purpose

This document defines the expected user journeys within Visual Blueprint.

User flows describe how users interact with the application to complete common tasks.

These flows must remain simple, predictable, and consistent.

---

# Design Principles

All user flows should:

- Minimize unnecessary clicks
- Avoid dead ends
- Preserve user context
- Support autosave
- Work on desktop and mobile

---

# Flow 1

Create New Project

---

Goal:

Create a new project and enter the editor.

---

Steps:

Home

↓

Click "New Project"

↓

Project Created

↓

Project Added To Sidebar

↓

Project Opens Automatically

↓

Editor Displayed

↓

Autosave Active

---

Expected Result:

User enters editor immediately and can start working.

---

# Flow 2

Rename Project

---

Goal:

Rename an existing project.

---

Steps:

Home Or Sidebar

↓

Open Project Menu

↓

Select Rename

↓

Edit Name

↓

Confirm

↓

Autosave

---

Expected Result:

Project name updates everywhere.

---

# Flow 3

Duplicate Project

---

Goal:

Create a copy of a project.

---

Steps:

Home Or Sidebar

↓

Open Project Menu

↓

Select Duplicate

↓

Copy Created

↓

Automatic Naming

Example:

Project

Project (1)

Project (2)

---

Expected Result:

Duplicate appears in project list.

Current project remains unchanged.

---

# Flow 4

Delete Project

---

Goal:

Remove a project.

---

Steps:

Home Or Sidebar

↓

Open Project Menu

↓

Delete

↓

Confirmation Dialog

↓

Confirm

↓

Autosave

---

Expected Result:

Project removed permanently.

---

# Flow 5

Open Existing Project

---

Goal:

Continue working on a project.

---

Steps:

Home

↓

Select Project

↓

Open Editor

↓

Restore:

- Canvas Position
- Zoom Level
- Open State

---

Expected Result:

Project restores previous state.

---

# Flow 6

Create Node

---

Goal:

Add content to canvas.

---

Desktop:

Shift + A

---

Mobile:

Double Tap Empty Canvas

---

Steps:

Open Node Library

↓

Search Optional

↓

Select Node Type

↓

Node Created

↓

Node Selected

---

Expected Result:

Node appears near cursor.

---

# Flow 7

Rename Node

---

Goal:

Rename selected node.

---

Steps:

Select Node

↓

Press F2

↓

Edit Name

↓

Click Outside Or Confirm

↓

Autosave

---

Expected Result:

Node title updated.

---

# Flow 8

Edit Node Content

---

Goal:

Add or modify information.

---

Steps:

Select Node

↓

Edit Content

↓

Autosave

---

Expected Result:

Content saved automatically.

---

# Flow 9

Delete Node

---

Goal:

Remove node.

---

Method A

Delete Key

↓

Node Removed

---

Method B

X

↓

Delete Menu

↓

Confirm

↓

Node Removed

---

Expected Result:

Node deleted.

Connections removed automatically.

---

# Flow 10

Connect Nodes

---

Goal:

Create relationships between nodes.

---

Steps:

Select Output Handle

↓

Drag Connection

↓

Connection Preview Visible

↓

Hover Compatible Input Handle

↓

Snap

↓

Release

↓

Connection Created

---

Rules:

Cannot connect node to itself.

Invalid connections rejected.

---

Expected Result:

Connection saved automatically.

---

# Flow 11

Create Group

---

Goal:

Organize related nodes.

---

Steps:

Create Group Node

↓

Move Nodes Into Group

↓

Group Expands Automatically

---

Expected Result:

Nodes become children of group.

---

# Flow 12

Resize Group

---

Goal:

Adjust group area.

---

Steps:

Select Group

↓

Drag Resize Handle

↓

Resize

↓

Autosave

---

Expected Result:

Group size updated.

---

# Flow 13

Upload Image

---

Goal:

Add image asset.

---

Steps:

Create Image Node

↓

Upload File

Or

Paste URL

↓

Image Loaded

↓

Asset Registered

↓

Autosave

---

Expected Result:

Image visible inside node.

---

# Flow 14

Upload File

---

Goal:

Attach file to project.

---

Steps:

Create File Node

↓

Choose File

↓

Asset Registered

↓

Autosave

---

Expected Result:

File available inside project.

---

# Flow 15

Delete Asset

---

Goal:

Remove asset.

---

Steps:

Open Asset Manager

↓

Select Asset

↓

Delete

↓

Reference Check

↓

Confirmation

↓

Delete

---

Expected Result:

Asset removed safely.

---

# Flow 16

Import Project

---

Goal:

Load external project.

---

Steps:

Home

↓

Import

↓

Select:

- AIBP
- AIBPZ

↓

Validate

↓

Import

↓

Project Added

---

Expected Result:

Project appears in list.

---

# Flow 17

Export Project

---

Goal:

Save project externally.

---

Steps:

Open Project

↓

Export

↓

Choose Format

- AIBP
- AIBPZ

↓

Generate File

↓

Download

---

Expected Result:

Portable project file created.

---

# Flow 18

Search Projects

---

Goal:

Find projects quickly.

---

Steps:

Home

↓

Search Bar

↓

Type Query

↓

Project List Filtered

---

Expected Result:

Matching projects displayed instantly.

---

# Flow 19

Change Theme

---

Goal:

Switch application appearance.

---

Steps:

Settings

↓

Theme

↓

Select:

- Light
- Dark
- System

↓

Apply

↓

Autosave

---

Expected Result:

Theme updates immediately.

---

# Flow 20

Recover Session

---

Goal:

Continue after accidental closure.

---

Steps:

Open Application

↓

Restore Last State

↓

Restore:

- Project
- Zoom
- Canvas Position

---

Expected Result:

User continues where they left off.

---

# Flow 21

Reset Application

---

Goal:

Remove all local data.

---

Steps:

Settings

↓

Reset Application

↓

Warning Dialog

↓

Confirm

↓

Delete Data

↓

Reload

---

Expected Result:

Fresh installation state.

---

# Desktop Interaction Rules

Preferred Input:

Keyboard + Mouse

---

Node Creation:

Shift + A

---

Rename Node:

F2

---

Delete Node:

Delete

Shift + X

---

Select All:

Ctrl + A

---

# Mobile Interaction Rules

Preferred Input:

Touch

---

Node Creation:

Double Tap Empty Canvas

---

Sidebar:

Drawer

---

Menus:

Bottom Sheet Or Context Menu

---

No desktop-only workflows allowed.

---

# Error Handling Rules

Invalid imports:

Show Error

Do Not Crash

---

Missing assets:

Show Placeholder

Do Not Crash

---

Storage failures:

Show Notification

Do Not Crash

---

# Autosave Rules

Every successful action updates project state.

Users should never need a Save button.

---

# User Experience Goal

Users should be able to:

Create Project

↓

Create Nodes

↓

Connect Information

↓

Add Assets

↓

Export Project

without reading documentation.