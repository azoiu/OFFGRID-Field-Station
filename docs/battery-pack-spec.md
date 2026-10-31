# Battery pack idea

I found a cell size that could solve the space problem. This is a design proposal, not an order yet.

## The cells

One possible cell is the Akkuplus LFP32700 LiFePO4 cell:

- 3.2 V nominal
- 6 Ah
- about 70 × 32 mm
- about 132 g
- product page: https://akkuplus.de/Akkuplus-LFP32700-32700-32-Volt-6000mAh-LiFePO4

The supplier says that the cells must be used with protection electronics. The exact cell datasheet and batch details must be checked before a pack is made.

## Proposed pack: 4S4P

I think the best target is **4S4P**, made by a battery pack supplier.

- 4 cells in series = 12.8 V nominal
- 4 cells in parallel = 24 Ah
- energy = about 307 Wh
- 16 cells total
- cell mass alone = about 2.1 kg

This is more capacity than 4S3P. It gives us a better chance of reaching 10 hours when the system is using more power.

At 15 W average, a rough estimate with 80% usable battery energy and 90% converter efficiency is about 14.7 hours. At 19 W it is about 11.6 hours. These are calculations, not tested runtime. Cold weather, battery ageing and the real power draw can reduce it.

## Possible physical layout

The cells are cylindrical. A supplier could lay them with their long axes parallel to the bottom of the case. The cell group could be arranged as a 4 by 4 grid:

- about 130 × 130 mm footprint
- about 32.5 mm cell diameter in the vertical direction
- about 70 mm cell length along the bottom

This is only the cell geometry. The BMS, insulation, busbars, wires and case need extra space. The supplier must confirm the final outer dimensions. Our available space is about 255 × 190 × 58 mm, but the real flat area still needs measuring.

## What I want the supplier to build

Please quote a complete pack with:

- Chemistry: LiFePO4
- Configuration: 4S4P
- Cells: 32700, 3.2 V, 6 Ah, same model and same production batch
- Nominal voltage: 12.8 V
- Capacity: 24 Ah
- BMS: 4S LiFePO4, balancing and over/under-voltage, over-current, short-circuit and temperature protection
- Low-temperature charge cut-off
- Continuous discharge rating: at least 15 A (supplier to confirm)
- Main fuse close to pack positive
- Insulated enclosure or proper insulation and mechanical cell holder
- Output connector and separate charging connection
- Outer dimensions target: maximum 200 × 160 × 48 mm if possible
- Ask for UN38.3 transport test summary and cell datasheets

The 15 A target gives margin over the expected system current, but the final value must be checked with the selected converters and measured startup current.

## Supplier options to ask

- EEMENTOR ENERGY: https://energy.eementor.co/collections/battery-pack — says it builds packs to order and offers 32700 LiFePO4 cells, BMS and custom dimensions.
- EEMENTOR 32700 cell details: https://energy.eementor.co/products/lfp32700-32700-lifepo4-cell
- Akkuplus single cell: https://akkuplus.de/Akkuplus-LFP32700-32700-32-Volt-6000mAh-LiFePO4

I have not received a quote or confirmation that the pack will fit. Do not order cells yet.

## Important

I do not want to solder or spot-weld this large pack at home. A supplier should assemble, insulate and test it. We can design the mounting bracket and connect the finished protected pack to OFFGRID after checking its datasheet.

The charger must match the final pack instructions. Do not assume that every 12.8 V LiFePO4 pack uses the same charge voltage.
