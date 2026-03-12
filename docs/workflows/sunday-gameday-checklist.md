# Sunday Gameday Checklist

The Gameday Checklist is a live Google Sheet filled out each Sunday by the responsible team members. This page explains the structure of the checklist and what each section covers.

**Live checklist:** [Gameday Checklist (Google Sheets)](https://docs.google.com/spreadsheets/d/126i08rn96KLfm1jfg6yoymLCw8bCvi3qauJ3NcN1JmQ/edit){target="_blank"}

---

## How the Checklist Works

Each item has a **Responsibility** column indicating which role owns it. If you are in that role it is your job to check the box and initial the task as you complete it. All boxes must be checked before the event can start. Use the Comments column to flag anything abnormal — this creates a maintenance record for the team.

---

## Service Data

**Responsibility: CG**

Filled in after rehearsal. Records the actual runtime of each service element so the team can track pacing.

| Item | Notes |
|---|---|
| 9am Service Runtime | HH:MM:SS |
| 9am Message Runtime | HH:MM:SS |
| 11am Service Runtime | HH:MM:SS |
| 11am Message Runtime | HH:MM:SS |
| Flip Time | Time between services (MM:SS) |
| Outside Temperature | Linked lookup |
| Weather | Linked lookup |

---

## Control Flex

**Responsibility: A1, Video Engineer, Lighting**

ControlFlex is the system used to control house lights, stage curtains, power for projectors and displays, and power for the PA. See [ControlFlex System Reference](controlflex-system.md) for full details.

| Item | Responsibility |
|---|---|
| Amp Power | A1 |
| Main Projector Power (Turn on at 8:15am) | Video Engineer |
| Confidence Projector Power | Video Engineer |
| Confidence Screen Power | Video Engineer |
| Multiviewer Power | Video Engineer |
| Lighting Power | Lighting |
| House Lights are off on the keypad | Lighting |
| Keypad locked | Lighting |
| Curtain Motors functional | A1 |

---

## FOH Audio

**Responsibility: A1**

### DiGiCo SD12

| Item | Notes |
|---|---|
| Console is on | Two power switches on back right of console |
| The correct session is loaded | See [Loading a Session on the SD12](../audio/digico-sd12-loading-a-session.md) |
| Spotify Audio is working | Mac Mini on right side of console running Waves Super Rack |
| CG A Audio is working | Coordinate with video crew to play a video, confirm signal on CG A fader |
| Sound check for all VIP mics | Confirm signal and routing through PA Mix Bus and Broadcast Matrix |
| Line check for worship | Ask each band member to play; confirm line and monitor |
| Line check Organ monitor | |
| Walk-in snapshot works | Fire snapshot and confirm PA responds correctly |
| Bumper snapshot works | Fire snapshot and confirm PA responds correctly |

!!! warning "After Rehearsal"
    Before the walk-in starts, hit the **Service Reset** macro on the SD12. This macro resets a number of critical console settings that are changed during rehearsal. Missing this step is a common cause of service issues.

### PA

| Item | Notes |
|---|---|
| Main LR is working | Confirm PA on in ControlFlex, PA control group unmuted on console |
| Front Fills are working | Fed off PA processor — no individual console control; if not working, reset Venueflex Definition Processor |
| Subs are working | |
| Surrounds are working | Fed from Surround Aux on SD12 via Venueflex Definition Processor; test with Spotify to Surround Aux |
| Spaceflex is working | |

### Waves Server

| Item | Notes |
|---|---|
| Waves Server is connected to network | Check for green indicator in Waves Superrack |
| Waves is linked to the DiGiCo | Waves follows the SD12 automatically when sessions are recalled or cues fired |

### Recorders

| Item | Notes |
|---|---|
| SD Recorder is working | Denon SD recorder in FOH rack; put in record-pause mode by pressing record once — auto starts/stops at set times |
| Virtual Soundcheck is working | |

### Broadcast

| Item | Notes |
|---|---|
| Broadcast Feed works | Confirm Broadcast Wet signal is present at Bcast Wet L+R matrix outputs |
| Lobby speakers on | |

---

## Stage / Backstage

**Responsibility: Stage Crew**

| Item | Notes |
|---|---|
| Stage setup and ready for musicians | Confirm against stage plot and input list in "00 Prod Doc This Week" folder |
| Wireless mics and monitors have fresh batteries | Replace all rechargeable batteries; place removed batteries on charger (top of backstage mic cabinet) |
| Wireless mics in hooks on the appropriate side of the stage | Place mics/packs on the side of the stage the person will enter from |
| Stage TV is on and has been tested | Confirm video crew is sending signal to it |
| Stage TV cable is neatly stored | Cable must unwrap cleanly — moved onto stage by one person during service |
| Podium and/or other stage props are ready to go | Normal Sunday: podium, stool, and TV for Pastor Rick |
| Stage east and west manual curtains are in the correct orientation | If motorized curtain is open and stained glass is visible, smaller curtains behind must be fully closed |
| Backstage lights / exterior lights are turned off | |
| Stage is clear of any unnecessary paper or trash | |
| VIPs have mics and know their cues | |

---

## Lighting

**Responsibility: Lighting**

| Item | Notes |
|---|---|
| GrandMA is on | Power button upper right corner of console; generally left on |
| Correct firmware is loaded | Version shown in title bar; current version is 1.9.2.2; restart to auto-load correct version |
| GrandMA is connected to Nodes | Feeds 6 ETC Nodes via sACN over lighting VLAN; see DMX Protocols window |
| Correct Arena composition loaded | |
| Restart Arena 10 min before service | |

---

## Video

**Responsibility: Video Engineer / Graphics**

### Switcher (ATEM Constellation 8k)

| Item | Responsibility | Notes |
|---|---|---|
| Video signal from all cameras | Video Engineer | |
| CCU control is working | Video Engineer | |
| ATEM Outputs are correct | Video Engineer | See [ATEM Output Configuration](../video/atem-output-configuration.md) |
| Make sure all lower and side thirds look right when keyed | Video Engineer | Check CG A and CG B keyers via Stream Deck |
| Make sure MADI 1 is set to unity and is unmuted | Video Engineer | ATEM software → Audio tab → MADI 1 fader at +0.00, set to ON |

### Pro Presenter

| Item | Responsibility | Notes |
|---|---|---|
| All CG computer outputs working | Graphics | |
| MIDI Connected (CG A, CG B, TD) | Graphics | |
| CG A Dante running | Graphics | See [CG A Dante Virtual Soundcard](../video/cg-a-dante-virtual-soundcard.md) |
| Apply correct theme to all songs on CG B | Graphics | See [Applying ProPresenter Theme on CG B](../video/propresenter-theme-cg-b.md) |
| Check CG B Prayer time slides | Graphics | |

### Stream Deck / Companion

| Item | Responsibility | Notes |
|---|---|---|
| Companion is working | Video Engineer | |
| All sources are connected | Video Engineer | |
| All buttons are functioning | Video Engineer | |
| Confirm control is ready for rehearsal | Video Engineer | |
| Confirm walk-in countdown + preshow adds up to 15 min | Video Engineer | |

### Recorders (HyperDecks)

| Item | Responsibility | Notes |
|---|---|---|
| All decks have drives | Video Engineer | 1 drive per HyperDeck, labeled with date and HyperDeck number |
| All drives formatted | Video Engineer | HyperDeck → Menu → Format → Drive 1 → HFS+ |
| Campus getting kiosk until walk-in | Video Engineer | Set Aux 4 to BFC Kiosk |

---

## Stream

**Responsibility: Video Engineer**

### RESI

| Item | Notes |
|---|---|
| Confirm encoder inputs on Ross Dashboard | Open Ross Dashboard on ATEM Control Tier 3; confirm Out 71 [RESI 1] = In 15 [SW Out 15 - ME3]; confirm Out 72 [RESI 2] = In 48 [Hyperdeck 4] |
| Encoder scheduled | |
| Web events scheduled for both services | |
| Update the date in the "title" on web events | |
| Facebook and YouTube feeds scheduled for both services | |

### Church Online

| Item | Notes |
|---|---|
| Services scheduled | |
| Services have the correct RESI embed link | |
| Duration is set to 1 hour 20 minutes | |
| Start the video 10 minutes before the service begins | |

### Tulakes

| Item | Notes |
|---|---|
| Encoder receiving signal at 10:55 | |
| Audio is working | |
