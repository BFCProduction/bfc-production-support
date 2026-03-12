# Loading a Session on the SD12

This page covers how to load a session on the DiGiCo SD12 console, including session naming conventions and the steps to load from the Master screen.

---

## Session Naming Convention

Sessions are named by date and service order using this format:

```
YYYY.MM.DD.S
```

| Part | Meaning | Example |
|---|---|---|
| YYYY | Year | 2025 |
| MM | Month (zero-padded) | 03 |
| DD | Day (zero-padded) | 16 |
| S | Service number | 1 or 2 |

**Example:** `2025.03.16.1` = March 16, 2025 — first service (9am). `2025.03.16.2` = second service (11am).

---

## Loading a Session

Sessions are loaded from the **Master screen** — the blue touchscreen on the right side of the console.

1. On the Master screen, tap **Sessions**
2. Locate the correct session file by date
3. Tap the session to select it
4. Tap **Load** to load it onto the console

!!! warning "Session Reset Before Service"
    After loading a session and completing rehearsal, run the **Service Reset** macro on the SD12 before the walk-in starts. This macro resets critical console settings that are modified during rehearsal. Skipping this step is a common cause of service issues.

---

## Notes

- The console has two power switches on the back right — both must be on
- Sessions should be created or confirmed correct during pre-service setup
- When loading the second service, load the `.2` session file — do not reuse the first-service session

