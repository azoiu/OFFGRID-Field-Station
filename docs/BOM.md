# Parts

This is the list of parts I plan to use. Some prices are from when I checked, so they can change. The full list is in [BOM.csv](../BOM.csv).

## Parts I already have

- SINOCASE SC001 case
- Keyboard
- 3D printer
- A few ESP32 boards (without LoRa)
- Some cables and small parts

## Main station

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Raspberry Pi 5, 8 GB | 1 | €184.06 | [TME](https://www.tme.eu/si/sl/details/sc1112/raspberry-pi-mini-racunalniki/raspberry-pi/raspberry-pi-5-8gb-ram/) |
| 512 GB SSD kit with M.2 HAT+ | 1 | €138.05 | [TME](https://www.tme.eu/si/sl/details/sc1676/raspberry-pi-dodatki/raspberry-pi/512gb-ssd-kit/) |
| Pi Active Cooler | 1 | €5.26 | [TME](https://www.tme.eu/si/en/details/sc1148/raspberry-pi-acessories/raspberry-pi/raspberry-pi-active-cooler/) |
| Waveshare 8DP-CAPLCD touchscreen | 1 | €93.50 in old BOM | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec LoRa 32 V3 EU868 | 2 | €22.95 each | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GPS | 1 | €16.40 | [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna) |

The screen model on the shop page is 8DP-CAPLCD. It uses HDMI for the picture and USB for touch. The product information lists 5 V power and about 4 W. I still need to check the exact power connector and cable arrangement.

The GPS module needs the correct supply for its breakout board. The GPS chip itself and the breakout board may have different voltage requirements, so I need to check the exact board.

## Handheld

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Waveshare ESP32-S3-Touch-LCD-2.8 V2 | 1 | Not checked yet | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |
| Heltec LoRa 32 V3 EU868 | 1 | Included above | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |

The handheld will use its own battery. The Waveshare screen board and Heltec LoRa board should talk over UART.

Planned wires:

- Waveshare GPIO43 TX to Heltec GPIO48 RX
- Waveshare GPIO44 RX to Heltec GPIO47 TX
- GND to GND

I still need to check the pins on the actual boards before connecting them. The signals are 3.3 V, not 5 V.

## Battery and power

I decided to use LiFePO4. The first size I want to check is 12.8 V, 20 Ah. It gives about 256 Wh on paper, but I have not found a pack that I know will fit the case.

I will probably use separate converters for the Pi and screen:

- Pi: stable 5.1 V, at least 5 A continuous.
- Screen: 5 V, at least 2 A.
- GPS: supply according to the exact GPS board.

The wall charger should be an external LiFePO4 charger. For the car I need a DC-DC charger made for LiFePO4. I will not connect the battery directly to the car socket.

The Geekworm Pi5-5V5APD is still only a possible option. Its input is 9–24 V, so it must be checked against the chosen battery and the actual output current.

## Price

The parts that already have prices add up to **€483.17** in the old price list. Prices and stock need to be checked again. This does not include the battery, chargers, power converters, handheld screen or shipping.

## Things I still need to do

- Find a battery that fits the case.
- Choose its BMS and correct charger.
- Choose and test the DC/DC converters.
- Check the exact GPS breakout board.
- Measure real power use.
- Finish the wiring and KiCad schematic.
- Check the full layout in the case.
- Build it and test the battery life.

The power budget and battery notes are in [power-budget.md](power-budget.md) and [battery-and-charging.md](battery-and-charging.md).
