# Battery and charging

For V1 I choose a **supplier-made 4S1P LiFePO4 pouch-cell pack**. I will not build this large battery from loose cells at home.

## Battery target

- 12.8 V nominal
- 25 Ah
- 320 Wh
- 4 cells in series
- matched 4S LiFePO4 BMS supplied with the pack
- finished pack target: maximum 245 × 175 × 45 mm

Topwell lists a 3.2 V 25 Ah pouch cell with a size of about 239 × 155 × 6.6 mm. Four cells in series have about 26.4 mm cell thickness before compression plates, BMS, insulation and wiring.

Cell page: https://www.topwellpower.com/products/5c-32v-20ah-lithium-iron-phosphate-pouch-cell

The pack builder must send a dimensioned drawing and confirm that the cell is still available with the listed specification.

## BMS

The battery must include a 4S LiFePO4 BMS with cell balancing, overcharge and over-discharge protection, over-current and short-circuit protection, cell temperature sensors, low-temperature charge cut-off and discharge temperature protection.

## Wall charger – selected model

I choose the **Victron Blue Smart IP65 12/5 (230 V version)** as the first charger to use.

Product manual: https://www.victronenergy.com/media/pg/Blue_Smart_IP65_Charger_230V_manual/en/technical-specifications---bsc---psc.html

It has a 5 A charging mode and a Li-ion mode with 14.2 V absorption. This is only approved for our battery if the pouch-cell supplier and pack builder confirm that 14.2 V is an allowed charge setting for the exact cells and BMS. If they require another voltage, use a charger with that exact setting instead.

The charger stays outside the case. No 230 V mains wiring inside OFFGRID.

## Car charger – selected model

I choose the **Victron Orion-Tr Smart 12/12-18A isolated** as the car charger.

Product information: https://www.victronenergy.com/dc-dc-converters/orion-tr-smart

It accepts an 8–17 V input and has an adjustable output voltage. Configure its lithium profile and limit charging current to 5 A, but only after checking the pack maker's settings. It is installed in the vehicle, not inside the OFFGRID case.

## Safety

- Do not bypass the BMS.
- Do not charge below the cell maker's allowed temperature.
- Insulate and cover all battery terminals.
- Fit the main fuse close to battery positive.
- Secure the battery so it cannot move or be crushed.
- Do not use a lead-acid or Li-ion charger unless the battery maker explicitly approves the settings.

The pack is not ordered. I need the supplier's quotation, datasheet and dimensioned drawing before buying.
