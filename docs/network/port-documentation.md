# Port Documentation

Per-port VLAN assignments, device labels, and switch layout diagrams are maintained in the **Sanctuary Production Network Info** spreadsheet. This is the source of truth for what is plugged into what.

## Spreadsheet

[Open Port Documentation Spreadsheet](https://docs.google.com/spreadsheets/d/1LpTyOXKnHZKCInrUXSrsrzCz6LdnJ3pxZm89U5FVQXo/edit){ .md-button }

## What's in the Spreadsheet

**Switch Layout tab** — The primary reference. Shows every switch with each port numbered, the VLAN ID assigned to that port, and the device label. Color-coded by VLAN:

| Color | VLAN |
|-------|------|
| Red | VLAN 50 — Audio |
| Dark Red | VLAN 51 — Dante |
| Green | VLAN 62 — GreenGo |
| Yellow/Orange | VLAN 60 — Video |
| Cyan | VLAN 61 — Displays |
| Purple/Lavender | VLAN 70 — Lighting |
| Pink | Trunk (multiple VLANs) |

**Per-VLAN tabs** — Each VLAN has its own tab listing all devices on that VLAN across all switches: Switches (VLAN 1), Audio (VLAN 50), Dante (VLAN 51), Soundgrid (VLAN 55), Video (VLAN 60), Displays (VLAN 61), and more.

## How to Read a Switch Block

Each switch block in the spreadsheet shows:

- **Sys Name** — The name as it appears in UniFi
- **IP Address** — Management IP on VLAN 1
- **Location** — Physical location in the building
- **Port rows** — Odd ports (1, 3, 5…) on top, even ports (2, 4, 6…) on bottom, matching the physical face of the switch
- **VLAN ID row** — The VLAN assigned to that port
- **Device row** — What's plugged in

SFP uplink ports are shown at the far right of each block, labeled separately.

## Keeping It Current

When you move or add a device, update the spreadsheet. The spreadsheet is shared with the team — changes are visible immediately. If you're adding a new device, also check [Adding a Device to the Network](adding-a-device.md) for the full process.
