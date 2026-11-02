# Tasks: Lead Board

## 1. Board Layout and Columns

- [x] 1.1 Update columns in `index.html` to "New", "Contacted", and "Won" and verify the column headers and count badges render in the browser
- [x] 1.2 Implement the "Add lead" button on each column and verify clicking it opens the lead creation dialog

## 2. Lead Cards and Minimalist-UI Design

- [x] 2.1 Style the board and cards according to `design/leads.html` with minimalist-ui typography, warm bone background, and subtle borders, verifying the layout matches in the browser
- [x] 2.2 Render lead cards with lead name and optional phone number (with phone icon) and optional note badge, and verify they display correctly in the browser

## 3. Lead Creation, Editing and Validation

- [x] 3.1 Implement the lead dialog fields for Name (required), Phone (optional), and Note (optional), and verify the input fields can be typed into in the browser
- [x] 3.2 Add empty name validation that prevents saving and displays a clear error message, and verify attempting to save without a name shows the error in the browser
- [x] 3.3 Enable clicking any lead card to open the edit dialog pre-filled with its name, phone, and note, and verify saving updates the card in the browser

## 4. Delete with "Are You Sure?" Confirmation

- [x] 4.1 Implement the delete button and inline "Are you sure?" confirmation prompt, and verify clicking delete asks for confirmation before removing the lead in the browser
- [x] 4.2 Support canceling the delete confirmation, and verify the lead is retained untouched in the browser

## 5. Drag-and-Drop and Persistence

- [x] 5.1 Implement native drag-and-drop between columns, and verify dragging a lead to another column updates the column counts immediately in the browser
- [x] 5.2 Persist all leads and column locations to `localStorage`, and verify that refreshing the browser retains all leads, edits, and column positions

## Workflow follow-up

- Run Ponytail review to ensure no unnecessary complexity or libraries were added.
- Run complete 7+ check user journey test in the browser.
- Record bug report and verification.
- Archive the change with OpenSpec.
