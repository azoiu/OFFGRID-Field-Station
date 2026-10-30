# OFFGRID

OFFGRID is a portable computer in a rugged case. It is designed for outdoor use and places without internet or mobile signal.

## Version 1

The first version is planned to include:

- Raspberry Pi 5 with 8 GB RAM
- Official 512 GB NVMe SSD kit
- 8-inch HDMI touchscreen
- Offline maps and GPS for Slovenia
- LoRa text messaging with a separate handheld touchscreen terminal
- Local document search
- Rechargeable battery
- Custom power-management board
- 3D-printed mounts and enclosures

The handheld terminal uses a small touchscreen and an on-screen keyboard. It has a separate LoRa radio board.

## Hardware decisions

The main hardware choices and supplier links are listed in [docs/BOM.md](docs/BOM.md).

The selected case is the SINOCASE SC001, purchased from Temu seller sinocase. The matching manufacturer specification lists an internal footprint of 255 × 190 mm and total internal depth of 85 mm. The current mechanical design assumes approximately 58 mm usable depth in the lower half; this is a user estimate and should be checked against the physical case during final mounting.

The preferred battery target is a protected 2S4P Li-ion pack around 7.4 V, 20 Ah / 148 Wh. The exact pack remains subject to supplier quote, complete dimensions, BMS documentation and charger compatibility. The custom power board must be load-tested before it is connected to the Raspberry Pi.

The 10-hour runtime target is an engineering goal, not a guarantee; it must be measured on the finished build.

## Later version

Possible later additions:

- RTL-SDR receiver
- Separate GPS trackers
- Tracker location and history

## Progress

The v1 component architecture and supplier shortlist are documented in the [parts list](docs/BOM.md). Remaining validation work is the battery purchase/fit, final power-board design and load test, mechanical fit check, and firmware tests for GPS, LoRa and the handheld terminal.
