# Arena Service Bumper — Auto-Start ProPresenter Timer

## Overview

| | |
|---|---|
| **Trigger** | Resolume Arena — Service Bumper clip active (Layer 11, Column 2) |
| **Action** | ProPresenter Clock 10 starts automatically |
| **Timer Name** | Arena - Service Bumper Timer |
| **System** | Bitfocus Companion |

---

## How It Works

When the service bumper starts playing in Resolume Arena, Bitfocus Companion detects the active clip and automatically starts a countdown timer in ProPresenter on CG A. This means the timer does not need to be started manually — it fires the moment the bumper goes live.

**Signal chain:**

1. Operator triggers the service bumper in Resolume Arena (FOH_Arena — Layer 11, Column 2)
2. Companion detects the clip via the `FOH_Arena` connection
3. Companion fires the **CG_A_PP7: Start Clock** action (Clock Number 10)
4. ProPresenter on CG A starts the **Arena - Service Bumper Timer** countdown

---

## Before Playing the Bumper — Set the Timer Duration

The timer duration must be set manually in ProPresenter to match the length of the specific bumper video. This will be different for each bumper.

- [ ] Get the exact duration of the bumper video
- [ ] In ProPresenter on CG A, open the **Clocks** panel
- [ ] Find **Arena - Service Bumper Timer** (Clock 10)
- [ ] Set the countdown duration to match the video length
- [ ] Confirm the timer is ready before going live

If the timer duration is wrong, it will either expire before the bumper ends or continue running after it finishes.

---

## Companion Trigger Reference

The trigger is configured in Companion under **Triggers → Arena/Service Bumper to CG A Timer**.

| Field | Value |
|---|---|
| **Trigger name** | Arena/Service Bumper to CG A Timer |
| **Event** | On condition becoming true |
| **Connection (condition)** | FOH_Arena |
| **Condition type** | Selected Clip |
| **Layer** | 11 |
| **Column** | 2 |
| **Connection (action)** | CG_A_PP7 |
| **Action** | Start Clock |
| **Clock Number** | 10 |

To view or edit: open Companion at [10.1.60.135:8888](http://10.1.60.135:8888) → **Triggers** → select **Arena/Service Bumper to CG A Timer**.

---

## Verifying It's Working

- [ ] Confirm the `FOH_Arena` connection in Companion is **green** (Connections page)
- [ ] Confirm the `CG_A_PP7` connection in Companion is **green**
- [ ] Confirm the trigger is **enabled** (toggle is on in the Triggers list)
- [ ] Trigger the service bumper in Arena — the **Arena - Service Bumper Timer** in ProPresenter should start counting down automatically within a second or two

---

## If the Timer Doesn't Start

- Check that `FOH_Arena` connection is active and not in error state
- Check that `CG_A_PP7` connection is active
- Confirm the bumper clip is on the correct layer and column (Layer 11, Column 2) — if the Arena composition has been modified, the clip position may have shifted
- Verify the trigger is enabled in Companion (Triggers page)
- As a fallback, start the **Arena - Service Bumper Timer** manually in ProPresenter via the Clocks panel

---

## Notes

- CG A, CG B, and CG C are the three main graphics playback computers — this automation runs specifically through CG A
- The ProPresenter slides in the Companion-controlled section include labels for Pre-Show, Service Bumper, and Message Bumper — do not move or delete these slides as Companion relies on their position
- This timer runs independently of the Pre-Show Countdown and other timers in ProPresenter
