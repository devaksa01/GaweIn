# Noternize

## Philosophy

Build a production-grade offline-first notes application that is simple for users and maintainable for developers.

---

# Core Principles

- Offline First
- No Account Required
- User Owns Their Data
- Feature-first Architecture
- Simplicity over Cleverness
- Performance First
- Testability
- Scalability

---

# v0.1.0 Scope (Aligned with PRD)

## In Scope

- Android only
- Block-based note editor: rich text, images, to-do blocks (Super Editor + custom blocks)
- Folders, trash, settings (theme, trash retention)
- Export/import: per-note and full-library `.ntz` bundle; `.txt` for single-note plain export
- Manual backup via `file_picker` / `flutter_file_dialog` (no Google Drive API in v0.1)
- Pomodoro timer (standalone feature)
- Local persistence: Isar for notes/folders/trash; Hive for app preferences

## Out of Scope (v0.1)

- Drawing, tables, infinite canvas
- Google Drive API, OAuth, realtime sync
- Donation / rewarded ads
- iOS, Web

---

# Tech Stack

## Framework

Flutter

## Language

Dart

## State Management

Riverpod

## Routing

GoRouter

## Database

Isar — notes, folders, trash, embedded metadata, `.ntz` domain models

## Preferences

Hive — theme, trash retention, export/import UI preferences (non-relational settings only)

## Rich Text & Editor

Super Editor — rich text blocks; custom block widgets for to-do lists and images

## Image Processing

image — resize/compress embedded images before storage

## File Picker

file_picker

## Native File Dialog

flutter_file_dialog

## Serialization

json_serializable — `.ntz` bundle and note document schema (include format version field)

## Logging

logger

## Testing

flutter_test
integration_test

---

# Architecture

Feature-first architecture with lightweight Clean Architecture.

```
Presentation
↓
Provider
↓
Use Case
↓
Repository
↓
Database / File I/O
```

## Editor Model (v0.1)

- **Block-based document**, not infinite canvas
- Block types: `richText`, `image`, `todoList`
- Document stored as ordered list of blocks (JSON via Isar + `.ntz` export)
- Repositories own all persistence; UI never touches Isar/Hive directly

## Data Ownership

| Store | Responsibility |
|-------|----------------|
| Isar | Notes, folders, trash, block documents, image binary refs |
| Hive | Theme, trash retention days, last export path hint, feature flags |
| File system | User-chosen export/import paths via system dialogs only |

## Sync / Backup (v0.1)

- No in-app cloud SDK
- User exports `.ntz` bundle → saves via OS dialog (local folder or cloud app if user picks it)
- User imports `.ntz` bundle → app validates version and applies merge/replace policy

---

# Folder Structure

```
lib/
│
├── core/
├── features/
│   ├── notes/
│   ├── editor/
│   ├── folders/
│   ├── trash/
│   ├── export_import/
│   ├── pomodoro/
│   └── settings/
├── shared/
└── main.dart
```

---

# Coding Rules

- Keep Widgets Small
- Business Logic Never Inside UI
- Repository Is The Only Database Gateway
- Avoid Global State
- Prefer Composition Over Inheritance
- One Responsibility Per Class

---

# Git Strategy

main

develop

feature/<feature-name>

fix/<bug>

release/<version>

---

# Branch Naming

feature/note-editor

feature/pomodoro

feature/folder

feature/export-import

fix/import

---

# Commit Convention

feat:

fix:

refactor:

docs:

style:

test:

perf:

build:

chore:

---

# Definition of Done

## Core paths (notes, editor, folders, trash, export/import)

- Feature implemented per PRD acceptance criteria
- Unit tests for use cases and repositories
- Widget or integration test for primary user flow
- No analyzer warnings in touched code
- No unresolved TODOs in shipped code
- CHANGELOG or relevant doc updated if behavior is user-visible

## Supporting features (Pomodoro, settings)

- Feature implemented per PRD acceptance criteria
- Unit tests for non-trivial logic
- No analyzer warnings in touched code

---

# Performance Goals

App startup < 2s

Create note < 300ms

Scrolling 60 FPS

---

# Future (Post-v0.1)

- Drawing and handwriting blocks
- Table blocks
- Infinite / free-roam canvas
- Google Drive API and optional automatic sync
- Realtime sync
- Collaboration
- Plugin system
- Optional donation (card + rewarded ads)
- iOS and Web targets
