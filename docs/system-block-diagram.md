# How the parts connect

This is a simple drawing of how I think the system will work. Some parts are still not chosen.

## Main station

```mermaid
flowchart TB
    BAT["12.8 V LiFePO4 (candidate only)"]
    BMS["4S BMS"]
    FUSE["Fuse and switch"]
    PWR["Power distribution"]
    PI5V["5.1 V converter for Pi"]
    LCD5V["5 V converter for screen"]
    PI["Raspberry Pi 5"]
    SSD["512 GB SSD"]
    LCD["Waveshare 8DP-CAPLCD"]
    GPS["GPS module"]
    LORA["Heltec LoRa"]

    BAT --> BMS --> FUSE --> PWR
    PWR --> PI5V --> PI
    PWR --> LCD5V --> LCD
    PI --- SSD
    PI <-->|"HDMI + USB touch"| LCD
    PI <-->|"GPS data"| GPS
    PI <-->|"UART"| LORA
```

## Handheld

```mermaid
flowchart TB
    HBAT["Separate handheld battery"]
    WAVE["Waveshare ESP32-S3 screen"]
    LORA["Heltec LoRa"]
    MAIN["Main station LoRa"]

    HBAT --> WAVE
    HBAT --> LORA
    WAVE <-->|"UART"| LORA
    LORA <-->|"LoRa radio"| MAIN
```

## What it should do

- The Pi is the main computer.
- GPS gives the station its position.
- LoRa is for sending text messages to the handheld.
- The handheld has its own battery.
- Offline maps, files and local AI should run on the Pi.

RTL-SDR and separate GPS trackers are not part of the first version.

## Not decided yet

- Exact battery pack and BMS
- Power converters and charger models
- Fuse, switch and wire sizes
- Exact GPS breakout board supply
- Exact Pi and Heltec UART pins
- Final case layout

This is only the basic plan, not the final wiring. I still need to draw the real circuit in KiCad.
