# OFFGRID

OFFGRID is a small computer in a hard case. I want to use it outside and in places where there is no internet or mobile signal.

## What I want to build

The first version should have:

- Raspberry Pi 5 with 8 GB RAM
- 512 GB SSD
- 8-inch touchscreen
- GPS and offline maps for Slovenia
- LoRa messaging
- A separate handheld device with a touchscreen
- Local document search
- A rechargeable battery

I already have the case, keyboard, 3D printer and a few ESP32 boards.

## The case

I bought a SINOCASE SC001 case from Temu. The matching product specification lists an inside size of 255 × 190 × 85 mm. I estimate that the bottom part has about 5.8 cm of space. I want to keep this case, so the layout will be designed around it.

The main screen should go in the lid. The Raspberry Pi, SSD, battery and power board will go in the bottom.

## Current plan

The parts and shop links are in [docs/BOM.md](docs/BOM.md).

I am planning to use a 2S Li-ion battery and make a power board for the Pi and screen. The battery still needs to be confirmed, and the power board needs to be designed and tested.

I would like the device to run for around 10 hours, but I need to test the finished build to see how long it really lasts.

## Later

If the first version works well, I may add an RTL-SDR receiver, separate GPS trackers and a way to save tracker locations.

For now, I want to get the basic device working properly.
