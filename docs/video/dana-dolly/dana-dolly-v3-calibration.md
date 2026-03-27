# Dana Dolly V3 Beltless — Calibrating with Sensors and Running Your First Ping Pong Shot

*Source: [eMotimo Support](https://support.emotimo.com/hc/en-us/articles/37146979454349)*

This is the final step after physical install and sensor setup. It covers teaching the controller where the midpoint marker is, then running a ping-pong interview shot.

---

## Prerequisites

- [ ] Firmware updated on your Spectrum ST4 or Conductor SA2.6 — see [Firmware](dana-dolly-v3-firmware.md)
- [ ] Sensor board installed and verified (LEDs off on clean track, LEDs on over stickers) — see [Spectrum sensor setup](dana-dolly-v3-spectrum-sensor.md) or [Conductor sensor setup](dana-dolly-v3-conductor-sensor.md)
- [ ] I/O Port set to **Ext. Trig** in Settings
- [ ] Drive wheel fully engaged
- [ ] Sensor board powered (Spectrum ST4 users: sensor board requires USB power)

---

## Step 1 — Teach the Midpoint

In **Live Motion**, use the remote to drive the Dana Dolly slowly (about 1 inch per second) **over and back across the midpoint sensor sticker**.

This registers the marker location in the controller's memory.

---

## Step 2 — Set Up an Interview Monster Shot

Return to the **Guided Menu** and configure an Interview Monster shot.

- Set your **Start** and **End Points** so the move **spans the midpoint marker** — the controller must pass over that sticker during every pass to maintain calibration.

---

## Step 3 — Run It

Start the shot and observe:

- When the dolly reaches the end of a pass and there is a measured position error, it will **automatically correct** before resuming the move in the opposite direction.

---

## Troubleshooting

**Corrections larger than a few mm (or ¼") on every pass:**
Check the spring force holding the drive wheel against the track. If there's very little pressure, the wheel is slipping.

**Lots of slipping and no obvious cause:**
Confirm the drive wheel is actually engaged. Review [Engaging and Disengaging the Motor](dana-dolly-v3-motor-engage.md).
