---
title: "Tapo Vacuum in H.A."
image: /assets/projects/vacuumcard-adv.png
order: 4
---
I needed to integrate my robot vacuum into Home Assistant, so I forked [epg-pers/tapo-rv30-ha](https://github.com/epg-pers/tapo-rv30-ha) and made:
[jan-tdy/TapoVac-ADV](https://github.com/jan-tdy/TapoVac-ADV)

Features:
- Full vacuum control — start, pause, stop, dock, **spot clean** (`vacuum.clean_spot`)
- **Native room cleaning, across every saved map/floor** — the vacuum's more-info dialog lets you map its rooms to Home Assistant areas and clean them with the standard `vacuum.clean_area` action (Home Assistant 2026.3+, see below); rooms from multiple saved maps show up grouped by floor in the mapping dialog
- **Room-by-room cleaning** via `tapo_rv30.clean_rooms` service
- Live colour **map image** rendered from LZ4 pixel data
- Fan speed selection (Quiet / Standard / Turbo / Max / Ultra)
- Water level select (Off / Low / Medium / High)
- Clean passes select (1 / 2 / 3)
- Battery sensor
- Mop pad attached binary sensor - Clean progress sensor (`%`, proper `native_unit_of_measurement` — usable directly in Tile cards etc. without hacking a literal `%` into `state_content`)
- **Current Room sensor** — which room the vacuum is currently in, inferred locally from its position against the map's room geometry (no extra device call). Reads `unknown` when the vacuum isn't inside a mapped room (e.g. a hallway), and updates at the same cadence as the map image.
- Error state sensor (e.g. "Ok", "Dust Bin Removed", "Trapped")
- Consumable wear sensors (main brush, side brush, filter, sensor, charge contacts)
- **Schedules sensor** — view of the schedules you've saved in the Tapo app (time, repeat days, rooms, clean settings), decoded from `get_schedule_rules` (credit: [peggleg/tapo-rv30](https://github.com/peggleg/tapo-rv30), who discovered this call — see [Protocol notes — schedules](#protocol-notes-schedules) below)
- **Run a saved schedule on demand** via `tapo_rv30.run_schedule` — no device call to trigger a schedule by ID is known to exist, so this reads the schedule's settings and replays them through the same room-cleaning calls, right now instead of waiting for its own time (see [Protocol notes — schedules](#protocol-notes-schedules))
- **`vacuum.send_command`** — raw passthrough to any device method (e.g. `command: getConsumablesInfo`), for calling anything this integration doesn't have a dedicated action for yet. Response is logged at info level on the `custom_components.tapo_rv30` logger.
- **Repair issue on room changes** — if the currently active map's rooms no longer match what you last mapped to Home Assistant areas (renamed, added, removed), Home Assistant raises a repair issue pointing back at the mapping dialog instead of silently leaving stale area mappings.
- Config flow UI — set up from Settings → Devices & Services
- Fixed: resuming after a pause now actually resumes (the upstream `start()` re-sent the same `setSwitchClean` call, which the device silently ignores while already `clean_on: true`) 

## Card
UI-editable through Home Assistant's own card editor (YAML still available too). A live map with configurable **rotation**, click-to-select rooms for targeted cleaning, **furniture** placed and calibrated directly on the map, **multi-floor** awareness, and start/pause/stop/return-to-dock controls.

**Repository:** [jan-tdy/VacuumCard-ADV](https://github.com/jan-tdy/VacuumCard-ADV)
