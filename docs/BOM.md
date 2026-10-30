# OFFGRID v1 – Parts List

Prices are snapshots checked on 30 October 2026. Shipping and stock can change.

## Parts I already have
- SINOCASE / SC001 hard case bought from Temu seller sinocase
- Keyboard for the main station
- 3D printer
- Two general ESP32 boards (not LoRa radios)
- Some cables and workshop materials

## Case dimensions and layout
The Temu product page is not accessible outside the Temu app. The matching SC001 manufacturer specification lists external dimensions of 280 × 230 × 98 mm and internal dimensions of **255 × 190 × 85 mm**: https://www.chinax.com/china-enclosure/pz691235a-moisture-proof-plastic-gun-case-dust-proof-waterproof-drop-resistant.html

The 8-inch display panel is approximately 194 × 119 mm. It fits the internal footprint with its 194 mm side along the 255 mm side. Recommended layout: display in a custom 3D-printed lid frame; Raspberry Pi, SSD and power board in the base. The 85 mm is the total internal depth; the lid/base split is not published. Measure both depths before printing final mounts or choosing the battery. Do not assume all 85 mm is available in the base.

## Main station
| Part | Qty. | Price incl. VAT | Shop |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €184.06 | https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/ |
| Official Raspberry Pi 512 GB SSD kit (includes M.2 HAT+) | 1 | €138.05 | https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/ |
| Raspberry Pi Active Cooler | 1 | €5.26 | https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/ |
| Waveshare 8DP-CAPLCD, 8-inch HDMI touchscreen | 1 | €93.50 | https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding |
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | https://hexaspot.com/products/heltec-wifi-lora-32-v3 |
| u-blox M10 GPS board with active antenna | 1 | €16.40 | https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna |

The SSD kit includes the M.2 HAT+ and SSD. Do not buy a second HAT+. Check the supplied mounting hardware and clearance with the Active Cooler using the official installation guide. The main display is 1280 × 800, HDMI video, USB touch and 4 W. Use a short micro-HDMI-to-HDMI cable and a separate 5 V supply branch. The GPS supports GPS, Galileo, GLONASS and BeiDou; its supply range is 1.65–3.6 V, so never connect it to 5 V. Use 3.3 V UART and check the board pin labels. The GPS listing showed 11 in stock when checked.

## Handheld terminal
| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | https://hexaspot.com/products/heltec-wifi-lora-32-v3 |
| Waveshare ESP32-S3-Touch-LCD-2.8, capacitive touch version | 1 | US$19.99–25.99 before shipping/tax | https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm |

Buy the version with touch. Waveshare switched shipments to V2 in June 2026; V2 uses CST3530, V1 uses CST328. Ask the seller to confirm V2. The handheld display board has no LoRa, so the second Heltec is required.

UART wiring between the handheld boards (3.3 V logic): Waveshare TXD GPIO43 → Heltec RX GPIO48; Waveshare RXD GPIO44 ← Heltec TX GPIO47; GND → GND. Do not connect their 5 V pins together. Confirm actual pin labels before soldering. Firmware and the UART link still need testing.

## Power system
The battery is not selected yet. Preferred architecture: protected 2S Li-ion pack, 7.4 V nominal / 8.4 V full, with integrated 2S BMS and cell balancing. Aim for 140–150 Wh if the 10-hour runtime target remains important, but this is only a capacity target; actual runtime must be measured.

The custom power board should provide a dedicated regulated 5.1 V / 5 A minimum Pi branch with a properly implemented USB-C source, a separate 5 V / 1.5 A display branch, battery monitoring, fuse, master switch, reverse-polarity protection and low-voltage safe-shutdown signal. Charger must be a CC/CV 8.4 V charger matched to the final battery and BMS. A possible external charger is the Fuyuang 8.4 V / 3 A unit at https://baterija.lt/en/chargers-power-supply/2124-fuyuang-2s-li-ion-battery-charger-84v-3a.html, but buy it only after the pack maker confirms compatibility.

A 2S 20 Ah (148 Wh) pack is a suitable capacity class on paper. The ASOL 2S4P example is an OEM quote item, not a ready-to-buy EU retail product: https://asolbattery.com/product/asol-21700-2s4p-7-4v-20000mah-cylindrical-li-ion-battery-pack/. Do not order it before confirming the complete pack dimensions, BMS, certificates, shipping and case depth. The 85 mm case depth is shared between lid and base.

For bench testing use the official Raspberry Pi 27 W USB-C supply. Do not power the Pi from an unverified USB-C breakout or generic buck converter. Test the complete power board under full CPU, SSD and screen load before connecting the Pi.

## LoRa
Use EU868 versions of both Heltec boards and their supplied 868 MHz antennas. Hexaspot listed €22.95 and a 1–3 week backorder when checked. Configure legal EU868 frequencies, transmit power and duty-cycle limits. Do not buy US915 versions. Meshtastic is useful for range tests; custom firmware may be needed for the final handheld interface.

## Other parts
Check workshop stock before buying: short micro-HDMI-to-HDMI cable; USB cable for touch; 3.3 V UART leads; battery connector matching the selected pack; correctly rated fuse and holder; DC-rated switch; locking connectors; suitable wire; heat-shrink; cable ties; M2.5 screws and spacers. Fuse and wire ratings must be chosen from the final battery and converter design. Print the display frame and internal mounts after measuring the lid/base split.

## Price estimate
Known euro-priced parts total **€483.17 including VAT** (Pi, SSD kit, cooler, main display, two LoRa boards and GPS). Excludes handheld touchscreen, battery, charger, converters, custom power PCB, wiring, connectors and shipping. This is not a final checkout total.

## Parts I will make
- Custom power-management PCB after battery and converter validation
- 3D-printed display frame and internal mounts
- 3D-printed handheld enclosure
- OFFGRID software and offline Slovenia maps

## Not in v1
RTL-SDR, separate GPS trackers, tracker history, large local language models or model training. Local document search is realistic; fast general-purpose local AI is not a reasonable Pi 5 performance promise.

## Final checks before ordering
- Measure the separate depth of the base and lid and usable flat floor area.
- Confirm Waveshare ships the V2 touch version.
- Confirm checkout price, stock and shipping. Hexaspot showed a 1–3 week backorder; Neven7 showed 11 GPS boards in stock.
- Confirm battery dimensions, BMS, charging current and certificates before buying a charger or designing the PCB.
- Test GPS, handheld UART and LoRa range before permanent mounting.
- Validate the power board with an electronic load and multimeter before connecting the Pi.

## References
- SC001 dimensions: https://www.chinax.com/china-enclosure/pz691235a-moisture-proof-plastic-gun-case-dust-proof-waterproof-drop-resistant.html
- Raspberry Pi power: https://www.raspberrypi.com/documentation/computers/getting-started.html
- M.2 HAT+ installation: https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html
- Raspberry Pi SSD kit: https://www.raspberrypi.com/products/ssd-kit/
- Waveshare main display: https://www.waveshare.com/wiki/8DP-CAPLCD
- Waveshare handheld V2: https://docs.waveshare.com/ESP32-S3-Touch-LCD-2.8
- Heltec V3: https://heltec.org/project/wifi-lora-32-v3/
- EU868 rules: https://www.thethingsnetwork.org/docs/lorawan/regional-parameters/eu868/
