# Dana Dolly V3 Beltless — Conductor SA2.6 Sensor and Marker Install

*Source: [eMotimo Support](https://support.emotimo.com/hc/en-us/articles/37141280517389)*

The DDV3 Conductor kit includes a sensor board and marker stickers. The sensor board connects directly to the Conductor SA2.6's 4-pin I/O port — no separate dongle or USB power needed.

---

## Before You Start

- Make sure the Conductor SA2.6 is on the latest firmware. ([Firmware guide](dana-dolly-v3-firmware.md))
- Have the motor physically installed on the Dana Dolly. ([Install guide](dana-dolly-v3-install.md))

---

## Conductor I/O Port Setting

Mount and power the Conductor SA2.6, then verify:

**Settings → Port → I/O Port → Ext. Trig**

---

## Sensor Board Wiring

1. Attach the cable to the sensor board.
2. Plug the other end into the **4-pin I/O port on the left side** of the Conductor SA2.6.
3. Both LEDs (green and red) should light up. If not, check the I/O Port setting above.

---

## Sensor Board Mounting

1. Disengage the drive wheel so you can slide the dolly manually.
2. Attach the sensor board to the DDV3 mount using the M4 screw — **finger tight only** to start.
    - Channel faces the carriage mount; wires face outward.
3. Position the board **as high as possible** on the mount while keeping it level and parallel to the track.
4. Lightly snug the screw.
5. **Check the LEDs** — they should go off when sensing the track surface (reflection). If they stay on, the board is too far from the track.
6. Slide the dolly manually along the full length of track. Both LEDs should remain **off** throughout.
7. If LEDs turn on mid-track, loosen and reposition the board slightly lower. Repeat until LEDs stay off across the full run.
8. Once correct, lightly snug the screw. **Do not overtighten** — the sensor stalk is plastic and will break. Use the short end of the wrench for less leverage.
9. Re-engage the drive wheel.

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

## Testing the Install

With everything powered up, manually slide the dolly along the track:

- **Clean track** — both LEDs should be off
- **Left stop sticker** — both LEDs (red and green) activate; dolly has 6–12 inches of additional travel before the physical end
- **Right stop sticker** — both LEDs (red and green) activate; dolly has 6–12 inches of additional travel before the physical end
- **Midpoint X marker** — green LED triggers on the back black portion, red LED on the front portion; both should clearly turn on when passing over

When all tests pass, your Dana Dolly is ready to calibrate and run its first ping-pong shot. See [Calibrating with Sensors and Running Your First Ping Pong Shot](dana-dolly-v3-calibration.md).
