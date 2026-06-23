# Apollo CAST-1 WizMote

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FApolloAutomation%2FBlueprints%2Fblob%2Fmain%2FCAST-1%2FCAST-1-WizMote.yaml)

Make your WizMote control the **Apollo Automation CAST-1** exactly how you want. Assign any of the nine WizMote buttons to media playback controls, a light toggle, or a custom Home Assistant action.

---

## Features

- 🎵 Every button ships with a sensible default (Play, Pause, Volume, Next, Previous) — override any of them by picking another option from its dropdown
- 🏠 Set a button to **Send HA Event** to run a custom action instead — play a Music Assistant playlist, toggle a room's lights, run a scene or script, anything HA can do
- 🔄 Your picks are written down to the CAST-1's per-button selects on HA start and on save, so the device page always mirrors this automation — no need to open the device page

### Per-button Actions

Each button offers the same dropdown:

```
Nothing · Play · Pause · Play / Pause · Next Track · Previous Track ·
Volume Up · Volume Down · Toggle Light · Send HA Event
```

| Button | Default |
|---|---|
| On | Play |
| Off | Pause |
| Night | Toggle Light |
| Brightness Up | Volume Up |
| Brightness Down | Volume Down |
| Button 1 | Previous Track |
| Button 2 | Next Track |
| Button 3 | Send HA Event |
| Button 4 | Send HA Event |

---

## Requirements

- **Apollo Automation CAST-1** (`CAST-1-W` or `CAST-1-ETH`) connected to Home Assistant via ESPHome, paired with a WizMote
- CAST-1 firmware with WizMote Home Assistant control (the per-button selects + `cast1_wizmote_event`)

---

## Setup

1. Click the **Import Blueprint** badge above, or copy the URL and paste it into
   **Settings → Automations & Scenes → Blueprints → Import Blueprint**

2. Create a new automation from the blueprint

3. **Select your CAST-1 device** from the dropdown

4. Expand each button you want to change and pick an **Action** from its dropdown

5. For any button set to **Send HA Event**, expand it and fill in the **Custom action** (TTS, lights, scenes, scripts…)

---

## Resources

- [CAST-1 Product Page](https://apolloautomation.com)
- [CAST-1 Wiki & Documentation](https://wiki.apolloautomation.com)
- [Apollo Automation Discord](http://dsc.gg/ApolloAutomation)
- [GitHub — CAST-1 Firmware](https://github.com/ApolloAutomation/CAST-1)
- [Apollo Automation Blueprints](https://github.com/ApolloAutomation/Blueprints)
