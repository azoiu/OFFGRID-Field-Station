# OFFGRID – parts list

This is the list of parts for the first version of OFFGRID. Prices are the ones I found while planning the build. They can change, so check the shop before ordering.

## What I already have

- SINOCASE SC001 case from Temu (seller: sinocase)
- Keyboard
- 3D printer
- Two ESP32 boards (these do not have LoRa)
- Some cables and workshop parts

## The case

The matching SC001 case specification gives these dimensions:

- Outside: 280 × 230 × 98 mm
- Inside: 255 × 190 × 85 mm

[Case specifications](https://www.chinax.com/china-enclosure/pz691235a-moisture-proof-plastic-gun-case-dust-proof-waterproof-drop-resistant.html)

I estimate that the bottom part has about 5.8 cm of usable depth. I want to keep this case, so the parts and mounts need to fit it.

The 8-inch screen is about 194 × 119 mm. It should fit in the lid. The Raspberry Pi, SSD, battery and power board will go in the bottom. Before making the mounts, I still need to check the actual space in the case and compare it with the parts.

## Main station

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €184.06 | [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/) |
| Official 512 GB SSD kit (includes M.2 HAT+) | 1 | €138.05 | [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/) |
| Raspberry Pi Active Cooler | 1 | €5.26 | [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/) |
| Waveshare 8-inch HDMI touchscreen | 1 | €93.50* | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GPS with antenna | 1 | €16.40 | [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna) |

*The display listing showed a stock notification when I checked. Check availability before ordering.

The SSD kit already includes the M.2 HAT+, so I do not need to buy one separately. The screen uses HDMI for the picture and USB for touch. I will need a short micro-HDMI to HDMI cable and a USB data cable.

The GPS board uses 3.3 V. It must not be connected to 5 V.

## Handheld terminal

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| Waveshare ESP32-S3-Touch-LCD-2.8, V2 | 1 | About US$20–26, before shipping and tax | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |

The handheld will have a touchscreen and an on-screen keyboard. The Waveshare board does not have LoRa, so it needs the second Heltec board.

I need the V2 version of the Waveshare screen. It uses a different touch controller from V1, so I should check the version with the seller before ordering.

The two boards will communicate over UART using 3.3 V signals:

- Waveshare TX GPIO43 → Heltec RX GPIO48
- Waveshare RX GPIO44 ← Heltec TX GPIO47
- GND → GND

I need to check the labels on the actual boards before soldering. The software for the handheld still needs to be written and tested.

## Battery

The current plan is to use a 2S4P Li-ion battery pack:

- 7.4 V nominal voltage
- 8.4 V when fully charged
- Around 20 Ah / 148 Wh
- Built-in 2S BMS with cell balancing and protection
- Target thickness around 44 mm, so it may fit in the case

One possible pack is listed by [ASOL](https://asolbattery.com/product/asol-21700-2s4p-7-4v-20000mah-cylindrical-li-ion-battery-pack/). This is a manufacturer product, not a normal shop item. I need to ask them for the full dimensions, BMS details, cell type, safety documents and a price before deciding.

A possible charger is the [Fuyuang 8.4 V / 3 A charger](https://baterija.lt/en/chargers-power-supply/2124-fuyuang-2s-li-ion-battery-charger-84v-3a.html). I should only buy it after the battery supplier confirms that it is suitable for the exact battery and BMS.

The aim is to get close to 10 hours of use. I will only know the real runtime after testing the finished device.

## Power

The Pi 5 needs a stable 5.1 V supply. I am considering the [Geekworm Pi5-5V5APD](https://wiki.geekworm.com/Pi5-5V5APD) for powering it. It can provide up to 5 V / 5 A over USB-C, but it needs a suitable input supply. The input and battery wiring still need to be designed properly.

I also need a separate 5 V supply for the main screen. The power board will be a custom PCB.

The board should include:

- A fuse close to the battery
- Main power switch
- Reverse-polarity protection
- Separate power outputs for the Pi and screen
- Battery voltage and current monitoring
- Low-battery warning and safe shutdown for the Pi
- Suitable connectors and protection

I should not connect the battery directly to the Pi or use a random buck converter. The power system needs to be tested with a multimeter and an electronic load before connecting the Pi.

For early testing, I can use a suitable 12 V supply for the Geekworm board and a separate 5 V supply for the screen.

## Other things I will need

I should check what I already have before buying these:

- Short micro-HDMI to HDMI cable
- USB data cable for the touchscreen
- Suitable 12 V power supply for testing
- Battery fuse and holder
- Main switch
- Charging socket
- Connectors for the battery and power cables
- Suitable wires, heat-shrink and cable ties
- Screws, nuts and spacers
- Insulation and a battery holder

The fuse, wire thickness and connectors must be chosen after the final power design is ready.

## Price so far

The parts with known prices add up to **€483.17**:

- Raspberry Pi 5
- 512 GB SSD kit
- Active Cooler
- Main touchscreen
- Two Heltec LoRa boards
- GPS module

This does not include the handheld screen, battery, charger, power board, cables, connectors or shipping. It is not the final price of the whole project.

## What I still need to do

1. Check the prices and availability before ordering.
2. Get the battery dimensions and BMS information from the supplier.
3. Finish the power-board design.
4. Test the power supply before connecting the Pi.
5. Test GPS, LoRa and the handheld screen.
6. Make the 3D-printed mounts after checking the parts in the case.
7. Measure the real battery runtime.

## Later additions

These are not part of the first version:

- RTL-SDR receiver
- Separate GPS trackers
- Tracker location history

For the first version, I want offline maps, GPS, LoRa messages and local document search to work reliably.

## Useful links

- [Raspberry Pi M.2 HAT+ guide](https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html)
- [Waveshare 8-inch screen](https://www.waveshare.com/wiki/8DP-CAPLCD)
- [Waveshare handheld screen documentation](https://docs.waveshare.com/ESP32-S3-Touch-LCD-2.8)
- [Heltec WiFi LoRa 32 V3](https://heltec.org/project/wifi-lora-32-v3/)
- [EU868 frequency rules](https://www.thethingsnetwork.org/docs/lorawan/regional-parameters/eu868/)
