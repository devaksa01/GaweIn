# Product Requirements Document (PRD)

> Single source of truth for product requirements.
> Focus on WHAT and WHY, not implementation.

---

# Project

Name: Noternize

Description: A free, no-login notes app with no ads in the core experience. Users can write block-based notes with rich text, images, and to-do lists; organize notes in folders; back up and restore data via manual export/import; use a Pomodoro timer; and access all core features offline on Android (v0.1.0).

Version: v0.1.0

Status: Planning

Owner: AS Adhyaksa A.K.A Devaksa01

---

# Vision

To create an actually good notes-taking app without annoying ads or forced accounts, so anyone can use it and own their data.

---

# Problem Statement

- Notes-taking apps are usually full of annoying ads.
- Some notes-taking apps force users to pick a single note type, but users cannot mix text, tasks, and media in one note.
- Some notes-taking apps require sign-in or an account to back up or sync notes.
- Some notes-taking apps limit how much content fits in a note.

---

# Goals

- Ads-free core experience (no ads in notes, editor, or primary flows)
- Core functions fully offline
- No account required, with user-controlled backup via export/import
- Useful as a learning companion (notes + Pomodoro)
- Mixed content in one note (text, images, to-do blocks) — block-based editor in v0.1

---

# Non-Goals (v0.1.0)

- Drawing or handwriting in notes
- Tables in notes
- Infinite or free-roam canvas layout
- Google Drive API or OAuth-based cloud sync
- Real-time sync or collaboration
- Web or iOS builds (Android only for v0.1.0)
- Handwriting recognition
- End-to-end encryption
- Optional donation page (card or rewarded ads)
- Server-side analytics or user tracking

---

# Target Users

## Primary

- Anyone who loves to take notes or learn with a Pomodoro timer
- Students who need to take notes in class

## Secondary

- People who want to write tasks in to-do lists inside their notes

---

# User Stories

- As a student, I want to write important things from today's class, so that I know what was discussed last time
- As a student, I want to use a Pomodoro timer, so that I can stay focused while learning
- As a businessperson, I want to jot down ideas in my notes, so that I can brainstorm on my own

---

# Core Flow

Open App
 ↓
Home
 ↓
Select features (Notes, Pomodoro)

## Notes

Home
↓
Notes
↓
Create Note
↓
Save / Export notes
↓
Back to Notes

## Trashcan

Home
↓
Notes
↓
Trashcan
↓
Restore / Delete permanently / Empty trash
↓
Back to Notes

## Pomodoro

Home
↓
Pomodoro Timer
↓
Adjust time
↓
Start
↓
Stop

## Settings

Home
↓
Settings
↓
Apply (theme, trash retention, export preferences)
↓
Back to Home

---

# MVP (v0.1.0)

## In Scope

- Block-based notes: rich text, images, and to-do blocks in one note
- Text styling: bold, italic, font, font-size, H1, H2, H3, subscript, superscript
- View, edit, save, and delete notes (all local)
- Export single note to `.ntz` or `.txt`
- Import single note from `.txt` or `.ntz`
- Single-file export/import of all notes and folders (`.ntz` bundle)
- Folders: create, edit, delete; move notes in/out of folders
- Trashcan: restore, permanent delete, empty trash (retention configurable in settings)
- Pomodoro timer: adjustable duration, start/stop
- Settings: theme, trash retention, export/import preferences
- Android only

## Deferred (Post-v0.1)

- Drawing and handwriting blocks
- Table blocks
- Infinite / free-roam canvas
- Google Drive API and automatic cloud sync
- Optional donation (card payment or rewarded ads)
- iOS and Web
- Real-time sync, collaboration, plugin system

---

# Functional Requirements

## Feature Name

Create block-based notes

Acceptance Criteria

- [ ] User can create a new note
- [ ] Note is saved locally
- [ ] Title is optional
- [ ] Note can start blank
- [ ] Symbols, emojis, unicode, superscript, and subscript are supported in text
- [ ] User can add rich text, an image, or a to-do block in the same note
- [ ] Blocks can be added, edited, and reordered within the note

---

## Feature Name

Manipulate text inside notes

Acceptance Criteria

- [ ] User can apply bold, italic, headers (H1, H2, H3), subscript, and superscript
- [ ] User can change font and font size

---

## Feature Name

View Notes

Acceptance Criteria

