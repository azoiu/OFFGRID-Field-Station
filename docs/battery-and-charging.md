# Battery and charging

I decided to use LiFePO4 cells. I have not bought the battery yet.

## First battery idea

My first option to investigate is a **4S LiFePO4 pack (12.8 V nominal), around 20 Ah**.

This would give about 256 Wh nominal energy. The power estimate is in [power-budget.md](power-budget.md).

I have not selected a battery model because I still need to check its size. The case is small and I do not want to change it just to fit a battery.

## Parts needed

- 4S LiFePO4 battery pack with a built-in or correctly matched BMS.
- 4S LiFePO4 charger.
- Main fuse close to the battery positive terminal.
- Main switch rated for DC current.
- DC/DC converter for the Pi.
- Separate DC/DC converter for the screen.
- Proper connectors and insulated wires.

The BMS must be made for 4S LiFePO4. A BMS for 4S Li-ion is not the same thing.

## Charging from a wall socket

I want to use an external certified AC charger for a 4S LiFePO4 battery. This keeps mains voltage outside the case.

A 12.8 V LiFePO4 battery commonly uses a charge voltage around 14.2 V, but the exact value and charge current must match the battery maker's instructions. I must not choose the charger only by its plug.

## Charging in a car

For car charging I will need a DC-DC charger made for a 12 V vehicle input and a 4S LiFePO4 output. I should not connect the battery straight to the car socket or alternator.

The car charger must also have the correct current limit and protection for vehicle voltage changes.

## What I have not selected yet

- Exact battery brand and model
- Battery dimensions and weight
- BMS current rating and protections
- AC charger model
- Car DC-DC charger model
- Fuse value and wire size

I will choose these after the battery and converters are checked together.

## Safety

Do not charge a LiFePO4 pack with a lead-acid or Li-ion charger unless the battery manufacturer specifically says it is compatible.

Do not bypass the BMS. Do not test an unknown battery pack unattended. Insulate exposed battery terminals and fit the fuse close to the battery.

Do not put 230 V mains wiring inside the case for this version. Use an external certified charger.

Useful reference:
- [Victron LiFePO4 charging guidance](https://www.victronenergy.com/media/pg/Lithium_Battery_Smart/en/operation.html)

This is still a plan. The exact battery and charger must be selected before wiring or ordering.
