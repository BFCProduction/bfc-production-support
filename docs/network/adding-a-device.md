# Adding a Device to the Network

Use this guide when connecting a new or relocated device to the production network.

---

## Step 1 — Determine the Correct VLAN

Match the device type to its VLAN. If unsure, check the [VLAN Reference](vlan-reference.md).

| VLAN | Device type |
|------|-------------|
| 1 | UniFi AP or switch (management) |
| 20 | Guest Wi-Fi device |
| 47 | Security cameras |
| 50 | General audio — console, Mac running audio software, REAPER, SMAART |
| 51 | Dante — Sanctuary (audio interfaces, stageboxes, amplifiers in the Sanctuary) |
| 52 | Sanctuary IEM system |
| 53 | Wireless IEM system |
| 54 | Dante — Worship Room (audio interfaces, stageboxes, amplifiers in the Worship Room) |
| 55 | Waves Soundgrid server or satellite |
| 60 | Video — ATEM, NDI device, CG machine, ProPresenter, PTZ |
| 61 | Displays and signage |
| 62 | GreenGo intercom |
| 70 | MA3 console, NPU, L-Node, ControlFlex, GPIO, show control |

---

## Step 2 — Find the Right Switch and Port

Check the [Port Documentation](port-documentation.md) spreadsheet to find a free port on the switch closest to where the device will live. Use the location guide:

| Area | Switch |
|------|--------|
| VDR | Production Video 1 or 2 |
| Upstairs (ADR3) | Production Video 3 |
| Backstage (ADR2) | Production BOH |
| FOH Audio position | Production FOH East |
| FOH Lights position | Production FOH West |
| Atrium | Atrium Production Switch |

---

## Step 3 — Configure the Port in UniFi

1. Open the UniFi Network controller.
2. Go to **Devices** and select the switch.
3. Click the **Ports** tab.
4. Find the port number and click to edit.
5. Set **Native VLAN** to the correct VLAN ID for the device.
6. If the port needs to carry multiple VLANs (trunk), add the additional VLANs under **Tagged VLANs**.
7. Enable **PoE** if the device requires it.
8. Save.

!!! note "Access vs. Trunk ports"
    Most devices get an **access port** — one VLAN, untagged. Uplink ports between switches and multi-VLAN endpoints (like a Mac running Dante and Video simultaneously) need a **trunk port** with the required VLANs tagged.

---

## Step 4 — Assign a Static IP (if required)

Most production devices use static IPs, not DHCP. Refer to the [Port Documentation](port-documentation.md) spreadsheet per-VLAN tabs for existing IP assignments on that VLAN — pick an unused address in the static range.

**IP address scheme:** All production VLANs use the `10.1.XX.YYY` scheme, where `XX` is the VLAN ID:

| VLAN | Subnet | Static range | DHCP range |
|------|--------|-------------|------------|
| 50 (Audio) | 10.1.50.x | .1 – .99 | .100 – .255 |
| 51 (Dante — Sanctuary) | 10.1.51.x | .1 – .99 | .100 – .255 |
| 52 (Sanctuary IEM) | 10.1.52.x | .1 – .99 | .100 – .255 |
| 53 (WR IEMs) | 10.1.53.x | .1 – .99 | .100 – .255 |
| 54 (Dante — Worship Room) | 10.1.54.x | .1 – .99 | .100 – .255 |
| 55 (Soundgrid) | 10.1.55.x | .1 – .99 | .100 – .255 |
| 60 (Video) | 10.1.60.x | .1 – .99 | .100 – .255 |
| 61 (Displays) | 10.1.61.x | .1 – .99 | .100 – .255 |
| 62 (GreenGo) | 10.1.62.x | .1 – .99 | .100 – .255 |
| 70 (Lighting) | 10.1.70.x | .1 – .99 | .100 – .255 |

Addresses `.1` through `.99` are reserved for static assignment. Addresses `.100` through `.255` are DHCP. Always assign production devices a static IP in the `.1–.99` range — check the spreadsheet first to avoid conflicts.

Assign the IP directly on the device. Do not rely on DHCP for production endpoints.

---

## Step 5 — Update the Port Documentation

Open the [Port Documentation spreadsheet](https://docs.google.com/spreadsheets/d/1LpTyOXKnHZKCInrUXSrsrzCz6LdnJ3pxZm89U5FVQXo/edit) and update:

- The **Switch Layout** tab — add the device name and VLAN ID to the correct port cell
- The **per-VLAN tab** for that device's VLAN — add the device name and IP

This keeps the spreadsheet current for the whole team.

---

## Step 6 — Verify Connectivity

- Confirm the device gets its expected IP.
- For Dante devices: open Dante Controller and verify the device appears on the correct subnet.
- For MA3 devices: run a network scan in the MA3 shell.
- For video devices: verify the device is reachable from other devices on VLAN 60.
- For GreenGo: verify the device appears in the GreenGo software.

If the device doesn't appear, check [Network Troubleshooting](network-troubleshooting.md).
