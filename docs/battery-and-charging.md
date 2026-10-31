# Battery and charging

For V1 I choose a **supplier-made 4S1P LiFePO4 pouch-cell pack**. I will not build this large battery from loose cells at home.

## Battery target

- 12.8 V nominal
- 25 Ah
- 320 Wh
- 4 cells in series
- matched 4S LiFePO4 BMS supplied with the pack

Topwell lists a 3.2 V 25 Ah pouch cell with a size of about 239 × 155 × 6.6 mm. Four cells in series have about 26.4 mm cell thickness before compression plates, BMS, insulation and wiring.

Cell page: https://www.topwellpower.com/products/5c-32v-20ah-lithium-iron-phosphate-pouch-cell

I want the supplier to make the complete pack no bigger than 245 × 175 × 45 mm. The supplier must send a dimensioned drawing. I still need to measure the flat area in the real case.

## BMS

The battery must include a 4S LiFePO4 BMS with:

- cell balancing
- overcharge and over-discharge protection
- over-current and short-circuit protection
- cell temperature sensors
- charge cut-off below 0 °C or the cell maker's stated limit
- discharge temperature protection

The pack builder must confirm the BMS current rating and the exact cell model.

## Wall charger

I choose an external 5 A LiFePO4 charger as the starting design. Its output voltage must match the final cell datasheet and BMS. Do not assume 14.6 V until the supplier confirms the cell's charge voltage.

The charger stays outside the case. No 230 V mains wiring inside OFFGRID.

## Car charging

For charging from a car, use a Victron Orion-Tr Smart DC-DC charger in the correct 12 V input/output version. It must be configured for LiFePO4 and its charge current limited to the battery maker's allowed value. Do not connect the battery directly to the car socket or alternator.

Product information: https://www.victronenergy.com/dc-dc-converters/orion-tr-smart

## Safety

- Do not bypass the BMS.
- Do not charge below the cell maker's allowed temperature.
- Insulate and cover all battery terminals.
- Fit the main fuse close to battery positive.
- Secure the battery so it cannot move or be crushed.
- Do not use a lead-acid or Li-ion charger unless the battery maker explicitly approves it.

The pack is not ordered. I need the supplier's quotation, datasheet and dimensioned drawing before buying.
