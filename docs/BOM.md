# OFFGRID – Shopping List (v1)

I checked the case size and the main parts again. The list below focuses on the first version only: Raspberry Pi, touchscreen, offline navigation, LoRa messaging and battery power. Prices are shown **including VAT**. They are online prices found on 30 October 2026; delivery costs and stock can change.

## Already owned

SC001 hard case, main keyboard, 3D printer, two general ESP32 boards and some workshop materials. The two ESP32 boards are not counted as purchased parts or as the two LoRa radios.

## Buy

**Main computer – TME**
- Raspberry Pi 5, 8 GB: **€184.06** – [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/)
- Official Raspberry Pi 512 GB SSD kit (includes M.2 HAT+): **€138.05** – [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/)
- Raspberry Pi Active Cooler: **€5.26** – [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/)

**Screen**
- Waveshare 8DP-CAPLCD, 8-inch, 1280 × 800 touchscreen: **about €93.50** – [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding). The listing shows €77.30 before VAT. HDMI and touch cables are included by Waveshare.

**LoRa messaging**
- 2 × Heltec WiFi LoRa 32 V3, EU868: **€22.95 each (€45.90 total)** – [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3). Each includes an antenna. One board goes in the main station and one in the handheld terminal.
- The handheld terminal still needs a small keyboard or another way to type messages. The board's OLED is only a display.

**Offline navigation**
- u-blox M10 GNSS board with active antenna: **€16.40** – [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna).

**Battery and charging**
- Green Cell 12.8 V, 10 Ah LiFePO4 battery: **€116.05** – [Senetic](https://www.senetic.si/product/CAV10). Dimensions: 151 × 65 × 95 mm. It should fit the SC001 case's published internal space (about 255 × 190 × 85 mm) when laid on its side, with the 65 mm dimension as height. Leave room for padding and wiring.
- 14.6 V LiFePO4 charger: **about €51.86** – [Tisto](https://tisto.eu/battery-chargers-sl/). Confirm connector and charging current match the exact battery before ordering.
- 5.1 V DC-DC converter, at least 8 A / 40 W, with proper cooling and protection: **not selected yet**. This is important: Raspberry Pi recommends 5 V at 5 A for Pi 5, and the screen also needs power. See [Raspberry Pi power requirements](https://www.raspberrypi.com/documentation/computers/getting-started.html).

## Estimated cost

Known parts: **about €651.08 including VAT**, before shipping. This includes the 10 Ah battery and its charger, but not the DC-DC converter, handheld keyboard, fuse, switch, connectors, wiring and mounting hardware.

## Battery runtime

The battery stores 128 Wh. With the Pi 5, SSD, screen and conversion losses, a realistic runtime depends on workload and screen brightness; **10 hours is not guaranteed**. We should measure actual consumption once the prototype is running. The battery dimensions fit the published SC001 internal dimensions on paper, but the foam and exact case variant must be checked before purchase.

## I will make

The power-management PCB, 3D-printed screen frame and internal mounts, handheld terminal enclosure, and the OFFGRID software.

RTL-SDR and the two GPS/LoRa trackers are excluded from v1 and remain ideas for a later version.
