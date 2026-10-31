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
| Main battery | 1 | Custom supplier-made 4S1P LiFePO4 pouch pack, 12.8 V, 25 Ah, 320 Wh |
| BMS | 1 | Matched 4S LiFePO4 BMS, supplied with pack |
| Main fuse | 1 | 10 A automotive blade fuse, verify after current test |
| Main switch | 1 | DC rated, at least 15 A at 16 V |
| Pi power module | 1 | Geekworm Pi5-5V5APD terminal-block version |
| Screen converter | 1 | Pololu D24V50F5 |
| Wall charger | 1 | External 4S LiFePO4 charger, 5 A target, final voltage matched to pack |
| Car charger | 1 | Victron Orion-Tr Smart DC-DC charger, exact model to match vehicle and battery |

Battery cell reference: [Topwell 3.2 V 25 Ah LiFePO4 pouch cell](https://www.topwellpower.com/products/5c-32v-20ah-lithium-iron-phosphate-pouch-cell).

The finished battery must be no larger than 245 × 175 × 45 mm. This is a supplier requirement, not a confirmed product size. Do not order before getting a dimensioned drawing and checking the real case.

Power module references:
- [Geekworm Pi5-5V5APD](https://wiki.geekworm.com/Pi5-5V5APD)
- [Pololu D24V50F5](https://www.pololu.com/product/2851/specs)

## Important

The battery, BMS and chargers must be bought as a matched system. The supplier must confirm the maximum charge voltage, charge temperature, discharge current and protection details. The 10 A fuse and 1.5 mm² wire are starting design values and must be verified before use.

## Still to check

- Exact GPS breakout board
- Screen power connector and polarity
- Exact battery connector
- Exact Victron car charger variant
- Internal case dimensions and mounting points
- Real power draw and fuse/wire sizing
