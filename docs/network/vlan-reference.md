# VLAN Reference

The production network is segmented into discipline-specific VLANs managed through UniFi. Keeping traffic isolated by function protects time-sensitive protocols (Dante, MA-Net) from being impacted by general network load and simplifies troubleshooting.

## VLAN Table

| VLAN ID | Name | Purpose |
|---------|------|---------|
| 1 | BFC Access Points | Management network for UniFi APs and switches. Subnet: `192.168.0.0/16` |
| 20 | Guests | Isolated guest Wi-Fi. No access to production VLANs. |
| 47 | SecurityCameras | Security camera traffic, isolated from production systems. |
| 50 | Audio | General audio devices — consoles, amps, stage boxes, personal monitors, REAPER, SMAART. |
| 51 | Dante — Sanctuary | Dante AoIP network for the Sanctuary. Latency-sensitive; keep this VLAN clean and isolated. |
| 52 | Sanctuary IEM | In-ear monitor traffic for the Sanctuary. |
| 53 | WR IEMs | Wireless in-ear monitor traffic. |
| 54 | Dante — Worship Room | Dante AoIP network for the Worship Room. Separate from Sanctuary Dante to keep the two rooms' devices isolated. |
| 55 | Soundgrid | Waves Soundgrid server and plugin processing traffic. |
| 60 | Video | Video devices — ATEM switchers, NDI sources, PTZ cameras, CG machines, ProPresenter. |
| 61 | Displays | Display outputs and signage endpoints. |
| 62 | GreenGo | GreenGo digital intercom traffic. |
| 70 | Lighting | Lighting control — MA3 consoles, L-Nodes, grandMA network (MA-Net). |

## Notes

**Dante (VLAN 51)** requires special handling:

- Dante uses multicast UDP. Multicast must be enabled on any switch carrying Dante traffic.
- Do not mix Dante with general audio or video traffic on the same unmanaged network.
- Each Dante subnet (51, 52, 53, 54) is kept separate because Dante devices auto-discover all devices on the subnet — mixing unrelated systems creates noise and potential routing conflicts.
- VLAN 51 is the Sanctuary Dante network; VLAN 54 is the Worship Room Dante network. Do not put Sanctuary Dante devices on VLAN 54 or vice versa.

**Lighting (VLAN 70)** carries MA-Net, the grandMA3 network protocol. MA3 consoles, NPUs, and L-Nodes must all be on this VLAN to communicate.

**Trunk ports** carry multiple VLANs. Any port tagged as a trunk in UniFi allows all assigned VLANs to pass through — typically used for uplinks between switches and for multi-function endpoints.

## Access Points

Wi-Fi SSIDs are bound to specific VLANs. If a wireless device needs to be on a production VLAN, it must connect to the correct SSID — not the guest network.
