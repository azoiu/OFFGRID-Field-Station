# How the parts connect

This is a simple drawing of how I think the system will work. Some parts are still not chosen.

## Main station

```mermaid
flowchart TB
    BAT["LiFePO4 battery"]
    BMS["BMS"]
    FUSE["Fuse and switch"]
    PWR["Power board"]
    PI["Raspberry Pi 5"]
    SSD["512 GB SSD"]
    LCD["8-inch screen"]
    GPS["GPS module"]
    LORA["Heltec LoRa"]

    BAT --> BMS --> FUSE --> PWR
    PWR --> PI
    PWR --> LCD
    PI --- SSD
    PI <-->|"HDMI + USB touch"| LCD
    PI <-->|"GPS data"| GPS
    PI <-->|"UART"| LORA
```

## Handheld

```mermaid
flowchart TB
    BAT["Handheld battery"]
    WAVE["Waveshare ESP32-S3 screen"]
    LORA["Heltec LoRa"]
    MAIN["Main station LoRa"]

    BAT --> WAVE
    BAT --> LORA
    WAVE <-->|"UART"| LORA
    LORA <-->|"LoRa radio"| MAIN
```

## What it should do

- The Pi is the main computer.
- GPS gives the station its position.
- LoRa is for sending text messages to the handheld.
- The handheld has its own screen and buttons.
- Offline maps, files and local AI should run on the Pi.

RTL-SDR and separate GPS trackers are not part of the first version.

## Not decided yet

- Exact battery and BMS
- Power converters
- Screen power supply
- Exact pins and connectors

This is only the basic plan, not the final wiring. I still need to draw the real circuit in KiCad.
