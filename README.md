# Ledger — Notes

A single-file, local-first Markdown note-taking web app. Open `ledger-notes-app.html` in a browser — no build step or server required. Notes are saved to your browser's `localStorage`.

|--|--|
| ![Ledger Notes in light mode, showing the note list sidebar on the left and the selected note's rendered markdown in the preview pane on the right.](ledger-note-light.png) | ![Ledger Notes in dark mode, showing the note list sidebar on the left and the selected note's rendered markdown in the preview pane on the right.](ledger-notes-light.png) |

## Features

- **Local-first**: notes are stored immediately in `localStorage`.
- **Markdown**: bold, italic, lists, admonitions, and task checkboxes.
- **Tags**: organize and filter notes by tag.
- **Themes**: follows your OS light/dark preference, with a manual override.
- **Keyboard shortcuts**:
  - `Cmd/Ctrl + .` — new note
  - `Cmd/Ctrl + Enter` — save and exit edit mode

## Export / Import

Open **Settings** to back up or restore your notes.

- **Export all notes** — saves every note to a single Markdown file (`ledger-notes-export.md`).
- **Import all notes** — loads a previously exported Markdown file. This **overwrites** all existing notes (you'll be asked to confirm first).

### Export file format

Each note is exported as a block of Markdown text with a YAML-style frontmatter header holding its metadata.
Notes are separated by a `<!-- ledger-note -->` marker:

```markdown
<!-- ledger-note -->
---
id: note-1718000000000
title: Meeting notes
tags: meetings, work
lastModified: 1718000000000
---

# Meeting notes

Your markdown content goes here.
```

Because the body is plain Markdown, exported files stay readable and portable in any editor. The frontmatter (`id`, `title`, `tags`, `lastModified`) is parsed back into each note on import.
