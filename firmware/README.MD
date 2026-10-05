# Common Smart Vent Configuration

The Common directory contains the shared ESPHome configuration used by the smart vent devices.

## `yet-another-smart-vent-base.yaml`

This file contains the common configuration for the smart vent, including:

- Servo configuration
- Servo movement range
- Vent open and close scripts
- 25%, 50%, and 75% vent positions
- Home Assistant cover entity
- Position control
- Command lockout
- Servo auto-detach
- Startup behavior

Instead of duplicating this configuration in every vent's ESPHome YAML file, each vent can include this common configuration as a package.

## Installation

Place:

`yet-another-smart-vent-base.yaml`

in your ESPHome configuration directory at:

`esphome/common/`

Your ESPHome directory should look similar to:

```text
esphome/
├── common/
│   └── yet-another-smart-vent-base.yaml
│
├── dining-vent.yaml
├── kitchen-vent.yaml
└── bedroom-vent.yaml
```

> **Important:** The file must be located in the `esphome/common/` directory if you use the package path shown in the examples in this repository.

## Using the Common Configuration

Your individual vent configuration can include the shared configuration using ESPHome packages.

Example:

```yaml
packages:
  vent_base: !include
    file: common/yet-another-smart-vent-base.yaml
    vars:
      servo_transition_length: 7s
      command_lockout: 5s
```

The individual vent YAML can then contain the device-specific configuration such as:

- Device name
- Friendly name
- Wi-Fi configuration
- API configuration
- OTA configuration
- Substitutions or package variables

while the common file handles the actual vent behavior.

## Servo Positions

The current configuration uses the following servo positions:

| Vent Position | Servo Level |
|---|---:|
| 100% Open | 0% |
| 75% Open | -20% |
| 50% Open | -40% |
| 25% Open | -60% |
| Closed | -80% |

Home Assistant still sees the vent as a normal **0–100% damper**. The common configuration translates that requested position into the appropriate servo position.

## Servo Calibration

Servo and vent geometry can vary slightly between builds.

Before final assembly, use the servo-centering utility included with this project to position the servo correctly and verify the mechanical range of the vent.

Do not force the servo beyond the physical limits of the vent mechanism.

---

**Learn it. Build it. Put it into practice.**

*Purpose in Practice*
