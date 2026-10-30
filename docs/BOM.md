# OFFGRID v1 – Parts List

This is the shopping list for the first version. Prices include VAT where stated. Prices and stock can change.

## Parts I already have

- SC001 case
- Keyboard for the main station
- 3D printer
- Two general ESP32 boards
- Some cables and workshop parts

## Main station

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €184.06 | [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/) |
| Raspberry Pi 512 GB SSD kit (includes M.2 HAT+) | 1 | €138.05 | [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/) |
| Raspberry Pi Active Cooler | 1 | €5.26 | [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/) |
| Waveshare 8-inch touchscreen | 1 | about €93.50 | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GPS board with active antenna | 1 | €16.40 | [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna) |

The GPS board is listed as in stock (11 units) at the time of checking. It supports UART, I2C and SPI and includes an active antenna. Check the exact pin labels before wiring it to the Pi.

## Handheld terminal

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/products/heltec-wifi-lora-32-v3) |
| Waveshare ESP32-S3-Touch-LCD-2.8, with capacitive touch | 1 | $19.99–$25.99 before shipping/tax | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |

The Waveshare board provides the small touchscreen and runs the on-screen keyboard. It does not include LoRa. The Heltec board provides LoRa. The two boards can communicate over a 3.3 V UART connection. On the Waveshare board, TXD is GPIO43 and RXD is GPIO44. On the Heltec V3, GPIO47 and GPIO48 are available for external use and can be assigned to a UART in software. Connect TX to RX, RX to TX and GND to GND. Do not connect the 5 V pins together. The software still needs to be written and tested. Buy the touch version, not the version without touch. Shipments have switched to V2 with the CST3530 touch controller, so use the V2 driver.

## Battery and power

The battery is not chosen yet. I am looking for one that fits inside the SC001 case. The charger will be chosen after the battery.

I will design and make the power-management board. It needs:
- A suitable battery charger and battery protection, chosen for the final battery
- A main fuse and power switch
- Battery voltage and current monitoring
- A stable 5.1 V / 5 A USB-C supply for the Raspberry Pi 5
- A separate 5 V supply for the main screen and other electronics

The Raspberry Pi 5 uses 5.1 V and the official 27 W USB-C supply provides 5.1 V at 5 A. The main screen is rated at 4 W and needs its own 5 V branch. The internal power board must therefore provide the Pi supply plus the screen load with extra margin. A basic buck converter connected to a random USB-C cable is not enough; the USB-C output must be designed to supply the required current safely. Use the official Pi supply for bench testing. See [Raspberry Pi power requirements](https://www.raspberrypi.com/documentation/computers/getting-started.html).

For the first bench tests, use the official Raspberry Pi 27 W USB-C power supply (5.1 V, 5 A). It is not the final internal battery power system.

## Other parts

- Short HDMI cable for the main screen
- USB cable for touchscreen input
- 3.3 V UART wires for GPS and for the two handheld boards
- LoRa antennas (included with the Heltec boards)
- Suitable wire, connectors, heat-shrink tubing and cable ties
- Screws, spacers and mounting parts

Check what is already in the workshop before buying these small parts.

## Current price estimate

The parts with known euro prices add up to about **€483.17 including VAT**. This includes both LoRa boards and the GPS board. It does not include the handheld touchscreen (listed in US dollars before shipping/tax), battery, charger, custom power board, power components or small parts. Shipping is extra.

## Parts I will make

- Power-management board
- 3D-printed screen frame and mounts
- 3D-printed handheld case
- OFFGRID software and offline maps

## Later version

The RTL-SDR receiver and separate GPS trackers are planned for a later version, not v1.

## Still to finish

- Find a battery that fits the case and choose its charger
- Design and test the battery power board and USB-C power output
- Test communication between the handheld touchscreen board and the Heltec LoRa board
- Confirm the GPS wiring and test satellite reception
- Measure the flat inside space and lid depth of the case; the outside dimensions alone are not enough to confirm fit
- Add final cable, connector and mounting quantities after the layout is fixed
