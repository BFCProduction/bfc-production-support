---
type: knowledge-base
area: BFC Production
tags: [arena, resolume, companion, pro-presenter, service-bumper, blackmagic, NDI, workflow]
created: 2026-03-16
updated: 2026-03-16
---

# Service Bumper — Arena Playback & Timer System

## Overview

The service bumper is a video countdown played from Resolume Arena at the start of each service. It outputs via SDI through a Blackmagic Decklink card into the video router, then to the ATEM. A synchronized timer runs on the back screen (CG A / stage display in Pro Presenter), triggered automatically by Bitfocus Companion when the bumper fires.

---

## Signal Flow

```
Resolume Arena (Mac Studio M2 Max)
    └── Advanced Output → SDI out via Blackmagic Decklink
        └── Video Router
            └── ATEM (routed to house screens / broadcast)
```

**Back screen / stage display:**
```
Companion (watching Arena slot)
    └── Trigger → Pro Presenter (CG A)
        └── Starts countdown clock on stage display
```

---

## The NDI Problem (Resolved 2026-03-16)

### What Was Happening
Audio dropouts and video stuttering on the service bumper, reproducible across multiple formats (DXV, H.264, etc.). Other Arena clips played without issue.

### Root Cause
The Advanced Output in Arena had two active outputs:
1. SDI via Blackmagic Decklink (to router/ATEM)
2. NDI output to Pro Presenter (CG A) — for embedding the video in the stage display

The combination of Decklink SDI output + NDI output was pegging the Mac Studio M2 Max CPU/GPU. Under that load, Arena was dropping audio frames during playback of the service bumper specifically (likely due to its length or codec demands vs. shorter clips).

### Fix
Deleted the NDI output from Arena's Advanced Output settings entirely. With only the Decklink SDI output active, the system ran clean. Tested back-to-back 6 times (3 per service) with zero audio dropouts or stuttering.

### Trade-off
Without the NDI feed, the bumper video no longer appears on the back screen / stage display. This is acceptable because the timer (see below) is more useful to the team on the back screen than the video itself.

If the video on the back screen is ever needed, it can be routed from the Arena output through the ATEM to the rear screen.

---

## Timer Trigger Workflow

Instead of showing the bumper video on the back screen, a countdown timer runs in Pro Presenter on CG A, triggered automatically when the bumper fires in Arena.

### How It Works

1. **Companion** is configured with a trigger that watches a specific Arena slot (defined by layer number and column number where the service bumper lives).
2. When that slot becomes active, Companion sends a command to **Pro Presenter (CG A)** to start a specific countdown clock.
3. The clock runs on the stage display, visible to the team on the back screen.

### Setup Requirements

- The Companion trigger must reference the correct Arena layer and column. If the bumper is ever moved to a different slot in the Arena composition, the trigger must be updated.
- The Pro Presenter clock must be set to match the runtime of the service bumper video. **This must be updated any time the bumper video changes.**

### Maintenance Note

The bumper video changes a few times per year (seasonal updates, series changes, etc.). Any time it changes:

- [ ] Update the clock duration in Pro Presenter to match the new video runtime
- [ ] Verify the Companion trigger still references the correct Arena slot
- [ ] Run a back-to-back test before the service (3 fires minimum)

---

## Lessons Learned

- Arena Advanced Output with simultaneous Decklink SDI + NDI can max out the Mac Studio M2 Max under certain playback conditions. If performance issues appear in the future, check active Advanced Outputs first.
- The timer-on-back-screen approach is more practical than video-on-back-screen for the team. The countdown gives clear cue timing; the video doesn't add value in that position.
- Test the bumper in live conditions, not just pre-service checks. The issue consistently reproduced in service but not during testing — the load difference under full system operation is real.
