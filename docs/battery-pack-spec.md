# Battery pack specification

I am choosing a **supplier-made 4S1P LiFePO4 pouch-cell pack** for V1. I am not going to build this high-energy pack from loose cells at home.

## Cell size that looks promising

Topwell lists a 3.2 V, 25 Ah LiFePO4 pouch cell (model 66F6Q0):

- 3.2 V nominal
- 25 Ah
- 6.6 mm maximum thickness
- 155 mm wide
- 239 mm long
- 480 g
- 2C continuous discharge listed

Product page: https://www.topwellpower.com/products/5c-32v-20ah-lithium-iron-phosphate-pouch-cell

The product table lists 25 Ah for this cell. The exact manufacturer's datasheet and current production details must be confirmed with the pack builder before payment.

## Pack I want made

Four of these cells connected in series (4S1P):

- Nominal voltage: 12.8 V
- Maximum charge voltage: 14.6 V (4 × 3.65 V, only if confirmed by the cell datasheet)
- Capacity: 25 Ah
- Nominal energy: 320 Wh
- Cell mass: about 1.92 kg before BMS, wiring and protection

The four thin pouch cells could be stacked together. Cell thickness alone is about 26.4 mm. Their face is about 239 × 155 mm. This is much more promising than the 32700 cylindrical cell idea for the case.

## Required finished pack size

The case has about 255 × 190 × 58 mm available in the lower section, based on my measurement. I want the supplier to target a complete pack no bigger than:

**245 × 175 × 45 mm**

This leaves a little space around the pack. It is still not confirmed that the actual flat area in the case is this large. I must measure between ribs, hinges and screw mounts before ordering.

The supplier must include compression plates or another cell-manufacturer-approved way to support the pouch cells. The BMS and output leads must be included in the dimensioned drawing.

## BMS and protection

Ask for a complete 4S LiFePO4 pack with:

- 4S LiFePO4 BMS, not a 4S Li-ion BMS
- balancing
- overcharge and over-discharge protection
- over-current and short-circuit protection
- cell temperature sensors
- charge cut-off below 0 °C (or the exact lower limit in the cell datasheet)
- discharge temperature protection
- at least 15 A continuous discharge capability
- 10 A maximum charge current unless the final cell datasheet and BMS allow more
- insulated terminals and protected output connector
- pack test report and cell batch information
- UN38.3 test summary for transport

The pack builder must confirm the correct charge voltage. I will not assume 14.6 V until the exact cell data is confirmed.

## Supplier to contact

Topwell Power lists the pouch cell and says it can supply custom cells. Ask them or a professional battery-pack maker to quote the complete 4S1P pack to the dimensions above.

Cell reference: https://www.topwellpower.com/products/5c-32v-20ah-lithium-iron-phosphate-pouch-cell

I have not ordered it and have not received a quote. Do not buy individual pouch cells and assemble them at home.

## Runtime estimate

At 25 Ah and 12.8 V the nominal energy is 320 Wh.

Using 80% usable energy and 90% converter efficiency:

- At 15 W average load: about 17.1 hours
- At 19 W average load: about 13.5 hours

This is only a calculation. Cold weather, battery ageing and real system load can lower it. The 10-hour target has a reasonable energy margin on paper, but needs a real test.

## Charging

Use a dedicated external 4S LiFePO4 charger. For the first design I choose a **5 A charger**, but its exact output voltage must match the final cell and BMS specification.

For charging from a car, use a DC-DC charger with a programmable LiFePO4 profile and current limit. Do not connect the pack directly to the car socket or alternator.

No 230 V mains wiring goes inside the case.
