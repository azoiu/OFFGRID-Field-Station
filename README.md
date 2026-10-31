# OFFGRID

**Status: design stage. Nothing is built or tested yet.**

OFFGRID is a computer in a hard case. I want to use it outside, also where there is no internet or phone signal.

**Scope:** V1 includes a Raspberry Pi 5 cyberdeck with local files and AI, offline maps of Slovenia, GPS, LoRa messaging and a LiFePO4 battery.

## What I want to put in it

- Raspberry Pi 5 with 8 GB RAM
- 512 GB NVMe SSD
- Waveshare 8-inch touchscreen (8DP-CAPLCD)
- GPS and offline maps of Slovenia
- LoRa for sending text messages
- A small handheld device with its own battery
- Local files and local AI
- LiFePO4 battery

I already have the case, keyboard and 3D printer.

## Case

The case is a SINOCASE SC001 from Temu. The approximate inside dimensions are about 250 × 185 × 55 mm. The usable space can be smaller because of ribs, hinges and screw posts.

I don't want a bigger case, so the parts have to fit in this one. The screen should go in the lid.

## Files

- [Parts and power choices](docs/BOM.md)
- [Basic system drawing](docs/system-block-diagram.md)
- [Wiring notes](docs/electrical-design.md)
- [Power budget](docs/power-budget.md)
- [Battery pack specification](docs/battery-pack-spec.md)
- [Battery and charging plan](docs/battery-and-charging.md)
- [Power test plan](docs/power-test-plan.md)
- [Case fit notes](docs/case-fit.md)
- [Software plan](docs/software-plan.md)
- [Work log](docs/work-log.md)
- [KiCad power overview](hardware/power-overview/README.md)

## Current power design

The current battery design target is a supplier-built 4S1P LiFePO4 pack using four 3.2 V 15 Ah Gotion 33140 cells. This gives 12.8 V, 15 Ah and 192 Wh. The cell-only arrangement is about 140 × 133 × 33.2 mm. The complete pack will be larger and its dimensions are not confirmed.

The Pi power module is Geekworm Pi5-5V5APD and the screen converter is Pololu D24V50F5. The Geekworm output voltage needs to be checked carefully before use.

The runtime estimate is about **7–9 hours**, depending on load. This is a calculation, not measured runtime. With local AI running, the average load may be about 19 W or more, giving about 7 hours or less. Chargers are not selected until the battery supplier confirms the charge profile.

## Open questions

- Exact battery pack, BMS, connector and finished dimensions
- Wall and car chargers and their settings
- Exact GPS breakout board
- UART pins
- Final case layout
- Keyboard placement in the case is not decided yet
- Cooling and closed-case temperatures
- Real runtime and power measurements

## Maybe later

RTL-SDR and separate GPS trackers are ideas for another version. They are not included in V1.
