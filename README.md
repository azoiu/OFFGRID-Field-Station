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
- [Battery pack proposal](docs/battery-pack-spec.md)
- [Power test plan](docs/power-test-plan.md)
- [Design decisions](docs/design-decisions.md)
- [Case fit notes](docs/case-fit.md)
- [Work log](docs/work-log.md)
- [KiCad power overview](hardware/power-overview/README.md)

## Current state

The first battery design I want to ask a supplier about is a **4S4P LiFePO4 pack, 12.8 V and 24 Ah**. It would use sixteen 32700 cells. The cell layout looks possible on paper, but the final pack dimensions including BMS and insulation are not confirmed.

I have added an editable KiCad power overview. It is a block diagram for planning, not a finished electrical schematic or PCB. Exact converters, fuses, connectors and wiring still need to be selected.

The goal is about 10 hours of use. This is only an estimate until I build the system and test it.

## Maybe later

RTL-SDR and separate GPS trackers are ideas for another version. They are not included in V1.
