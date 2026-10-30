# OFFGRID v1 — Bill of Materials

Last reviewed: 30 October 2026. Prices are EUR incl. VAT where stated; shipping and checkout prices can change.

## 1. Already owned

- SINOCASE SC001 hard case, bought from Temu seller sinocase
- Main keyboard
- 3D printer
- Two generic ESP32 development boards (not LoRa radios)
- Some workshop cables and materials

## 2. Case and mechanical layout

The Temu listing itself is not publicly readable outside the Temu app. The matching SC001 manufacturer specification gives external dimensions **280 × 230 × 98 mm** and internal dimensions **255 × 190 × 85 mm**:
https://www.chinax.com/china-enclosure/pz691235a-moisture-proof-plastic-gun-case-dust-proof-waterproof-drop-resistant.html

User-estimated usable lower-case depth: **58 mm**. Use this as the current mechanical design constraint; do not change to a larger case. The proposed 2S4P battery candidate is about 44 mm thick, so it is potentially compatible, but reserve clearance for wiring, insulation, mounting and the case floor. The exact battery pack cross-section and the case's flat floor area must be checked against the physical parts before drilling or printing final mounts.

The 8-inch panel is approximately 194 × 119 mm and fits the 255 × 190 mm internal footprint in the lid, with its 194 mm side along the 255 mm side. Mount the screen in a printed bezel in the lid. Put the Pi, SSD, power module and battery in the lower half. Keep the battery mechanically restrained and separated from sharp edges and hot components.

## 3. Main station — selected parts

| Part | Qty. | Price incl. VAT | Supplier |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB (TME SC1112) | 1 | €184.06 | https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/ |
| Official Raspberry Pi 512 GB SSD kit (SSD + M.2 HAT+) | 1 | €138.05 | https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/ |
| Raspberry Pi Active Cooler | 1 | €5.26 | https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/ |
| Waveshare 8DP-CAPLCD 8-inch HDMI capacitive touchscreen, 1280×800 | 1 | €93.50 (listing; stock notification shown) | https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding |
| Heltec WiFi LoRa 32 V3 EU868 | 1 | €22.95 | https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3 |
| u-blox M10 GPS board with active antenna | 1 | €16.40 | https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna |
| Geekworm Pi5-5V5APD 5.1 V / 5 A USB-C PD power module | 1 | price/stock to confirm | https://wiki.geekworm.com/Pi5-5V5APD |

The SSD kit already includes the M.2 HAT+; do not buy another HAT+. Check the HAT+ and Active Cooler physical clearance using the official guide before final assembly. Main display uses HDMI for video and USB for touch; add one short **micro-HDMI-to-HDMI cable** and one USB-A-to-USB-C data cable for touch. The screen is specified at 5 V / approximately 4 W; power it from a separate regulated 5 V branch, not from the Pi's USB port.

The GPS module supports GPS, Galileo, GLONASS and BeiDou. Its supply range is 1.65–3.6 V: connect to 3.3 V only, never 5 V. Use UART initially. Keep its active antenna away from the LoRa antenna and display/power switching noise.

The Geekworm Pi5-5V5APD accepts 9–24 V DC (or suitable USB-C PD input) and provides a genuine 5 V / 5 A USB-C PD output for the Pi. Manufacturer documentation requires **more than 30 W input** for full 5 A operation; a 27 W Raspberry Pi supply is not enough to guarantee full load. Feed it from the battery through a correctly designed regulated DC stage or use a compatible 12 V supply during bench testing. The board is 44 × 55 mm. Verify exact input version and mounting before ordering.

## 4. Handheld LoRa terminal — selected parts

| Part | Qty. | Price incl. VAT | Supplier |
|---|---:|---:|---|
| Heltec WiFi LoRa 32 V3 EU868 | 1 | €22.95 | https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3 |
| Waveshare ESP32-S3-Touch-LCD-2.8 capacitive touchscreen board, **V2** | 1 | approx. US$19.99–25.99 before shipping/tax; confirm checkout | https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm |
| Small LiPo battery for handheld, 3.7 V with matching SH1.25-2 connector | 1 | choose after enclosure/runtime test | https://hexaspot.com/collections/heltec |

