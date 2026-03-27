# Dana Dolly V3 Beltless — Spectrum ST4/ST4.3 Sensor and Marker Install

*Source: [eMotimo Support](https://support.emotimo.com/hc/en-us/articles/39083339405965)*

The DDV3 Spectrum kit includes a sensor board, marker stickers, and a dongle that sits between the Spectrum head and the sensor board. The sensor enables automatic end-stop detection and ping-pong shot calibration.

---

## Before You Start

- Confirm your Spectrum ST4/ST4.3 is on the correct firmware. As of October 2025, this is **RC008_24_B3** — check the release notes for the latest version.
- Have the motor physically installed on the Dana Dolly ([Install guide](dana-dolly-v3-install.md)).

---

## Spectrum I/O Port Setting

Power up the Spectrum and go to:

**Settings → (Page 5/7) → I/O Port → Set to: Ext. Trigger**

!!! note
    If end stops don't behave correctly after install, try the newer **Ext. Trig Reversed** option added in recent firmware.

---

## Dongle Wiring

The dongle connects three things:

1. **USB-C power in** — from a standard USB power source (V-Mount or Gold Mount battery USB-A/C output works well)
2. **4-wire locking connector** — to the sensor board
3. **3-lead I/O cable** — to the Spectrum's I/O port

!!! danger "Do NOT use Tilta D-Tap to USB-C cables"
    These unregulated cables can deliver up to 16.5V and will permanently damage the sensor board, potentially your camera, and other connected gear. Use a standard USB power source only.

When powered correctly, both LEDs on the dongle (green and red) should illuminate.

---

## Sensor Board Mounting

1. Disengage the drive wheel so you can slide the dolly manually.
2. Attach the sensor board to the DDV3 mount using the M4 screw — **finger tight only** to start.
    - Channel faces the carriage mount; wires face outward.
3. Position the board **as high as possible** on the mount while keeping it level (parallel to the track).
4. Lightly snug the screw.
5. **Check the LEDs** — they should go off when the sensor "sees" the track surface via reflection. If they stay on, the board is too far from the track.
6. Slide the dolly along the full length of track. Both LEDs should remain **off** throughout.
7. If LEDs turn on mid-track, loosen and reposition the board slightly lower. Repeat until LEDs stay off across the full run.
8. Once correct, lightly snug the screw. **Do not overtighten** — the sensor stalk is plastic and will break. Use the short end of the wrench for less leverage.
9. Re-engage the drive wheel.

---

## Wire Routing

The motor wire anchors to the back of the housing. Run the motor pod wire and track sensor wire together through the included Velcro wraps. The dongle can be mounted on top of the Dana Dolly.

---

## Marker Sticker Install

Stickers establish left stop, right stop, and midpoint positions on the track. Placement matters in two dimensions: **left/right position** and **placement on top of the round rail** (centered on the highest point — the centerline the two sensors straddle).

**Left End Stop:**
Move the dolly to the left end. Place the sticker so that when traveling left, both LEDs activate **6–8 inches before** the dolly would hit the end — typically about 15–16 inches from the left end of track.

**Right End Stop:**
Move the dolly to the right end. Place the sticker so that when traveling right, both LEDs activate **6–8 inches before** the end — typically about 13–14 inches from the right end of track.

**Midpoint Marker:**
Place between the two end stops (exact position doesn't matter as long as it's centered). The sticker centerline goes on top of the rail, straddling the two sensors.

Press all stickers flat — nothing should be lifting off the rail surface.

---

## When You Need Marker Stickers

| Use Case | Stickers Needed |
|---|---|
| Single-pass shots | None required |
| Ping-pong interview shooting | Midpoint marker only |
| Remote installs (dolly out of sight) | All three (left stop, right stop, midpoint) |

---

## Testing the Install

With everything powered up, manually slide the dolly along the track:

- **Clean track** — both LEDs should be off
- **Left stop sticker** — both LEDs turn on; the Spectrum auto-sets the left stop
- **Right stop sticker** — both LEDs turn on; the Spectrum auto-sets the right stop
- **Midpoint sticker** — green LED triggers on the back black portion, red LED on the front portion; both should clearly turn on and off

!!! tip
    Traverse each sticker **slowly** (about 1 inch per second or less) when testing.

If you get stuck at a stop, press **Options** on the controller to clear the stops.

When all tests pass, proceed to [calibration and first ping-pong shot](dana-dolly-v3-calibration.md).
