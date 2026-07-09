# Branch — Returns Workflow

## Feature Details

| Field | Value |
|-------|-------|
| **Feature Name** | Returns (Branch) |
| **Slug** | `branch-returns` |
| **Module** | Branch |
| **Navigation Path** | Branch Home → Returns |
| **Priority** | P2 |

## Business Purpose

Provides the branch with a sub-menu for managing all return flows — initiating returns to the manufacturer, viewing the branch's own return history, and processing incoming returns from pharmacies.

## Sub-Features

| Tile | Colour | Purpose |
|------|--------|---------|
| **Manufacturer Return** | Blue | Return packs from branch back to manufacturer |
| **My Returns** | Green | View history of returns initiated by this branch |
| **Incoming Returns** | Yellow/Tan | View and process returns from pharmacies sent to this branch |

---

## Manufacturer Return

### UI Elements (identical to Distributor Manufacturer Return)
| Element | Type | Description |
|---------|------|-------------|
| Scan area | Camera input | "Tap to scan pack / SSCC" |
| Note field | Optional text | Return reason |
| Initiate Return button | Primary action | Submits the return request |

### Happy Path
1. Tap **Manufacturer Return**.
2. Scan the pack or SSCC barcode.
3. Optionally add a note.
4. Tap **Initiate Return** → success confirmation.

---

## My Returns

### Happy Path
1. Tap **My Returns**.
2. List of returns created by this branch, with Return #, From/To GLN, Items, Created date, Status (CONFIRMED / CANCELLED).
3. Filterable by status.

---

## Incoming Returns

### Happy Path
1. Tap **Incoming Returns**.
2. List of returns sent to this branch by downstream pharmacies.
3. Statuses: PENDING (awaiting action), CANCELLED.
4. Tap a return to review and accept it.

## Edge Cases & Validation Rules

- Identical edge cases to Distributor Returns.
- PENDING incoming returns require branch action.

## Notes

- Returns UI is visually identical to the Distributor's Returns screen — same 3 sub-tiles, same colours.
- The branch acts as both sender (to manufacturer) and receiver (from pharmacies) in the returns chain.
