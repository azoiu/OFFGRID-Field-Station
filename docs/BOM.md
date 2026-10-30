# OFFGRID – parts list

These are the parts I am planning to use for the first version. Prices are from when I checked and may change.

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

The screen uses HDMI for the image and USB for touch, so I will need both cables. The GPS module uses 3.3 V, not 5 V.

## Handheld

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3, EU868 | 1 | €22.95 | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| Waveshare ESP32-S3-Touch-LCD-2.8, V2 | 1 | About US$20–26 | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |

The handheld will have a touchscreen and an on-screen keyboard. The Waveshare board has no LoRa, so I am pairing it with another Heltec.

The connection between the two boards should be UART (3.3 V):

- Waveshare TX GPIO43 → Heltec RX GPIO48
- Waveshare RX GPIO44 ← Heltec TX GPIO47
- GND → GND

I need to double-check the pin labels before soldering. Also, I need to make sure I order V2 of the Waveshare board, not V1.

## Battery

I am looking at a 2S4P Li-ion pack from [ASOL](https://asolbattery.com/product/asol-21700-2s4p-7-4v-20000mah-cylindrical-li-ion-battery-pack/).

- 7.4 V nominal, 8.4 V fully charged
- 20 Ah (about 148 Wh)
- Built-in 2S BMS
- Listed thickness: about 44 mm

I have not ordered it yet. I still need the full dimensions, BMS details and a quote from the supplier. The listed dimensions are not enough to confirm that it fits.

A possible charger is the [Fuyuang 8.4 V / 3 A charger](https://baterija.lt/en/chargers-power-supply/2124-fuyuang-2s-li-ion-battery-charger-84v-3a.html), but I will check that it matches the battery and its BMS first.

## Power

This part still needs work.

The Pi 5 needs a stable 5.1 V supply. The [Geekworm Pi5-5V5APD](https://wiki.geekworm.com/Pi5-5V5APD) can supply up to 5 V / 5 A, but its input needs 9–24 V. My planned 2S battery only gives 6–8.4 V, so it cannot power this board directly. I would need a suitable boost converter before it, or a different power solution.

The screen will also need its own 5 V supply. I plan to make a small power PCB with a fuse, switch, battery monitoring and separate outputs. I have not chosen the final parts for this yet.

I will test the power setup before connecting it to the Pi. I also need to work out safe low-battery shutdown.

## Price so far

The parts with prices listed above come to **€483.17**. This includes the Pi, SSD kit, cooler, main screen, two Heltec boards and GPS.

It does not include the handheld screen, battery, charger, power electronics, cables or shipping, so the final price will be higher.

## Still to do

- Get the battery dimensions and BMS information.
- Decide on the power supply and design the power PCB.
- Test GPS, LoRa and the handheld screen.
- Check that everything fits in the case and make the mounts.
- Measure the real battery runtime. Around 10 hours would be nice, but I need to test it.

## Links

- [Raspberry Pi M.2 HAT+ guide](https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html)
- [Waveshare 8-inch screen](https://www.waveshare.com/wiki/8DP-CAPLCD)
- [Waveshare handheld screen documentation](https://docs.waveshare.com/ESP32-S3-Touch-LCD-2.8)
- [Heltec WiFi LoRa 32 V3](https://heltec.org/project/wifi-lora-32-v3/)
- [EU868 frequency rules](https://www.thethingsnetwork.org/docs/lorawan/regional-parameters/eu868/)
