# Battery pack specification

## Selected V1 direction

I am changing the battery choice. The earlier 25 Ah pouch-cell idea would cover too much of the case floor.

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

This should leave more usable floor area than the earlier pouch-cell idea. It is not a confirmed fit yet. The supplier must send a dimensioned drawing and I must check the available space in the case.

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

## Cell warning

"33140"-type cells are sold with different specifications. Listed maximum discharge rates range from 1C to 5C, and listed weights are about 267–305 g. One seller lists a 33140 15 Ah cell as LMFP with a 3.6 V charge voltage. Names such as 32135, 32140 and 33140 are also mixed up in listings, and relabelled cells exist.

I need the supplier to confirm in writing:
- manufacturer name
- exact datasheet and cell model
- chemistry (LFP, matching the 4S LiFePO4 BMS)
- continuous and peak discharge ratings

I should not rely on the size or model name alone.

## Runtime estimate

The nominal pack energy is 192 Wh. Using 80% usable energy and 90% converter efficiency gives:

192 Wh × 0.8 × 0.9 = **138.24 Wh**.

- At 12 W average load: about **11.5 hours**
- At 15 W average load: about **9.2 hours**
- At 19 W average load: about **7.3 hours**

With local AI running, the average load may be about 19 W or more, so the estimate is about **7 hours or less**.

These are calculations, not measured runtime. Cold weather, battery ageing, screen brightness, CPU load and radio activity can reduce runtime. A realistic first target is about **7–9 hours**, depending on the average load.

## Charging

The charge voltage must be confirmed by the pack supplier. 14.2–14.4 V is common and gentler for a 4S LiFePO4 pack. 14.6 V is the cell maximum only if the final datasheet confirms 3.65 V per cell. The supplier must confirm the correct voltage and current for the exact pack.

For car charging, the Victron Orion-Tr Smart 12/12-18A can deliver up to 18 A. This is more than 1C (15 A) for this 15 Ah pack. Its current limit must be set much lower, for example about half of 1C, after the supplier confirms the permitted charge current. This is still to confirm.

No 230 V mains wiring goes inside the case.

## Status

This is the selected design direction, not an order. The exact cell datasheet, supplier-built pack, BMS, dimensions, connector and charger compatibility still need written confirmation before purchase.
