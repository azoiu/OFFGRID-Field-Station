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

The case is a SINOCASE SC001 from Temu. The inside is listed as 255 × 190 × 85 mm. I measured about 5.8 cm usable space in the bottom part.

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
- [Work log](docs/work-log.md)
- [KiCad power overview](hardware/power-overview/README.md)

## Current power design

The selected design target is a supplier-made 4S1P LiFePO4 pouch pack, 12.8 V and 25 Ah (320 Wh). The pack must fit within 245 × 175 × 45 mm and include a matched BMS. This is a specification to send to a battery supplier, not a battery already purchased.

The Pi uses a Geekworm Pi5-5V5APD module. The screen uses a Pololu D24V50F5 converter. Exact battery connector and final fuse sizing still need verification.

The goal is about 10 hours of use. This is an estimate until I build and test it.

## Maybe later

RTL-SDR and separate GPS trackers are ideas for another version. They are not included in V1.
