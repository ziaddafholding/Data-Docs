# Branch Module — Domain Knowledge

## Role
Login with a **Branch** account (`testbranch@eptts.com` / `Admin@123456`). A Branch is a **warehouse or storage facility** that acts as an intermediary between the distributor and pharmacies.

## Business Purpose
Branches receive pharmaceutical stock from distributors and manufacturers, store it, and dispatch shipments to pharmacies. They also handle bidirectional returns. The branch account in test data is named **"Main warehouse"**.

## Features

| Feature | Slug | Description |
|---------|------|-------------|
| Branch Home | `branch-home` | 7-tile grid (Create Shipment, My Shipments, Receive Shipment, Returns, EPCIS History, Delete Account, Logout) |
| Create Shipment | `branch-create-shipment` | Create outbound shipment to pharmacy |
| My Shipments | `branch-my-shipments` | View all shipments (in and out) with status tracking |
| Receive Shipment | `branch-receive-shipment` | Accept incoming shipments from manufacturers/distributors |
| Returns | `branch-returns` | Sub-menu: Manufacturer Return / My Returns / Incoming Returns |
| EPCIS History | `branch-epcis-history` | View EPCIS event log for this branch |

## Home Screen Tiles
| Tile | Content-Desc | Colour |
|------|-------------|--------|
| Create Shipment | `~Create Shipment` | Teal |
| My Shipments | `~My Shipments` | Purple |
| Receive Shipment | `~Receive Shipment` | Peach/Salmon |
| Returns | `~Returns` | Blue/Grey |
| EPCIS History | `~EPCIS History` | Green |
| Delete Account | `~Delete Account` | Pink/Red |
| Logout | `~Logout` | Grey/White |

## Supply Chain Position
```
Manufacturer → Distributor → [Branch] → Pharmacy → Patient
```

## Comparison with Distributor
| Aspect | Distributor | Branch |
|--------|-------------|--------|
| Home tile count | 5 | 7 (adds Delete Account + Logout) |
| Header text | — | "Hello / [Branch name]" |
| Create Shipment form | Identical | Identical |
| Returns sub-menu | Identical | Identical |
| Receive senders | Manufacturers | Manufacturers + Distributors |

## Observed Incoming Senders (Receive Shipment)
- Bio Egypt
- Janssen
- Upjohn EESV
- Pharmaoverseas Importer

## Shipment Statuses
Same as Distributor: **Draft**, **Dispatched**, **Delivered**, **Partially Delivered**

## EPCIS Event Types
| Type | Trigger |
|------|---------|
| SHIPPING | Branch dispatches a shipment |
| RECEIVING | Branch receives a shipment |
| UNPACKING | Container is unpacked at branch |

## Test Credentials
| Field | Value |
|-------|-------|
| Email | `testbranch@eptts.com` |
| Password | `Admin@123456` |

## Business Rules
- Create Shipment: Destination GLN + ERP Invoice Number required (same as Distributor)
- Receive Shipment: scan all packs against the invoice manifest
- Returns sub-menu is identical to Distributor returns (same 3 sub-features, same UI)
- Logout requires confirmation via dialog (same pattern as Inspector)
- Delete Account is a destructive action requiring confirmation