The Waveshare V2 is required: shipments changed to V2 in June 2026 and V2 uses the CST3530 touch controller (V1 uses CST328). Confirm V2 with the seller before ordering. The display board does not contain LoRa, hence the second Heltec board.

Connect the two handheld boards using 3.3 V UART: Waveshare TXD GPIO43 → Heltec RX GPIO48; Waveshare RXD GPIO44 ← Heltec TX GPIO47; GND → GND. Do not join their 5 V pins. Verify silkscreen labels and board revision before soldering. The firmware and UART link still need to be developed and tested.

The Heltec V3 has integrated single-cell LiPo charging/management and a SH1.25-2 battery connector. Select a protected 3.7 V LiPo that physically fits the handheld enclosure; do not connect a 2S pack to this board.

## 5. Main battery and charging

**Selected battery specification for quoting (not yet a confirmed retail purchase):**

- 2S4P lithium-ion pack using eight matched 21700 cells
- 7.4 V nominal, 8.4 V fully charged
- 20 Ah / approximately 148 Wh
- Integrated 2S BMS with balancing, overcharge, undervoltage, overcurrent, short-circuit and temperature protection
- Target continuous discharge capability at least 10 A
- Target pack dimensions around 142 mm long and 44 mm thick; manufacturer must provide the complete 3D dimensions including width, wires and connector
- XT60 connector or a connector specified in the final power-board design

Candidate manufacturer reference: ASOL 2S4P 20 Ah pack. It is an OEM/B2B quote product, not a normal EU retail listing. Request a sample quote, full dimensioned drawing, BMS datasheet, cell make/model, CE/RoHS/UN38.3/MSDS documents, shipping method and confirmation that the supplied charger is compatible:
https://asolbattery.com/product/asol-21700-2s4p-7-4v-20000mah-cylindrical-li-ion-battery-pack/

**Charger candidate:** Fuyuang 8.4 V / 3 A 2S Li-ion charger, €22.70 incl. VAT, listed in stock:
https://baterija.lt/lt/ikrovikliai-ir-maitinimo-saltiniai/2124-fuyuang-2s-li-ion-bateriju-ikrovilnik-84v-3a.html

Only order this charger after the battery supplier confirms that its CC/CV output and charge current are suitable for the exact pack and BMS. The charger does not replace the pack's BMS. Provide a dedicated charge socket and prevent operation/charging configurations that the final BMS and power design do not support.

A 148 Wh battery is a reasonable target for an approximately 10-hour design goal, but **10 hours is not guaranteed**. Runtime depends on screen brightness, CPU load, radio use, conversion losses and battery ageing. Measure real average power after assembly.

## 6. Main power distribution — design requirements

The main power board is a custom PCB to be designed after the selected battery is confirmed. It must include:

- Battery input matched to the pack connector and 2S voltage range (6.0–8.4 V operating design range, subject to pack/BMS specification)
- Main fuse close to battery positive, sized from measured maximum current and wire rating
- DC-rated master switch
- Reverse-polarity protection
- Protected 5.1 V / 5 A minimum supply path for the Pi (Geekworm module or an equivalent validated design with genuine USB-C 5 A signalling)
- Separate regulated 5 V branch for the 8-inch display, rated for at least 1.5 A
- 3.3 V regulated branch for GPS/peripherals if not powered from the Pi
- Battery voltage/current measurement
- Low-voltage warning and safe Pi shutdown signal
- Locking connectors, strain relief, insulated terminals and thermal separation from the battery

Do not buy a generic buck converter and assume it can power the Pi 5. The converter and USB-C PD/source signalling must be designed and tested as a system. Test with an electronic load and multimeter at full load before connecting the Pi. Do not charge the pack while it is powering the system until the battery/BMS supplier confirms that simultaneous charge and load is supported and the power-path design handles it.

