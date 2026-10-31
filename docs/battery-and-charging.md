# Battery and charging

For V1 I choose a **supplier-made 4S1P LiFePO4 pack using four Gotion 33140 15 Ah cells**. I will not build this large battery from loose cells at home.

## Battery target

- 12.8 V nominal
- 15 Ah
- 192 Wh
- 4 cells in series
- matched 4S LiFePO4 BMS supplied with the pack
- finished pack dimensions: not yet confirmed

The listed Gotion cell dimensions are about 33.2 × 140 mm. Four cells arranged next to each other should have a cell-only envelope of roughly 140 × 133 × 33.2 mm. The finished pack will be larger.

Cell page: https://www.lifepo4cells.eu/en/cell/gotion-33140-15ah-3-2v-lifepo4-cell/

The pack builder must send a dimensioned drawing and confirm that the cell is still available with the listed specification.

## Cell warning

"33140"-type cells are sold with different specifications. Listed maximum discharge rates range from 1C to 5C, and listed weights are about 267–305 g. One seller lists a 33140 15 Ah cell as LMFP with a 3.6 V charge voltage. Names such as 32135, 32140 and 33140 are also mixed up in listings, and relabelled cells exist.

I need the supplier to confirm the manufacturer name, exact datasheet, chemistry (LFP, matching the 4S LiFePO4 BMS) and discharge rating in writing.

## BMS

The battery must include a 4S LiFePO4 BMS with cell balancing, overcharge and over-discharge protection, over-current and short-circuit protection, cell temperature sensors, low-temperature charge cut-off and discharge temperature protection.

## Wall charger – not selected yet

I am not locking in a charger model until the pack supplier confirms the exact charge profile.

The charge voltage must be confirmed by the pack supplier. 14.2–14.4 V is common and gentler for a 4S LiFePO4 pack. 14.6 V is the cell maximum only if the final datasheet confirms 3.65 V per cell. The supplier must confirm the correct voltage and current for this exact pack.

The charger stays outside the case. No 230 V mains wiring inside OFFGRID.

## Car charger – not selected yet

For car charging, a programmable DC-DC charger is planned. The Victron Orion-Tr Smart 12/12-18A can deliver up to 18 A. This is more than 1C (15 A) for this 15 Ah pack. Its current limit must be set much lower, for example about half of 1C, after the supplier confirms the permitted charge current. This is still to confirm.

The car charger stays in the vehicle, not inside the OFFGRID case.

## Safety

- Do not bypass the BMS.
- Do not charge below the cell maker's allowed temperature.
- Insulate and cover all battery terminals.
- Fit the main fuse close to battery positive.
- Secure the battery so it cannot move or be crushed.
- Do not use a lead-acid or Li-ion charger unless the battery maker explicitly approves the settings.
- Do not connect the wall charger and car charger at the same time.

The pack is not ordered. I need the supplier's quotation, datasheet and dimensioned drawing before buying.
