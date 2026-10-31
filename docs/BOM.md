# Parts

This is the current parts plan. Prices can change. The full list is in [BOM.csv](../BOM.csv).

## Parts I already have

- SINOCASE SC001 case
- Keyboard
- 3D printer
- A few ESP32 boards (without LoRa)
- Some cables and small parts

## Main station

| Part | Qty. | Status |
|---|---:|---|
| Raspberry Pi 5, 8 GB | 1 | Planned |
| 512 GB SSD kit with M.2 HAT+ | 1 | Planned |
| Pi Active Cooler | 1 | Planned |
| Waveshare 8DP-CAPLCD touchscreen | 1 | Planned |
| Heltec LoRa 32 V3 EU868 | 1 | Planned |
| u-blox M10 GPS breakout | 1 | Planned; exact breakout supply still needs checking |

## Handheld

| Part | Qty. | Status |
|---|---:|---|
| Waveshare ESP32-S3-Touch-LCD-2.8 V2 | 1 | Planned |
| Heltec LoRa 32 V3 EU868 | 1 | Planned |
| Separate handheld battery | 1 | To be selected |

## Battery and power – selected architecture

| Part | Qty. | Choice |
|---|---:|---|
| Main battery | 1 | Supplier-made 4S1P LiFePO4 pack, 12.8 V, 15 Ah, 192 Wh |
| BMS | 1 | Matched 4S LiFePO4 BMS, supplied with pack |
| Main fuse | 1 | 10 A automotive blade fuse, verify after current test |
| Main switch | 1 | DC rated, at least 15 A at 16 V |
| Pi power module | 1 | Geekworm Pi5-5V5APD |
| Screen converter | 1 | Pololu D24V50F5 |
| Wall charger | 1 | LiFePO4 charger to select after pack maker confirms charge profile |
| Car charger | 1 | Programmable DC-DC charger, settings to be confirmed |

Battery cell reference: [Gotion 33140 3.2 V 15 Ah LiFePO4 cell](https://www.lifepo4cells.eu/en/cell/gotion-33140-15ah-3-2v-lifepo4-cell/).

The finished battery dimensions are not known. The supplier must provide a dimensioned drawing. Do not order before checking the drawing against the available case space.

Power module references:
- [Geekworm Pi5-5V5APD](https://wiki.geekworm.com/Pi5-5V5APD)
- [Pololu D24V50F5](https://www.pololu.com/product/2851/specs)
- [Victron Blue Smart IP65 12/5](https://www.victronenergy.com/media/pg/Blue_Smart_IP65_Charger_230V_manual/en/technical-specifications---bsc---psc.html)
- [Victron Orion-Tr Smart 12/12-18A](https://www.victronenergy.com/media/pg/Orion-Tr_Smart_DC-DC_Charger_-_Isolated/en/specifications.html)

## Important

The battery, BMS and chargers must be treated as one matched system. The supplier must confirm the maximum charge voltage, charge temperature, discharge current and protection details. The 10 A fuse and wire size are starting design values and must be verified before use.

## Still to check

- Exact GPS breakout board
- Screen power connector and polarity
- Exact battery connector
- Actual internal case dimensions and mounting points
- Real power draw and fuse/wire sizing
- Final charger current and charge voltage