- [ ] User can view notes clearly based on their preferences (e.g. theme)

---

## Feature Name

Edit Notes

Acceptance Criteria

- [ ] User can edit existing notes
- [ ] Edited notes render correctly with no unexpected layout or content loss

---

## Feature Name

Save Notes

Acceptance Criteria

- [ ] Notes auto-save or save on explicit action (product decision at implementation)
- [ ] Saved notes render correctly with no unexpected changes
- [ ] Unsaved work is recovered after an unexpected app close where technically feasible

---

## Feature Name

Delete Notes

Acceptance Criteria

- [ ] User can delete a note
- [ ] Deleted notes are held in trash according to user-configured retention (settings)

---

## Feature Name

Trashcan

Acceptance Criteria

- [ ] Trashed notes retain full content and can be restored
- [ ] User can permanently delete individual trashed notes or empty trash

---

## Feature Name

Folders and folder management

Acceptance Criteria

- [ ] User can create, rename, and delete folders
- [ ] User can move notes into and out of folders

---

## Feature Name

Export notes

Acceptance Criteria

- [ ] User can export a single note to `.ntz` or `.txt` via the system file picker or save dialog
- [ ] Exported files open/import correctly in Noternize

---

## Feature Name

Import `.txt` and `.ntz` notes

Acceptance Criteria

- [ ] User can import a single note from `.txt` or `.ntz`
- [ ] Imported notes render correctly

---

## Feature Name

Single-file all-notes export/import

Acceptance Criteria

- [ ] User can export all notes and folder structure to one `.ntz` bundle via file picker / save dialog
- [ ] User can import all notes from one `.ntz` bundle
- [ ] Import merges or replaces according to a clear, documented user choice (e.g. merge vs replace all)
- [ ] Bundle size remains reasonable for typical personal note libraries

---

## Feature Name

Pomodoro Timer

Acceptance Criteria

- [ ] User can adjust focus duration
- [ ] User can start and stop the timer
- [ ] Timer counts down accurately while the app is in foreground (background behavior documented if limited in v0.1)

---

## Feature Name

Settings

Acceptance Criteria

- [ ] User can change theme (e.g. light / dark / system)
- [ ] User can configure trash retention period
- [ ] User can set export/import preferences where applicable
- [ ] Settings persist across app restarts

---

# Non-Functional Requirements

## Performance

- App startup < 2 seconds on a mid-range Android device
- Create note < 300 ms

## Reliability

- Crash-free rate > 95%
- Automatically recover in-progress note content when possible after unexpected exit

## Security

- No server-side collection of user data
- No accounts or authentication in v0.1
- Note data stays on device unless the user explicitly exports it

## Accessibility

- Support system font scaling

## Offline Support

- All v0.1 features work fully offline
- Export/import uses local file picker; saving to cloud storage (e.g. Drive) is via the OS share/save flow, not an in-app cloud API

## Compatibility

- Long-term: Android, iOS, and Web
- v0.1.0: Android only

---

# Constraints

## Technical

- Flutter (see PROJECT.md for stack)

## Business

- Free to use
- No ads in core product flows in v0.1
- Optional donation flows deferred to post-v0.1

## Budget

- ~$40 (e.g. Play Store developer account, domain)

## Time

- No fixed deadline; ship v0.1 when scope is stable and tested

---

# Success Metrics

- More than 1K downloads
- Minimum 4.5 star average rating
- App runs reliably without critical errors in core flows (create, edit, save, export, import, trash)

---

# Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| Block editor scope (rich text + images + todos) takes longer than expected | High | Ship block types incrementally; defer drawing/tables/canvas |
| `.ntz` format changes break older exports | Medium | Version field in format; document migration rules early |
| Super Editor + custom blocks integration complexity | Medium | Spike early; keep v0.1 blocks minimal |
| Solo development + strict quality bar slows release | Medium | Strict tests on core paths; lighter coverage on Pomodoro/settings |
| Users expect full “free-roam” canvas from marketing language | Medium | Clear store listing and in-app copy: block-based editor in v0.1 |

---

# Open Questions

- Import conflict policy: merge by note ID, skip duplicates, or prompt user?
- Auto-save interval vs save-on-blur vs explicit save button?
- Pomodoro: background timer and notifications in v0.1, or foreground-only?
- Maximum image size / compression defaults for embedded images?
- Trash default retention period (e.g. 30 days)?
