# CG A Dante Virtual Soundcard

CG A (Computer Graphics A) runs Dante Virtual Soundcard to route audio from full-screen video playback into the Dante network. This page covers the required settings and how to verify it is working correctly.

---

## Overview

When a full-screen video plays on CG A (via ProPresenter or another application), its audio is routed through Dante Virtual Soundcard onto the Dante network rather than through a local audio output. This allows the A1 to receive and control CG A video audio at the FOH console like any other Dante source.

The corresponding fader on the SD12 is the **CG A** fader.

---

## Dante Virtual Soundcard Settings

Open the Dante Virtual Soundcard application on CG A and confirm these settings:

| Setting | Value |
|---|---|
| Audio Channels | 2×2 |
| Dante Latency | 10ms |
| Network Interface | USB (or the interface in the .51 VLAN range) |

The network interface should show an IP address in the **10.1.51.x** range (Dante VLAN). If it shows a different IP, select the correct interface.

---

## Verifying Audio is Working

To confirm CG A Dante is routing correctly:

1. Play a video with audio on CG A
2. At the SD12, check for signal on the **CG A** fader
3. Confirm signal is present and routed through the PA Mix Bus and Broadcast Matrix

This is part of the [Sunday Gameday Checklist](../workflows/sunday-gameday-checklist.md) — coordinate with the Video Engineer to play a test video.

---

## Notes

- Dante Virtual Soundcard must be running and licensed before audio will pass
- If CG A audio is absent at the console, first check that the DVS application is active and showing the correct network interface
- The Dante VLAN is 10.1.51.x — see the network documentation for VLAN details

