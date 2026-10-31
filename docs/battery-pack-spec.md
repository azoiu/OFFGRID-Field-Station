# Battery pack specification

## Selected V1 direction

I am changing the battery choice. The 25 Ah pouch cells are very thin, but each cell is about 239 × 155 mm. A 4S pack would cover almost the whole floor of the case. That leaves too little room for the Pi, SSD, converters and wiring.

For V1 I choose a **supplier-built 4S1P LiFePO4 pack using four 3.2 V 15 Ah Gotion 33140 cylindrical cells**.

Cell reference:
https://www.lifepo4cells.eu/en/cell/gotion-33140-15ah-3-2v-lifepo4-cell/

The listed cell data is:
- LiFePO4 chemistry
- 3.2 V nominal
- 15 Ah
- 48 Wh per cell
- 33.2 × 140 mm
- about 267 g
- 3.65 V charge voltage
- 1C maximum continuous discharge listed

Four cells in series give:
- 12.8 V nominal
- 15 Ah
- 192 Wh nominal energy
- 14.6 V maximum charge voltage if the final cell datasheet confirms 3.65 V per cell

## Why this layout

The four cylindrical cells can be arranged next to each other as a flat 2D group, rather than stacked into a tall block. The cell-only envelope is roughly 140 × 133 × 33.2 mm if arranged with all four cylinders parallel and side by side. The real pack will be larger after holders, insulation, BMS and wiring.

This should leave more usable floor area than the large pouch-cell pack. It is not a confirmed fit yet. The supplier must send a dimensioned drawing and I must measure the actual case floor, including ribs and screw posts.

There is no confirmed finished-pack envelope yet. The pack supplier must send a dimensioned drawing. The cell-only envelope does not include the BMS, insulation, holder, terminals or wiring.

## Required pack build

The pack must be assembled and tested by a battery supplier. I will not weld or assemble this high-energy pack from loose cells at home.

Ask for:
- four matched genuine Gotion 33140 15 Ah cells, or an equivalent documented cell
- 4S LiFePO4 BMS, not a 4S Li-ion BMS
- balancing
- overcharge, over-discharge, over-current and short-circuit protection
- cell temperature sensing
- low-temperature charge cut-off (charging must stop below the cell maker's permitted temperature)
- at least 10 A continuous discharge capability
- insulated terminals and a protected output connector
- cell batch details, pack test report and UN38.3 transport test summary
- exact pack dimensions and weight
- confirmation of charge voltage and maximum charge current

The final BMS current rating, fuse and charger settings must match the supplier's datasheet.

## Runtime estimate

The nominal pack energy is 192 Wh.

Using 80% usable energy and 90% converter efficiency:
- At 15 W average system load: about 10.2 hours
- At 19 W average system load: about 8.1 hours

These are calculations, not measured runtime. Cold weather, battery ageing, screen brightness, CPU load and radio activity can reduce runtime. A realistic first target is **around 8 hours**, with 10 hours possible only at a lower average load.

## Charging

Use an external charger with a LiFePO4 profile. The final charge voltage must match the exact cell and pack datasheet. A 14.2 V charger preset must not be assumed to fully charge cells specified for 14.6 V. Confirm this with the pack builder before buying a charger.

For car charging, use a programmable DC-DC charger and set its voltage and current only after the pack maker confirms them.

No 230 V mains wiring goes inside the case.

## Status

This is the selected design direction, not an order. The exact cell datasheet, supplier-built pack, BMS, dimensions, connector and charger compatibility still need written confirmation before purchase.
