# Battery and charging

I decided to use LiFePO4 cells. I have not bought the battery yet.

## First capacity target

The first capacity target to investigate is around **12.8 V and 20 Ah** (about 256 Wh). This is based on the power estimate in [power-budget.md](power-budget.md). With the current 11–19 W load estimate, 20 Ah may be enough for 10 hours at the lower and middle part of the range, but it may be slightly short at the high end. A real test is needed.

But there is a problem with the case. I measured only about 58 mm usable depth in the bottom part. Most ready-made 12.8 V 20 Ah battery blocks are around 75–80 mm thick, so they will not fit flat in the bottom. For example, the ECTIVE LC 20L datasheet gives dimensions of 180 × 75 × 170 mm.

So I should not order a normal battery block yet.

## Possible way to make it fit

I need to look for a flat 4S LiFePO4 pack that is made to fit the case. One option could be a supplier-made pack using matched cells arranged flat, with a proper 4S LiFePO4 BMS.

I should not build a high-capacity lithium pack from loose cells myself without the right equipment and experience. The pack needs correct cell matching, mechanical support, insulation, fusing and a suitable BMS.

The pack must fit inside the measured space with room for wires, connectors and insulation. It also needs to be fixed so it cannot move if the case is carried.

LiFePO4 packs commonly must not be charged below 0 °C unless the pack has a suitable low-temperature charging system. Since OFFGRID may be used outside in winter, I need to check the selected pack's charge temperature range. The BMS should stop charging when the cells are too cold.

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

The charge voltage must match the exact battery maker's instructions. Some 12.8 V LiFePO4 batteries specify 14.2 V and some specify 14.6 V, so I must not pick a charger from the nominal voltage alone.

## Charging in a car

For car charging I will need a DC-DC charger made for a 12 V vehicle input and a 4S LiFePO4 output. I should not connect the battery straight to the car socket or alternator.

The car charger must also have the correct current limit and protection for vehicle voltage changes.

## What I have not selected yet

- Exact battery pack and dimensions
- BMS current rating and protections
- AC charger model
- Car DC-DC charger model
- Fuse value and wire size

## Safety

Do not charge a LiFePO4 pack with a lead-acid or Li-ion charger unless the battery manufacturer specifically says it is compatible.

Do not bypass the BMS. Do not test an unknown battery pack unattended. Insulate exposed battery terminals and fit the fuse close to the battery.

Do not put 230 V mains wiring inside the case for this version. Use an external certified charger.

Useful references:
- [ECTIVE LC 20L battery datasheet](https://www.ective.de/mediafiles/Datenblatt/ective/LC-BT/Ective-LC-20L-BT-EN.pdf)
- [Victron LiFePO4 charging guidance](https://www.victronenergy.com/media/pg/Lithium_Battery_Smart/en/operation.html)

This is still a plan. The exact battery and charger must be selected before wiring or ordering.
