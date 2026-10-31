# Design decisions

This page keeps the main choices in one place so I do not forget why I picked them.

## Current choices

| Part | Decision |
|---|---|
| Main computer | Raspberry Pi 5, 8 GB |
| Storage | 512 GB NVMe SSD |
| Main screen | Waveshare 8DP-CAPLCD, 8 inch |
| Radio | Heltec WiFi LoRa 32 V3, EU868 |
| GPS | u-blox M10 module |
| Battery chemistry | LiFePO4 |
| Handheld | Waveshare ESP32-S3-Touch-LCD-2.8 V2 and separate Heltec LoRa V3 |
| Handheld power | Its own battery |
| Case | SINOCASE SC001, keep the same case |
| Runtime goal | Around 10 hours |

## Power direction

The first battery size to check is 12.8 V, 20 Ah LiFePO4. This is only a candidate until its dimensions, BMS and price are checked.

The Pi and screen will have separate regulated power outputs.

Wall charging will use an external LiFePO4 charger. Car charging will use a suitable DC-DC charger.

## Still open

- Exact battery pack and dimensions
- Exact BMS and charger
- DC/DC converter models
- Fuse, switch, wire and connector ratings
- Exact GPS breakout board voltage
- Exact SSD model and power use
- Final case layout
- Final KiCad schematic and PCB

## Important

The current drawings are planning drawings. They are not a finished circuit. I have not made or tested a power PCB yet.
