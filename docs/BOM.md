# OFFGRID – Bill of Materials

This is the practical shopping list for the first version of OFFGRID. I am keeping it focused on the parts needed for the portable offline computer, navigation and LoRa messaging. Prices are approximate **VAT-inclusive prices** found from European shops on 30 October 2026. Shipping may change the final total, and stock should be checked before ordering.

## Parts I already have

- SC001 hard case.
- One keyboard for the main station.
- 3D printer for brackets, mounts and custom plastic parts.
- Some cables, switches and electronic parts (inventory still needs checking).

I also have two general-purpose ESP32 boards, but they are not included in this shopping list and are not being counted as the final LoRa devices.

## Main computer

**Raspberry Pi 5 – 8 GB RAM (1 pc)**  
Approx. **€184.06**. A suitable price was listed by TME; check stock and shipping before ordering.  
[View at TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/)

**Raspberry Pi 512 GB NVMe SSD Kit (1 pc)**  
Approx. **€138.05** at TME. This kit already includes the official M.2 HAT+, so a second adapter is not needed.  
[View at TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/)

**Raspberry Pi Active Cooler (1 pc)**  
Budget approx. **€6**. Needed to keep the Pi 5 cool during sustained use inside the case.  
[Official product information](https://www.raspberrypi.com/products/active-cooler/)

## Screen

**Waveshare 8DP-CAPLCD, 8-inch HDMI touchscreen (1 pc)**  
Approx. **€79.30** at RobotShop EU. 1280 × 800 IPS display with capacitive touch.  
[View at RobotShop EU](https://eu.robotshop.com/products/waveshare-8inch-capacitive-touch-display-toughened-glass-1280x800-ips-hdmi)

The display uses HDMI for video and USB for touch. Check the package contents before buying extra cables; the previous supplier listing included the required cables/adapters.

## LoRa messaging

**Heltec WiFi LoRa 32 V3, EU868 version (2 pcs)**  
Approx. **€25.35 each / €50.70 for two** at Nettigo. Each board includes an ESP32-S3, SX1262 LoRa radio, small OLED and an antenna. One is intended for the handheld terminal and one for the main station. Make sure the selected version is 868 MHz / EU868, not US915.  
[View at Nettigo](https://nettigo.eu/products/heltec-wifi-lora-32-v3-868mhz-esp32-lora-oled-0-96)

The handheld terminal still needs a practical way to type free-form messages. The small OLED is only a display, not a keyboard. We need to choose a compact keyboard or another text-input method and design a case for it.

## Offline navigation

**u-blox M10 GNSS module with active antenna (1 pc)**  
Approx. **€16.40** at Neven7. It supports GPS, Galileo, GLONASS and BeiDou. This board uses UART/I2C, so it will need suitable wiring or a USB-to-UART adapter to connect to the Raspberry Pi.  
[View at Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna)

## Power system

The battery is not selected yet. It must fit the actual space inside the case and safely supply the computer and screen.

Parts still needed:
- Protected 12.8 V LiFePO4 battery with a suitable BMS.
- Correct 14.6 V LiFePO4 charger for the chosen battery.
- Efficient 5 V regulator with enough current for the Raspberry Pi 5 and screen. The final design must be sized from measured peak load; a small generic USB buck board is not suitable without checking its real rating.
- Main power switch, correctly rated fuse, wiring and connectors.
- Voltage/current monitoring for the custom power-management PCB.

A compact 12.8 V 6 Ah battery stores only about 77 Wh. That is unlikely to provide 10 hours once conversion losses and the Pi 5 plus screen are included. The 10-hour target needs a proper power budget and may require a larger battery. Do not order a battery until the case dimensions and power budget are confirmed.

## Small parts and workshop materials

Allow for:
- Standoffs, screws, nuts and washers.
- Cable ties, heat-shrink tubing and insulation.
- Suitable connectors and wire.
- 3D-printing filament for the screen frame, internal mounts and terminal enclosure.
- A fuse holder and spare fuse.

I will check the parts already in my workshop before buying these.

## What I will make myself

- 3D-printed screen frame, internal brackets and mounts.
- Custom power-management PCB.
- OFFGRID software for offline maps, local document search/AI and LoRa messaging.
- Enclosure and mounting parts for the handheld terminal.

## Current price estimate

The currently priced core parts come to approximately **€474.51**, before shipping and before the battery, charger, power converter, text-entry device and small hardware are added. This is a working estimate, not a final project budget.

Prices and stock can change. The cheapest option is not always the best choice for a device that must be reliable and safe to carry, especially for the battery and power electronics.

## Not included in version 1

RTL-SDR and the two GPS/LoRa tracking devices are reserved for a possible later version. They are not part of this shopping list.
