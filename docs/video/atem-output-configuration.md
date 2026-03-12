# ATEM Output Configuration

This page documents the standard Aux output routing for the ATEM Constellation 8K and the required MADI 1 audio settings.

---

## Aux Output Routing

| Output | Source | Notes |
|---|---|---|
| Aux 1 | Confidence B | Confidence display at front of stage |
| Aux 2 | CG C | CG C graphics computer output |
| Aux 4 | BFC Kiosk | Campus kiosk feed; set to BFC Kiosk until walk-in |
| Output 13 | ME1 | Main program output |
| ME2 Outboard | ME2 | |
| ME3 Stream | ME3 | Stream output for RESI |

---

## MADI 1 Audio Setting

The MADI 1 input must be set to unity and unmuted before each service.

1. Open **ATEM Software Control**
2. Go to the **Audio** tab
3. Locate the **MADI 1** fader
4. Set the level to **+0.00** (unity)
5. Set the channel to **ON** (not AFV or OFF)

!!! warning
    If MADI 1 is muted or not set to unity, audio from the SD12 will not reach the switcher correctly. Check this during the Gameday Checklist before service.

---

## Lower Thirds / Keyers

Check that all lower thirds and side thirds render correctly when keyed before service:

- Verify **CG A** keyer via Stream Deck
- Verify **CG B** keyer via Stream Deck

See the Gameday Checklist for the full verification steps.

---

## Notes

- Aux routing should be verified as part of the [Sunday Gameday Checklist](../workflows/sunday-gameday-checklist.md)
- The ATEM Software Control application runs on ATEM Control Tier 3

