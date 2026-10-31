# How the parts connect

This is the current V1 system plan. The exact battery pack, BMS and some connections still need confirmation.

## Main station

```mermaid
flowchart TB
    BAT["4S1P LiFePO4 12.8 V 15 Ah"] --> BMS["Matched 4S LiFePO4 BMS"]
    BMS --> FUSE["10 A fuse (to verify)"]
    FUSE --> SW["15 A DC main switch"]
    SW --> BUS["12.8 V DC distribution"]
    BUS --> PI_PWR["Geekworm Pi5-5V5APD"]
    PI_PWR --> PI["Raspberry Pi 5"]
    BUS --> LCD_PWR["Pololu D24V50F5"]
    LCD_PWR --> LCD["Waveshare 8DP-CAPLCD"]
    PI --- SSD["512 GB NVMe SSD"]
    PI <-->|"HDMI + USB touch"| LCD
    PI <-->|"GPS data"| GPS["u-blox M10 GPS"]
    PI <-->|"UART"| LORA["Heltec WiFi LoRa 32 V3 EU868"]
    PI -.->|"USB power or fused 5 V branch"| GPS
    PI -.->|"USB power or fused 5 V branch"| LORA
```

The screen gets its 5 V supply from the Pololu converter. The Pi gets power from the Geekworm module. I still need to check that the screen's USB touch connection does not join the Pi's 5 V line to the Pololu 5 V output.

## Handheld

```mermaid
flowchart TB
    HBAT["Separate handheld battery"] --> WAVE["Waveshare ESP32-S3-Touch-LCD-2.8 V2"]
    HBAT --> LORA_H["Heltec WiFi LoRa 32 V3 EU868"]
    WAVE <-->|"UART"| LORA_H
    LORA_H <-->|"LoRa radio"| LORA_M["Main station Heltec"]
```

## What it should do

- The Pi is the main computer.
- GPS gives the station its position.
- LoRa is for sending text messages to the handheld.
- The handheld has its own battery.
- Offline maps, files and local AI should run on the Pi.
- RTL-SDR and separate GPS trackers are not part of the first version.

## Not decided yet

- Exact supplier-built battery pack, BMS and battery connector
- Wall and car chargers, including charge input connector and protection
- Exact GPS breakout board
- UART pins
- Final case layout

This is only the basic plan, not the final wiring. I still need to draw the real circuit in KiCad and run ERC/DRC before making a PCB.