For bench testing, use a quality 12 V / 5 A (60 W) regulated supply into the Geekworm module, plus a separate suitable 5 V supply for the screen. A 27 W Pi supply is insufficient to test the Geekworm module at its full rated output.

## 7. Small parts and assembly materials

Buy only after checking workshop stock:

- 1 × short micro-HDMI-to-HDMI cable (Pi 5 to main display)
- 1 × USB-A-to-USB-C data cable (touch input)
- 1 × 12 V / 5 A regulated bench PSU for testing the Geekworm module (or equivalent >30 W input source)
- 1 × main battery fuse + holder, DC-rated and sized after current calculation
- 1 × DC-rated master switch
- 1 × panel-mount charging socket compatible with selected charger
- 1 × battery connector pair matching selected pack (XT60 candidate)
- 1 × suitable locking connector set for display and internal power branches
- Appropriate stranded copper wire, selected by current and length; separate power and signal wiring
- Heat-shrink tubing, cable ties, adhesive cable mounts, grommets and strain relief
- M2.5 screws, nuts, spacers and inserts for Pi/display mounts
- Thin insulating sheet / battery cradle and foam restraint
- 3D-printed lid display bezel, Pi/SSD mount, battery cradle and handheld enclosure

Do not choose fuse rating, wire gauge or connector rating until the final power architecture and maximum input current are calculated.

## 8. Current known price subtotal

Known EUR-priced core items (Pi, SSD kit, Active Cooler, main touchscreen listing, two Heltec V3 boards and GPS) total **€483.17 incl. VAT**. This is not the final project total. It excludes the handheld touchscreen, battery, charger, Geekworm power module, custom PCB, wiring, connectors, test PSU and shipping. The main display listing showed a stock notification; confirm availability before checkout.

## 9. Build sequence

1. Order core compute, storage, cooling, displays, LoRa and GPS only after checking live checkout prices and stock.
2. Obtain battery manufacturer's quote and full mechanical/electrical documents; confirm it fits the 58 mm lower-case depth with clearance.
3. Finalise power schematic, fuse/wire sizing, charging socket and power-path behaviour.
4. Prototype and load-test the power system before connecting the Pi.
5. Test HDMI/touch, GPS reception, LoRa link and handheld UART separately.
6. Measure actual runtime at the intended screen brightness and workload.
7. Only then print final mounts, drill the case and complete assembly.

## 10. Not in v1

RTL-SDR, separate GPS trackers, position history, large local language models and model training. Offline maps, local document search and a modest local assistant are the realistic target for a Pi 5 8 GB.

## References

- SC001 matching dimensions: https://www.chinax.com/china-enclosure/pz691235a-moisture-proof-plastic-gun-case-dust-proof-waterproof-drop-resistant.html
- Raspberry Pi 5: https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/
- Raspberry Pi SSD kit: https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/
- Raspberry Pi M.2 HAT+ installation: https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html
- Waveshare main display: https://www.waveshare.com/wiki/8DP-CAPLCD
- Waveshare handheld V2: https://docs.waveshare.com/ESP32-S3-Touch-LCD-2.8
- Heltec V3: https://heltec.org/project/wifi-lora-32-v3/
- Geekworm Pi5-5V5APD: https://wiki.geekworm.com/Pi5-5V5APD
- u-blox M10 GPS listing: https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna
- ASOL 2S4P battery candidate: https://asolbattery.com/product/asol-21700-2s4p-7-4v-20000mah-cylindrical-li-ion-battery-pack/
- Fuyuang 2S charger candidate: https://baterija.lt/lt/ikrovikliai-ir-maitinimo-saltiniai/2124-fuyuang-2s-li-ion-bateriju-ikrovilnik-84v-3a.html
- EU868 regional parameters: https://www.thethingsnetwork.org/docs/lorawan/regional-parameters/eu868/
