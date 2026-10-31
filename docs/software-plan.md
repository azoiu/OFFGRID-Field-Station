# Software plan

This is a plan only. I have not installed or tested this software yet.

## Operating system

I plan to use Raspberry Pi OS 64-bit. The exact OS image and setup are still to decide.

## Offline maps of Slovenia

I want offline maps based on OpenStreetMap data. The map application and the way I will download and update the Slovenia map are still to decide.

## Local AI

I want to try local AI on the Raspberry Pi 5 with 8 GB RAM.

The M.2 HAT+ will be used for the NVMe SSD, so I plan for CPU-only inference at first. Small models around 1–3B parameters are the realistic starting point. A 7–8B Q4 model may run at only a few tokens per second on this hardware. This is an expectation, not a measurement.

I need to test memory use, speed and heat before choosing a model.

## LoRa

One idea is to use Meshtastic on the Heltec WiFi LoRa 32 V3 EU868 boards.

In the EU 868 MHz band there are duty-cycle limits. Some sub-bands are usually limited to 1%, while some allow 10%. I need to check the current rules and the exact frequency plan before transmitting. The correct settings must follow the local regulations.

## GPS

I plan to use a u-blox M10 receiver. The exact breakout board, antenna, power supply and interface to the Pi are still to decide.

## What I will test first

1. Boot Raspberry Pi OS from the NVMe SSD.
2. Check the screen, HDMI and USB touch connection.
3. Get GPS data from the selected breakout.
4. Send and receive a short LoRa message between the two boards.
5. Open offline map data for Slovenia without an internet connection.
6. Run a small local AI model and record speed, memory use and temperature.
7. Check that the main software can start without internet access.

These are planned tests. None of them are completed yet.
