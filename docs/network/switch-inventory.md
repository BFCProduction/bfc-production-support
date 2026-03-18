# Switch Inventory

All production switches are UniFi managed and accessible through the UniFi Network controller on VLAN 1. Each switch has a system name, a management IP, and a physical location.

## Production Switches

| Sys Name | Model | IP Address | Location |
|----------|-------|------------|----------|
| Production Video 1 | USW Pro Max 48 POE | 192.168.9.205 | VDR |
| Production Video 2 | USW Pro Max 48 POE | 192.168.9.206 | VDR |
| Production Video 3 | USW Pro Max 24 POE | 192.168.9.207 | ADR3 — Upstairs |
| Production BOH | USW Pro Max 48 POE | 192.168.9.210 | ADR2 — Backstage |
| Production FOH East | USW Pro Max 24 POE | 192.168.9.208 | FOH — Audio |
| Production FOH West | USW Pro Max 24 POE | 192.168.9.209 | FOH — Lights |
| Atrium Production Switch | US 48 | 192.168.9.205 | VDR |

## Switch Roles

**VDR (Video Distribution Rack)**
The VDR houses the three largest switches. Production Video 1 and 2 are the primary backbone switches — most production devices uplink here. The Atrium Production Switch serves the Atrium area from the same rack.

**ADR3 — Upstairs**
Production Video 3 serves the upstairs area. It carries amplifiers (A-AMP series), L-Nodes, and ControlFlex units. It uplinks back to the VDR.

**ADR2 — Backstage**
Production BOH covers the backstage area including wireless mics (W-MIC series), backstage amplifiers, IEM wing control, and choir/band room devices.

**FOH — Audio (East)**
Production FOH East is the audio console switch. It carries SpaceFLEX, ChoirFLEX, REAPER, Digico, SMAART, Waves, GreenGo antenna, and front-of-house break-out panels.

**FOH — Lights (West)**
Production FOH West serves the lighting position. It carries Mac Studio workstations (VLAN 51, 60, and 70), camera connections, lighting controllers (MA3 nodes), and break-out panels.

## Accessing a Switch

1. Open the UniFi Network controller
2. Navigate to **Devices**
3. Find the switch by sys name or IP
4. Click to open — port status, VLAN assignments, and traffic stats are all visible here

To SSH into a switch directly, use the management IP on VLAN 1. Credentials are stored in the password manager.

## SFP Uplink Ports

On the 48-port models, ports 49–52 are SFP+ uplinks. These are typically used for inter-switch fiber or DAC connections. On the 24-port models, ports 25–26 are SFP uplinks. Uplink ports are trunk ports carrying all production VLANs.
