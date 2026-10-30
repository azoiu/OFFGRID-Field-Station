# OFFGRID

OFFGRID is a small computer built into a hard case. I want to use it outdoors and in places without internet or mobile signal.

## First version

- Raspberry Pi 5 (8 GB)
- 512 GB SSD
- 8-inch touchscreen
- GPS and offline maps for Slovenia
- LoRa messaging
- A small handheld terminal with a touchscreen
- Local document search
- Rechargeable battery

I already have the case, keyboard, 3D printer and a few ESP32 boards.

## Case

I bought a SINOCASE SC001 from Temu. The listed inside dimensions are 255 × 190 × 85 mm. The bottom part seems to have around 5.8 cm of usable space. I want to keep this case, so everything has to fit inside it.

The screen will go in the lid. The Pi, SSD, battery and power electronics will go in the bottom.

## Current plan

The parts I am considering are listed in [docs/BOM.md](docs/BOM.md). I am looking at a 2S Li-ion battery, but the battery and power system are not final yet.

My target is around 10 hours of runtime. I will have to measure the actual runtime once it is built.

## Maybe later

If the first version works, I might add an RTL-SDR receiver and separate GPS trackers.

For now, I just want to get the basic station working.
