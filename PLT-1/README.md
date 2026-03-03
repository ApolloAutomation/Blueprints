# Apollo PLT-1 Plant Sensor Alerts

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FApolloAutomation%2FBlueprints%2Fblob%2Fmain%2FPLT-1%2FPLT-1.yaml)

Receive mobile push notifications and trigger custom actions when your **Apollo Automation PLT-1** or **PLT-1B** plant sensor detects conditions outside your configured thresholds.

---

## Supported Sensors

| Sensor | Alert Types | Default Thresholds |
|---|---|---|
| Soil Moisture | Low (needs watering) / High (overwatered) | 20% – 80% |
| Soil Temperature | Too cold / Too hot | 10°C – 30°C |
| Air Temperature | Too cold / Too hot | 15°C – 32°C |
| Air Humidity | Too dry / Too humid | 30% – 80% |
| Light Intensity | Too dark / Too bright | 100 – 50,000 lux |
| UV Index | Too high | > 6 |
| Battery Level | Low *(PLT-1B only)* | < 20% |

Each sensor group is **disabled by default** (except Soil Moisture) so you can monitor only what matters for your plants.

---

## Requirements

- **Apollo Automation PLT-1 or PLT-1B** connected to Home Assistant via ESPHome
- Home Assistant **2024.6.0** or newer
- Home Assistant Companion App installed on your phone *(for mobile push notifications)*

---

## Setup

1. Click the **Import Blueprint** badge above, or copy the URL and paste it into
   **Settings → Automations & Scenes → Blueprints → Import Blueprint**

2. Create a new automation from the blueprint

3. **Select your PLT-1 device** from the dropdown — the blueprint automatically finds all sensor entities

4. Enter your **plant's name** (appears in notification messages)

5. Select your **mobile device** for push notifications (optional — you can use a Custom Action instead)

6. Expand the sensor groups you want to monitor, enable them, and adjust the thresholds to suit your plant

7. *(Optional)* Expand **Repeat Alerts** to configure how often you get reminded while a condition persists

---

## Input Reference

### Device

| Input | Description | Default |
|---|---|---|
| PLT-1 Device | Your PLT-1 or PLT-1B device | — |
| Plant Name | Used in notification messages | `My Plant` |

### Notifications

| Input | Description | Default |
|---|---|---|
| Notify Device | Mobile device (Companion App) | *(optional)* |
| Interruption Level | iOS notification urgency | `active` |
| Android Options | High priority, sticky, or channel | *(optional)* |
| Custom Action | Any HA action (TTS, lights, email…) | *(optional)* |

### Repeat Alerts

| Input | Description | Default |
|---|---|---|
| Repeat — Hours | How often to re-alert while condition persists | Every Hour |
| Repeat — Minutes | Minute offset for repeat schedule | At :01 |

Set **Hours** to `Never (disable repeat)` to receive only one alert per threshold crossing.

### Per-Sensor Inputs

Each sensor group (Soil Moisture, Soil Temperature, Air Temperature, Air Humidity, Light Intensity, UV Index, Battery) shares the same pattern:

| Input | Description |
|---|---|
| Enable Alerts | Toggle — enable or disable this sensor group |
| Minimum threshold | Alert when value drops below this level |
| Maximum threshold | Alert when value rises above this level *(where applicable)* |
| Alert Delay (minutes) | How long the condition must persist before firing — prevents false alerts |

---

## Alert Behaviour

- **Immediate alert**: fires as soon as the threshold is exceeded for the configured delay duration
- **Repeat alert**: the repeat schedule re-sends the alert while the condition persists
- **Deduplication**: the automation is set to `parallel` mode, so multiple sensors can alert simultaneously without blocking each other

---

## Compatible Devices

| Model | Wired/Battery | Battery Alerts |
|---|---|---|
| PLT-1 | Wired (USB) | Not applicable |
| PLT-1B | Battery (Li-ion) | Yes — enable in **Battery** section |

---

## Resources

- [PLT-1 Product Page](https://apolloautomation.com)
- [PLT-1 Wiki & Documentation](https://wiki.apolloautomation.com)
- [Apollo Automation Discord](https://apolloautomation.com/discord)
- [GitHub — PLT-1 Firmware](https://github.com/ApolloAutomation/PLT-1)
- [Apollo Automation Blueprints](https://github.com/ApolloAutomation/Blueprints)
