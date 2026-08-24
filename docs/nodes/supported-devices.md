# QSEN07 Device Notes

## Sensors

| Sensor | Measures |
|---|---|
| AHT20 | Temperature, relative humidity |
| BH1750 | Ambient light level in lux |
| BMx280 / BMP280 | Temperature, barometric pressure |
| SCD4x | CO2, temperature, relative humidity |
| QMI8658 | Acceleration, gyroscope motion, sensor temperature |

## Features

| BLE | SIM | WiFi | LINK | Battery | SD Card |
|---:|---:|---:|---:|---:|---:|
| ✓ | ✕ | ✓ | ✓ | ✕ | ✕ |

## Runtime

QSEN07 wakes, samples its environmental and motion sensors, publishes or relays data, then returns to sleep. It is intended to spend most of its time asleep to reduce power draw and sensor self-heating.

## Notes

- QSEN07 should use approximately 5 minute sleep intervals because excess internal heat can bias temperature and environmental readings.
- Battery telemetry is not currently exposed in firmware.
- SD card support is disabled.
- LINK refers to local relay/link transport support such as ESP-NOW.

# M5 Capsule Device Notes

## Sensors

| Sensor | Measures |
|---|---|
| IMU | Acceleration, gyroscope motion, IMU temperature, movement delta |
| Microphone | RMS, peak audio level, dBA, min/avg/max dBA, LA10, LA90 |
| Battery | Battery voltage and charge percentage |

## Features

| BLE | SIM | WiFi | LINK | Battery | SD Card |
|---:|---:|---:|---:|---:|---:|
| ✓ | ✕ | ✓ | ✓ | ✓ | ✕ |

## Runtime

M5 Capsule wakes, samples IMU, microphone, and battery data, stores or sends telemetry, then returns to sleep. It can use LittleFS-backed storage for queued telemetry when data is not sent immediately.

## Notes

- M5 Capsule includes battery voltage and percentage reporting.
- SD card support is disabled.
- LINK refers to local relay/link transport support such as ESP-NOW.