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

The main hardware choices are listed in [docs/BOM.md](docs/BOM.md). The battery pack is not selected yet. The preferred power architecture is a 2-cell Li-ion pack, subject to finding a suitable pack and validating its charger, protection and dimensions.

The exact case model and usable internal dimensions still need to be confirmed before the final mechanical layout and battery can be approved. The 10-hour runtime target must be measured on the finished build.

## Later version

Possible later additions:

- RTL-SDR receiver
- Separate GPS trackers
- Tracker location and history

## Progress

The main components have been selected and the first power architecture is defined. Mechanical fit, battery selection, power-board validation and firmware tests remain. See the [parts list](docs/BOM.md) for the current shopping list.
