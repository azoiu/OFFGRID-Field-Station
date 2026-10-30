# OFFGRID v1 – Simple Shopping List

This list covers Version 1 only. Prices are estimates including VAT, checked on 30 October 2026 where a live price was available. Stock and delivery costs can change.

## Already owned

- SC001 hard case
- Main keyboard
- 3D printer
- Two general ESP32 development boards (not counted as the LoRa radios)
- Some workshop materials and cables (inventory still needs checking)

## Buy – main station

| Part | Quantity | Estimated price | Where |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €184.06 | [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/) |
| Official Raspberry Pi 512 GB SSD kit (includes M.2 HAT+) | 1 | €138.05 | [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/) |
| Raspberry Pi Active Cooler | 1 | €5.26 | [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/) |
| Waveshare 8DP-CAPLCD, 8-inch touchscreen, 1280 × 800 | 1 | about €93.50 | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec WiFi LoRa 32 V3, EU868 | 1 | about €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GNSS receiver board with active antenna | 1 | €16.40 (currently out of stock) | [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna) |

## Buy – handheld terminal

| Part | Quantity | Estimated price | Where |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | about €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| Small text-input device | 1 | Not selected | Choose a compact Bluetooth keyboard or a small physical keypad before ordering |

Both Heltec boards include an OLED screen and LoRa radio. The handheld still needs a practical way to enter messages. The keyboard/keypad choice also affects the handheld enclosure and firmware.

## Power system – battery deliberately left open

- Battery: **not selected yet**. I am looking for a battery with suitable dimensions for the SC001 case.
- Charger: **not selected yet**. It must match the final battery chemistry, voltage and charging current.
- Custom power-management PCB: I will design and make it.
- DC-DC power stage: design target is a stable 5.1 V supply for the Raspberry Pi 5 (up to 5 A) and a separate 5 V supply for the screen. The final converter/current rating will be chosen together with the battery and power PCB.
- Add a correctly rated main fuse, master switch, battery-voltage/current monitoring, connectors and suitable wire. These will be integrated into the custom power board and wiring layout.

The Raspberry Pi 5 officially recommends 5 V at 5 A. The screen uses 5 V and is rated at 4 W. The power system must therefore be designed for both loads, with enough margin. See the [Raspberry Pi power requirements](https://www.raspberrypi.com/documentation/computers/getting-started.html) and [Waveshare display specifications](https://www.waveshare.com/wiki/8DP-CAPLCD).

## Small parts and materials

- HDMI cable for the display (short, flexible cable)
- USB cable for touchscreen input (short cable; display package includes connection cables/adapters)
- GNSS connection wires and a suitable 3.3 V UART connection to the Raspberry Pi (confirm the exact board pinout before wiring)
- LoRa antennas supplied with the Heltec boards
- Suitable wire, connectors, heat-shrink tubing, insulation, cable ties and mounting screws/standoffs
- Main power fuse and switch (final ratings depend on the selected battery and power design)

Check existing workshop stock before buying these small items to avoid duplicates.

## Estimated cost (battery excluded)

The currently priced main components total about **€482.12 including VAT**, before shipping. This includes the two LoRa boards and the GNSS board at its listed price, even though the GNSS board is currently out of stock. It excludes the handheld keyboard/keypad, battery, charger, final DC-DC stage, custom PCB parts and small materials. This is a partial subtotal, not the final project price.

## What I will make

- Custom power-management PCB
- 3D-printed screen frame and internal mounts
- 3D-printed handheld enclosure
- OFFGRID software and offline map setup

## Not part of Version 1

RTL-SDR receiver, two separate GPS/LoRa trackers, tracker history and other radio-monitoring features are postponed to Version 2.

## Still to decide before ordering everything

1. Select a battery that physically fits the case; battery and charger are intentionally left open.
2. Choose how messages will be typed on the handheld terminal.
3. Replace the GNSS board if it remains out of stock, and confirm its connector/pinout before purchase.
4. Measure the case interior and check the foam layout before fixing the screen, battery and mounts in place.
