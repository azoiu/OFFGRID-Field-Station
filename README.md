# OFFGRID

OFFGRID is a small computer built into a hard case. I want to use it outdoors and in places without internet or mobile signal.

## First version

- Raspberry Pi 5 (8 GB)
- 512 GB NVMe SSD
- 8-inch touchscreen
- GPS and offline maps for Slovenia
- LoRa text messages
- A separate handheld terminal with a touchscreen
- Local document search and local AI
- Rechargeable LiFePO4 battery

I already have the case, keyboard, 3D printer and a few ESP32 boards.

## Case

I bought a SINOCASE SC001 from Temu. The listed inside dimensions are 255 × 190 × 85 mm. The bottom part seems to have around 5.8 cm of usable space. I want to keep this case, so everything has to fit inside it.

The screen will go in the lid. The Pi, SSD, battery and power electronics will go in the bottom.

## Current plan

The parts and prices are in [BOM.csv](BOM.csv). More notes are in [docs/BOM.md](docs/BOM.md). The first system layout is in [docs/system-block-diagram.md](docs/system-block-diagram.md), and the first wiring plan is in [docs/electrical-design.md](docs/electrical-design.md).

I am still choosing the battery and power parts. My target is around 10 hours of runtime, but I will have to measure the real runtime once it is built.

## Maybe later

Separate GPS trackers and an RTL-SDR receiver are ideas for a later version, not part of V1.

For now, I just want to get the basic station working.
