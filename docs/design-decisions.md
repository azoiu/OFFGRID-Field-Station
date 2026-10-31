# Design decisions

This page keeps the main choices in one place so I do not forget why I picked them.

## Current choices

| Part | Decision |
|---|---|
| Main computer | Raspberry Pi 5, 8 GB |
| Storage | 512 GB NVMe SSD |
| Main screen | Waveshare 8DP-CAPLCD, 8 inch |
| Radio | Heltec WiFi LoRa 32 V3, EU868 |
| GPS | u-blox M10 module; exact breakout to decide |
| Battery | Supplier-built 4S1P LiFePO4 pack, 12.8 V, 15 Ah, 192 Wh |
| Handheld | Waveshare ESP32-S3-Touch-LCD-2.8 V2 and separate Heltec LoRa V3 |
| Handheld power | Its own battery |
| Case | SINOCASE SC001, keep the same case |
| Runtime estimate | About 7–9 hours, calculation only |

## Power direction

The battery pack will use four 3.2 V 15 Ah Gotion 33140 cells, with a matched 4S LiFePO4 BMS supplied with the pack. The complete pack dimensions and BMS details are not confirmed.

The Pi and screen will have separate regulated power outputs:
- Geekworm Pi5-5V5APD for the Pi
- Pololu D24V50F5 for the screen

The main fuse target is 10 A and the main switch target is 15 A DC. Both still need to be checked against the final wiring and current.

Wall charging will use an external LiFePO4 charger. Car charging will use a programmable DC-DC charger. Both charger models and settings are still to decide after the pack supplier confirms the charge requirements.

## Still open

- Exact battery pack, BMS, connector and finished dimensions
- Wall and car charger models, charge settings and charge input wiring
- Exact GPS breakout board and interface
- UART pins
- Final case layout, including keyboard placement
- Final KiCad schematic and PCB

## Important

The current KiCad drawing is a planning drawing. It is not a finished circuit. I have not made or tested a power PCB.
