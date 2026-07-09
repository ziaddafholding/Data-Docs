# Branch — EPCIS History Workflow

## Feature Details

| Field | Value |
|-------|-------|
| **Feature Name** | EPCIS History (Branch) |
| **Slug** | `branch-epcis-history` |
| **Module** | Branch |
| **Navigation Path** | Branch Home → EPCIS History |
| **Priority** | P2 |

## Business Purpose

Shows the branch's full EPCIS event log — every supply-chain event (shipping, receiving, unpacking) submitted to the national EPTTS registry on behalf of this branch. Supports compliance monitoring and audit.

## UI Elements

| Element | Type | Description |
|---------|------|-------------|
| Status filter dropdown | Dropdown | "All statuses" → filter by Completed / Failed |
| Event list cards | List | Event hash ID, Event type, Sender, Receiver, Items, (Failed count), Event Time, Status badge |
| Status badges | Labels | Completed (green), Failed (red) |
| "View event errors" link | Link | On Failed entries |

## EPCIS Event Types Observed

| Event Type | Description |
|------------|-------------|
| **SHIPPING** | Pack dispatched from this branch |
| **RECEIVING** | Pack received by this branch |
| **UNPACKING** | Container unpacked at this branch |

## Happy Path

1. From Branch Home, tap **EPCIS History**.
2. EPCIS History opens with Status dropdown (default: "All statuses").
3. Event list shows all EPCIS events where this branch is sender or receiver.
4. Each card: UUID event hash, event type, Sender name, Receiver name, Items, Event Time, Status (Completed / Failed).
5. Failed entries show a failed count summary and a **View event errors** link.
6. Use the Status filter to narrow results.

## Observed Test Data

| Event Type | Sender | Receiver |
|------------|--------|----------|
| SHIPPING | Main warehouse | صيدلية د. هشام ابراهيم (Arabic pharmacy name) |
| SHIPPING | Main warehouse | PH Aswan esaaf 24 |
| UNPACKING | Main warehouse | Main warehouse |
| RECEIVING | Main warehouse | Main warehouse |

## Notes

- Event hashes are UUIDs (hex format).
- Multi-language receiver names observed (Arabic + English).
- Identical screen design to Distributor and Pharmacy EPCIS History.
