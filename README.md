# OFFGRID

OFFGRID is a computer in a hard case. I want to use it outside, also where there is no internet or phone signal.

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

The case is a SINOCASE SC001 from Temu. The inside is listed as 255 × 190 × 85 mm. I measured about 5.8 cm of usable space in the bottom part.

I don't want a bigger case, so the parts have to fit in this one. The screen should go in the lid.

## Files

- [Parts and prices](BOM.csv)
- [More parts notes](docs/BOM.md)
- [Basic system drawing](docs/system-block-diagram.md)
- [Wiring notes](docs/electrical-design.md)
- [Power budget](docs/power-budget.md)
- [Battery and charging plan](docs/battery-and-charging.md)
- [Power test plan](docs/power-test-plan.md)
- [Design decisions](docs/design-decisions.md)

## Current state

I checked the main power requirements and made a first estimate. The rough load is around 11–19 W, with 15 W used for the first battery calculation.

A 12.8 V 20 Ah LiFePO4 pack is a possible starting point. I have not selected or bought it because the dimensions still need to be checked against the case.

The goal is about 10 hours of use. This is only an estimate until I build the system and test it.

## Maybe later

RTL-SDR and separate GPS trackers are ideas for another version. They are not included in V1.
