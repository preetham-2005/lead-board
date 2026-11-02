# Proposal: Lead Board

## Why

A small business needs a streamlined way to track sales prospects from initial contact to closing deals. Transforming the generic Kanban task board into a dedicated Lead Board simplifies lead management, capturing essential contact information (name, phone number, note) and tracking deal progress across three clear sales stages without unnecessary complexity.

## What Changes

- **Columns**: Replace generic task lanes ("To Do", "Doing", "Done") with sales pipeline stages: "New", "Contacted", and "Won".
- **Card Content**: Replace task title and color strip with lead details:
  - Lead Name (required)
  - Phone number (optional, displayed on the card)
  - Short note (optional, visible and editable in modal)
- **Delete Confirmation**: When clicking delete on a lead card, require explicit user confirmation ("Are you sure?") before removing the lead.
- **Validation**: Require a non-empty lead name before saving; show a clear validation error message if the name is blank.
- **Persistence**: Save leads and their respective stages to browser local storage so all data survives a page refresh.
- **Styling**: Align with the approved mockup in `design/leads.html` following minimalist-ui principles.

## Capabilities

### New Capabilities
None.

### Modified Capabilities
- `board`: Modify column definitions to "New", "Contacted", "Won"; replace task attributes with lead contact fields (name, phone, note); add delete confirmation prompt; update empty name validation.

## Impact

- Affects `index.html` (UI markup, CSS styling, and client-side JavaScript state/storage logic).
- No new external libraries or dependencies added.
