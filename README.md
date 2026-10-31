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

The current battery design target is a supplier-built 4S1P LiFePO4 pack using four 3.2 V 15 Ah Gotion 33140 cells. This gives 12.8 V, 15 Ah and 192 Wh. The cell-only arrangement is about 140 × 133 × 33.2 mm. The complete pack will be larger and its dimensions are not confirmed.

The Pi power module is Geekworm Pi5-5V5APD and the screen converter is Pololu D24V50F5. The Geekworm output voltage needs to be checked carefully: its published test shows 4.987 V at 5 A without the boost jumper and 5.127 V at 5 A with it. The jumper also raises the no-load voltage. This needs a real load test before final selection.

The first runtime estimate is about 8–10 hours, depending on load. This is only a calculation, not a measured result. Chargers are not selected until the battery supplier confirms the charge profile.

## Maybe later

RTL-SDR and separate GPS trackers are ideas for another version. They are not included in V1.
