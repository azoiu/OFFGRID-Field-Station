# OFFGRID – system block diagram

This is the first version of the system layout. It shows the main parts and how data and power should move between them. Some exact modules and connectors are still to be chosen.

## Main station

```mermaid
flowchart TB
    BAT["LiFePO4 battery pack<br/>voltage and capacity TBD"]
    BMS["Battery BMS"]
    FUSE["Main fuse and switch"]
    PWR["Power PCB<br/>protection and DC/DC converters"]
    PI["Raspberry Pi 5<br/>main computer"]
    SSD["512 GB NVMe SSD"]
    DISP["8-inch touchscreen"]
    GPS["u-blox M10 GNSS"]
    LORA["Heltec LoRa 32 V3<br/>EU868"]
    BAT --> BMS --> FUSE --> PWR
    PWR -->|"5.1 V, high-current rail"| PI
    PWR -->|"display supply<br/>voltage/current TBD"| DISP
    PI --- SSD
    PI <-->|"USB touch"| DISP
    PI <-->|"UART / USB (to decide)"| GPS
    PI <-->|"UART (pins TBD)"| LORA
```

## Handheld terminal

```mermaid
flowchart TB
    HMI["Waveshare ESP32-S3<br/>touchscreen terminal"]
    HLORA["Heltec LoRa 32 V3<br/>EU868"]
    HBAT["Handheld battery<br/>and suitable charging/power circuit"]
    HBAT --> HMI
    HBAT --> HLORA
    HMI <-->|"UART, 3.3 V logic"| HLORA
    HLORA <-->|"LoRa radio link"| MAIN["Main station LoRa"]
```

## What it does

- The Raspberry Pi is the main computer. It runs the offline maps, local document search and local AI.
- The GPS module provides the position of the station.
- The main LoRa board sends and receives text messages with the handheld terminal.
- The handheld has its own screen and controls. It does not need a phone or internet connection.
- Separate GPS trackers and RTL-SDR are not part of V1. They may be added in a later version.

## Still to decide

- Exact LiFePO4 battery voltage, capacity, BMS and physical dimensions.
- The DC/DC converter or power module for the Pi 5.
- The correct supply for the 8-inch screen.
- Exact UART pins and connector types for the LoRa and GPS boards.
- The handheld battery and charging circuit.

This is a system diagram, not a finished wiring plan. The exact electrical connections will be checked in the next document and then drawn in KiCad.
