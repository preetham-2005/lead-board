# Board Specification

## Purpose

Provides a personal Kanban task board with three columns, card creation, editing, drag-and-drop movement, and local persistence.

## Requirements

### Requirement: Three fixed columns with counts
The board SHALL display three fixed columns named "New", "Contacted", and "Won", each showing its current lead count.

#### Scenario: Column counts display correctly
- **WHEN** the board loads or leads are added, moved, or deleted
- **THEN** each column displays its name and the exact number of leads in that column

### Requirement: Validate non-empty title on save
The system SHALL require a non-empty name when adding or editing a lead and display a clear error message without saving if the name is empty.

#### Scenario: Saving card with empty title
- **WHEN** user attempts to save a lead with an empty name
- **THEN** a clear error message is displayed and the lead is not saved

### Requirement: Edit or delete card
The user SHALL be able to click any existing lead card to open an edit dialog to change its details, or delete the lead with confirmation.

#### Scenario: Editing card details
- **WHEN** user clicks a lead card, edits the name, phone number, or note, and saves
- **THEN** the updated lead details are reflected on the board and saved

#### Scenario: Deleting a card
- **WHEN** user clicks a lead card, clicks "Delete", and confirms "Are you sure?"
- **THEN** the lead is removed from the board and the column count decrements

### Requirement: Drag and drop cards between columns
The user SHALL be able to drag a card from any column and drop it into another column.

#### Scenario: Moving card across columns
- **WHEN** user drags a card to another column
- **THEN** the card moves to the target column and both column counts update immediately

### Requirement: Local storage persistence
The board state SHALL persist in the browser's local storage so all cards and columns survive a page refresh.

#### Scenario: Surviving page refresh
- **WHEN** cards exist on the board and the user refreshes the page
- **THEN** all cards remain in their respective columns with their saved details

### Requirement: Lead card with name and phone
The board SHALL represent each lead with a required name, optional Indian mobile number, and optional note, displaying the name and phone number directly on the card.

#### Scenario: Card displays name and phone
- **WHEN** a lead is displayed on the board
- **THEN** the card shows the lead name and Indian mobile number

#### Scenario: Refresh preserves lead details
- **WHEN** leads with name, phone, and note are present and the page is refreshed
- **THEN** all leads survive the refresh in their columns with correct details

### Requirement: Delete confirmation prompt
The system SHALL ask "Are you sure?" before deleting any lead and require confirmation before removing the lead from the board.

#### Scenario: User confirms lead deletion
- **WHEN** user confirms the "Are you sure?" delete prompt
- **THEN** the lead is permanently removed and the column count updates

#### Scenario: User cancels lead deletion
- **WHEN** user cancels the delete confirmation prompt
- **THEN** the lead remains unchanged on the board
