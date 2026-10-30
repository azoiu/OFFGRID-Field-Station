# OFFGRID v1 – Parts List

This is the selected hardware for version 1. Prices and stock were checked on 30 October 2026 and can change. Shipping is not included.

## Parts I already have

- SC001 case (exact manufacturer and internal dimensions still need confirmation)
- Keyboard for the main station
- 3D printer
- Two general ESP32 boards (not LoRa radios)
- Some cables and workshop parts

## Main station

| Part | Qty. | Current price | Shop |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €190.80 | [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/) |
| Official Raspberry Pi 512 GB SSD kit (includes M.2 HAT+) | 1 | €146.70 | [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/) |
| Raspberry Pi Active Cooler | 1 | about €5.26 | [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/) |
| Waveshare 8DP-CAPLCD, 8-inch HDMI touchscreen | 1 | €93.50 | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GPS board with active antenna | 1 | €16.80 | [Neven](https://www.neven.sk/p/gps-modul-ublox-m10-s-aktivnou-antenou) |

The SSD kit includes the M.2 HAT+ and SSD. The standard HAT+ uses the supplied 16 mm spacers and is compatible with the Active Cooler underneath it. Do not buy a second M.2 HAT+.

The main display is 1280 × 800, connects by HDMI, uses USB for touch and needs a 5 V supply of at least 750–800 mA (4 W). Its panel is about 194 × 119 mm. Make a removable 3D-printed bezel so the glass is protected when the case is closed.

The GPS board supports GPS, Galileo, GLONASS and BeiDou and includes an active antenna. Its supply range is 1.65–3.6 V: do not connect it to 5 V. Use a 3.3 V UART connection to the Pi, check the board's actual pin labels, and mount the antenna with a clear view of the sky.

## Handheld terminal

| Part | Qty. | Current price | Shop |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/products/heltec-wifi-lora-32-v3) |
| Waveshare ESP32-S3-Touch-LCD-2.8, capacitive touch version | 1 | $19.99–$25.99 before shipping/tax | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |

Buy the version **with touch**. Shipments changed to V2 in June 2026. V2 uses the CST3530 touch controller; V1 uses CST328. The handheld display board does not have LoRa, so the second Heltec board is required.

Connect the two handheld boards over 3.3 V UART:
- Waveshare TXD (GPIO43) → Heltec RX (GPIO48)
- Waveshare RXD (GPIO44) ← Heltec TX (GPIO47)
- GND → GND

Do not connect their 5 V pins together. Confirm the pin labels on the actual board revision before soldering. The UART link and messaging firmware still need to be written and tested.

## Power system – selected design

The battery chemistry and physical pack are deliberately not selected until the case layout is measured. The power architecture is:

1. Use a **2-cell series Li-ion pack (2S, nominal 7.4 V)** as the preferred design direction, if a protected pack with suitable dimensions can be found.
2. The battery must have a correctly rated 2S BMS with cell balancing and over-current, over-charge and over-discharge protection.
3. The custom power board must include a charger specifically designed for 2S Li-ion (8.4 V charge voltage), a main fuse close to the battery, a master switch, reverse-polarity protection, battery voltage/current measurement and temperature-aware charging.
4. Provide a dedicated regulated **5.1 V / 5 A minimum** output for the Pi 5, with a USB-C source implementation that correctly advertises the available current. Use a short, low-resistance cable. Do not feed the Pi through an unverified USB-C breakout or a random buck converter.
5. Provide a separate regulated 5 V branch rated for at least 1.5 A for the main display, plus a small branch for GPS and other low-power electronics.
6. Design the converter and PCB for the combined load, start-up surges and heat. Bench-test under full CPU, SSD and screen load before installing it in the case.

A 2S pack is a design direction, not a battery purchase approval. Do not order the battery, BMS or charger until the dimensions, capacity and final charging circuit are checked together. The 10-hour runtime target is not guaranteed; measure the real average load and usable battery energy first.

For bench testing, use the official Raspberry Pi 27 W USB-C power supply. Raspberry Pi recommends 5 V at 5 A for Pi 5. The screen is powered separately. The official supply is a test supply, not the internal battery solution.

## LoRa setup

Use the EU868 versions of both Heltec boards and their supplied 868 MHz antennas. Configure legal EU868 frequencies, transmit power and duty-cycle limits for the selected sub-band. Do not use US915 boards or assume that maximum radio output is legal on every EU868 channel. The first version is a direct two-node text link; Meshtastic is useful for range testing, but custom firmware may be needed for the final handheld interface.

## Other parts to buy after checking the workshop

- Short HDMI cable (micro-HDMI to HDMI for the Pi 5)
- USB cable for the screen's touch input
- 3.3 V UART wires for GPS and handheld link
- Main fuse and holder, switch, suitable connectors and wire
- Heat-shrink tubing, cable ties, screws and spacers
- 3D-printed display frame, Pi/SSD support and handheld enclosure

## Price estimate

Known euro-priced parts total about **€498.96 including VAT**. This includes the Pi, SSD kit, cooler, main display, both LoRa boards and GPS. Add the handheld touchscreen (US$19.99–25.99 before shipping/tax), shipping, cables, connectors, power-board parts and the battery system. This is a component estimate, not a final checkout total.

## Parts I will make

- Custom power-management PCB (after the battery and converter design are validated)
- 3D-printed screen frame and internal mounts
- 3D-printed handheld case
- OFFGRID software and offline Slovenia maps

## Not included in v1

- RTL-SDR receiver
- Separate GPS trackers
- Tracker location history
- Local large language model training or heavy AI workloads

A small local document search assistant is realistic. A fast, general-purpose local AI model is not a reasonable performance promise for a Pi 5.

## Remaining checks before ordering

- Confirm the exact SC001 case model and measure usable internal floor dimensions, base depth and lid depth. The display's 194 × 119 mm panel is the key fixed footprint. Do not cut the case or order a battery before this check.
- Check that the Pi, standard M.2 HAT+, Active Cooler and cable bend radius fit the planned mount.
- Confirm stock and final shipping costs at checkout. Hexaspot showed the Heltec V3 as a 1–3 week backorder; the GPS listing showed 11 in stock when checked.
- Confirm Waveshare ships the V2 **touch** version.
- Test GPS reception, handheld UART and LoRa range before making permanent mounts.
- Validate the complete power board with an electronic load and a multimeter before connecting the Pi.

## References

- [Raspberry Pi 5 power requirements](https://www.raspberrypi.com/documentation/computers/getting-started.html)
- [Raspberry Pi M.2 HAT+ installation and cooler compatibility](https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html)
- [Raspberry Pi 512 GB SSD kit](https://www.raspberrypi.com/products/ssd-kit/)
- [Waveshare 8DP-CAPLCD specifications](https://www.waveshare.com/wiki/8DP-CAPLCD)
- [Waveshare handheld display V2 documentation](https://docs.waveshare.com/ESP32-S3-Touch-LCD-2.8)
- [Heltec WiFi LoRa 32 V3](https://heltec.org/project/wifi-lora-32-v3/)
- [EU868 regional restrictions overview](https://www.thethingsnetwork.org/docs/lorawan/regional-parameters/eu868/)
