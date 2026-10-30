# OFFGRID – parts list

These are the parts I am planning to use for the first version. Prices are from when I checked and may change. The full list is in [BOM.csv](../BOM.csv).

## Already have

- SINOCASE SC001 case (Temu, seller: sinocase)
- Keyboard
- 3D printer
- Two ESP32 boards (without LoRa)
- Some cables and workshop parts

## Case

The listed dimensions for the SC001 are:

- Outside: 280 × 230 × 98 mm
- Inside: 255 × 190 × 85 mm

[Case specifications](https://www.chinax.com/china-enclosure/pz691235a-moisture-proof-plastic-gun-case-dust-proof-waterproof-drop-resistant.html)

I measured roughly 5.8 cm of usable depth in the bottom. The 8-inch screen is about 194 × 119 mm, so it should fit in the lid. I still need to check the real measurements before making the mounts.

## Main station

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €184.06 | [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/) |
| Official 512 GB SSD kit (with M.2 HAT+) | 1 | €138.05 | [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/) |
| Raspberry Pi Active Cooler | 1 | €5.26 | [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/) |
| Waveshare 8-inch HDMI touchscreen | 1 | €93.50* | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GPS with antenna | 1 | €16.40 | [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna) |

*The screen was showing a stock notification when I checked.

The screen uses HDMI for the image and USB for touch. The GPS module uses 3.3 V, not 5 V.

## Handheld terminal

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| Waveshare ESP32-S3-Touch-LCD-2.8, V2 | 1 | About US$20–26 | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |

The handheld will have a touchscreen and an on-screen keyboard. The Waveshare board has no LoRa, so I am pairing it with another Heltec.

The planned UART connection is:

- Waveshare TX GPIO43 → Heltec RX GPIO48
- Waveshare RX GPIO44 ← Heltec TX GPIO47
- GND → GND

I need to double-check the pin labels before soldering. Both boards use 3.3 V logic.

## Battery and power

I have decided to use a LiFePO4 battery for the main station, but I have not chosen the exact pack yet. I still need to compare its voltage, capacity, BMS, size and price. The target is around 10 hours of use.

The charger must match the selected battery pack and its BMS. I will not choose a charger before choosing the battery.

The Pi 5 needs a stable 5.1 V supply with enough current. The screen needs its own supply based on the exact display specifications. The power PCB should include a fuse, main switch, protection, separate outputs and battery monitoring.

The Geekworm Pi5-5V5APD is only one possible module. Its input range is 9–24 V, so it can only be used if the selected battery and power design can supply that voltage. It is not selected yet.

## Price so far

The parts with prices listed in BOM.csv add up to **€483.17**. This includes the Pi, SSD kit, cooler, main screen, two Heltec boards and GPS.

It does not include the battery, charger, power electronics, handheld screen, cables or shipping, so the final price will be higher.

## Still to do

- Choose the LiFePO4 battery and charger.
- Finish the power design.
- Check the exact display power requirements.
- Test GPS, LoRa and the handheld screen.
- Check that everything fits in the case and make the mounts.
- Measure the real battery runtime.

## Useful links

- [Raspberry Pi M.2 HAT+ guide](https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html)
- [Waveshare 8-inch screen](https://www.waveshare.com/wiki/8DP-CAPLCD)
- [Waveshare handheld screen documentation](https://docs.waveshare.com/ESP32-S3-Touch-LCD-2.8)
- [Heltec WiFi LoRa 32 V3](https://heltec.org/project/wifi-lora-32-v3/)
- [EU868 frequency rules](https://www.thethingsnetwork.org/docs/lorawan/regional-parameters/eu868/)
