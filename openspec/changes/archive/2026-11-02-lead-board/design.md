# Design: Lead Board

## Context

The application is built inside a single file (`index.html`) using vanilla HTML, CSS, and JavaScript. Data is stored purely in the browser's `localStorage`. The look is guided by `design/leads.html` and the `minimalist-ui` skill. See `proposal.md` for overall motivation.

## Goals / Non-Goals

**Goals:**
- Provide a responsive 3-column Lead Board: "New", "Contacted", and "Won".
- Display lead cards showing Name (bold) and Phone Number with a clean phone icon.
- Allow adding and editing leads with Name (required), Phone (optional), and Note (optional).
- Show an inline "Are you sure?" confirmation prompt before deleting a lead.
- Validate that the lead name is non-empty, preventing save and showing a clear error message.
- Support native drag-and-drop between columns with immediate column count updates.
- Persist state automatically to `localStorage` across page reloads.

**Non-Goals:**
- No server-side database or network APIs (all browser-local).
- No external frameworks or JavaScript libraries (e.g., no React, Tailwind, SortableJS, or Lodash).
- No complex multi-user authentication.

## Decisions

1. **Architecture & Scope**: Everything resides in `index.html`. Follow the Ponytail rules: native platform features, zero external dependencies, minimum clean code.
2. **Data Structure**: Store an array of lead objects in `localStorage` under `lead_board_data`:
   ```javascript
   {
     id: "lead-...",
     name: "string",
     phone: "string",
     note: "string",
     columnId: "new" | "contacted" | "won"
   }
   ```
3. **Delete Confirmation Flow**: Clicking "Delete" in the lead modal reveals an inline confirmation warning: `"Are you sure you want to delete this lead?"` with `"Yes, delete"` and `"Cancel"` actions. This prevents accidental deletion without requiring jarring alert popups.
4. **Drag and Drop**: Utilize the browser's native HTML5 Drag and Drop API with visual lane highlighting on `dragover`.
5. **Styling & Aesthetics**: Adhere to `minimalist-ui` guidelines with a warm off-white canvas (`#F7F6F3`), crisp borders (`1px solid #E2E2DC`), refined typography, and subtle muted badges.

## Risks / Trade-offs

- **[Risk] Accidental lead deletion**:
  → *Mitigation*: Delete button requires explicit secondary confirmation ("Are you sure?").
- **[Risk] Missing name validation bypassed**:
  → *Mitigation*: Trimming input string check on submit; displays inline error banner and keeps modal open.
- **[Risk] State desynchronization on refresh**:
  → *Mitigation*: Single source of truth in memory synchronized to `localStorage` on every add, edit, move, or delete event.
