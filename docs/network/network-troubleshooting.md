# Network Troubleshooting

Common network issues on the production system and how to resolve them.

---

## Device Not Showing Up on the Network

**Symptom:** A device is connected but not visible to other devices or software.

1. Check that the cable is seated and the switch port shows a link light.
2. Open the UniFi controller → **Clients** and confirm the device has an IP address.
3. If the device has an IP in the wrong subnet, the port VLAN is probably wrong. Check the port assignment in UniFi against the [Port Documentation](port-documentation.md).
4. If the device has no IP at all, check whether it expects a static IP or DHCP. Most production devices use static IPs.

---

## Dante Devices Not Discovering Each Other

**Symptom:** Dante Controller doesn't see a device, or devices show up on different subnets.

1. Confirm both devices are on the same Dante VLAN (51, 52, 53, or 54). Dante can only route within the same subnet without a Dante domain manager.
2. Open Dante Controller — if a device shows a different subnet (e.g., it's on Audio VLAN 50 instead of Dante VLAN 51), the port is on the wrong VLAN. Fix it in UniFi.
3. Check that multicast is functioning. Dante uses multicast for discovery. If a switch has multicast filtering enabled incorrectly, devices will appear offline.
4. If a device was previously visible and suddenly disappeared, check for a duplicate IP conflict in Dante Controller.

!!! warning "Dante VLAN isolation"
    Do not move Dante devices onto the general Audio VLAN (50) or any other VLAN. Each Dante VLAN is isolated by design. Mixing Dante traffic with other protocols can cause latency issues and discovery failures.

---

## MA3 / Lighting Devices Not Communicating

**Symptom:** MA3 console can't see an L-Node or NPU, or session won't sync.

1. Confirm all MA3 devices (console, NPU, L-Nodes) are on VLAN 70 (Lighting).
2. In the MA3 shell, run a network scan and verify all nodes appear with correct IPs.
3. Check the switch port for each device in UniFi — it should be assigned to VLAN 70 untagged.
4. If a node recently moved or was re-patched, update the [Port Documentation](port-documentation.md) and verify the new port is correctly assigned.

---

## GreenGo Intercom Not Working

**Symptom:** GreenGo devices can't communicate or don't appear in the GreenGo software.

1. GreenGo runs on VLAN 62. Confirm the device's port is on VLAN 62 in UniFi.
2. GreenGo uses multicast — same considerations as Dante. If discovery fails, check multicast settings on the switch.
3. Verify the GreenGo antenna at FOH East is connected and on VLAN 62.

---

## Can't Reach a Switch for Management

**Symptom:** Can't access the UniFi controller or a switch's management page.

1. Management traffic runs on VLAN 1 (192.168.0.0/16). Your computer must be on VLAN 1 to reach the controller.
2. If you're at FOH or a remote position, you may need to be on the management network. Check with the lead engineer.
3. If the UniFi controller itself is unreachable, the controller host machine may be offline. The controller runs on a machine in the VDR — check power and connectivity there first.

---

## Slow or Degraded Network Performance

**Symptom:** Audio dropouts, video glitches, or latency on network-dependent systems.

1. Open the UniFi controller and check **Insights → Traffic** for any switch showing high utilization.
2. Check for any device generating broadcast storms (a single misbehaving device can saturate a VLAN).
3. For Dante specifically — even brief congestion can cause audio dropouts. Dante VLANs (51–54) should carry only Dante traffic. If a non-Dante device ended up on a Dante VLAN, move it.
4. Check SFP uplink ports on the VDR switches for errors. A bad DAC cable or SFP can cause intermittent issues across all downstream devices.

---

## Port Shows as Connected But Device Doesn't Work

**Symptom:** Link light is on, UniFi shows the port up, but the device doesn't function.

1. Check the VLAN assignment — the port may be up on the wrong VLAN.
2. Check PoE. Some devices require PoE and may appear connected on link but aren't powered. Verify PoE is enabled for the port in UniFi.
3. Try a different cable or a different port to rule out a hardware fault.
