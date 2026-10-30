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
| Waveshare 8-inch touchscreen | 1 | €93.50 | [Opencircuit](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding) |
| Heltec LoRa 32 V3 EU868 | 2 | €22.95 each | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |
| u-blox M10 GPS | 1 | €16.40 | [Neven7](https://www.neven7.eu/p/ublox-m10-gps-module-with-an-active-antenna) |

The screen uses HDMI for the picture and USB for touch. The GPS module needs 3.3 V.

## Handheld

| Part | Qty. | Price | Shop |
|---|---:|---:|---|
| Waveshare ESP32-S3-Touch-LCD-2.8 V2 | 1 | Not checked yet | [Waveshare](https://www.waveshare.com/product/esp32-s3-touch-lcd-2.8.htm) |
| Heltec LoRa 32 V3 EU868 | 1 | Included above | [Hexaspot](https://hexaspot.com/collections/heltec/products/heltec-wifi-lora-32-v3) |

The handheld will use the Waveshare screen and the Heltec board for LoRa. They should talk over UART.

Planned wires:

- Waveshare GPIO43 TX to Heltec GPIO48 RX
- Waveshare GPIO44 RX to Heltec GPIO47 TX
- GND to GND

I still need to check the pins on the actual boards before connecting them. The signals are 3.3 V, not 5 V.

## Battery and power

I decided to use LiFePO4, but I have not picked the battery pack yet. I still need to choose its voltage, capacity, BMS and size.

The charger has to match that battery. The Pi needs a good 5.1 V supply. The screen also needs the correct power supply, which I have to check.

The Geekworm Pi5-5V5APD is one possible option, but I have not chosen it. It needs 9–24 V input, so it might not work with the battery I choose.

## Price

The parts that already have prices add up to **€483.17**. This does not include the battery, charger, power converters, handheld screen or shipping.

## Things I still need to do

- Choose the battery and charger.
- Choose the power converters.
- Check how much power the screen needs.
- Finish the wiring and KiCad schematic.
- Check that everything fits in the case.
- Build it and test the battery life.
