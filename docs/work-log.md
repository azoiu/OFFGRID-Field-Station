# Work log

I keep this page so I can see what changed in the project.

## 31 October 2026 – power design update

Added:

- `docs/battery-pack-spec.md` – changed the battery plan to a supplier-made 4S1P 25 Ah pouch-cell pack.
- `hardware/power-overview/README.md` – notes for the KiCad power drawing.
- `hardware/power-overview/OFFGRID-Power.kicad_pro` – KiCad project.
- `hardware/power-overview/OFFGRID-Power.kicad_sch` – editable power architecture drawing.

Updated:

- `README.md` – selected power architecture and links.
- `docs/BOM.md` – chosen power modules and battery specification.
- `docs/electrical-design.md` – power flow, selected modules and wiring plan.
- `docs/case-fit.md` – removed the bad cylindrical-cell layout and added the pouch-cell idea.

## Current decisions

- Battery: supplier-made 4S1P LiFePO4 pouch pack, 12.8 V, 25 Ah, 320 Wh.
- Pack size target: maximum 245 × 175 × 45 mm.
- BMS: matched 4S LiFePO4 BMS with temperature protection and low-temperature charge cut-off.
- Pi power: Geekworm Pi5-5V5APD terminal-block version.
- Screen power: Pololu D24V50F5.
- Main fuse: 10 A starting value, must be checked after current measurements.
- Main switch: DC rated for at least 15 A at 16 V.
- Wall charging: external 5 A LiFePO4 charger matched to the final pack.
- Car charging: Victron Orion-Tr Smart DC-DC charger, exact model to be checked against the car.

## Important things found

- Raspberry Pi 5 needs 5.1 V and recommends the 27 W USB-C supply. The Geekworm module provides the 5 V 5 A USB-C PD handshake for battery operation.
- Geekworm says its Pi5-5V5APD needs more than 30 W input for full output.
- Pololu D24V50F5 accepts 6–38 V and gives 5 V output, with typical continuous current up to 5 A subject to cooling.
- A 25 Ah pouch cell is listed at about 239 × 155 × 6.6 mm. Four in series have about 26.4 mm cell thickness before pack protection and compression.
- The battery is still a supplier specification, not an order. The final pack drawing must fit the case.
- 320 Wh nominal energy gives about 17.1 h at 15 W and 13.5 h at 19 W using 80% usable energy and 90% converter efficiency. These are estimates only.

## Not done yet

- Supplier quote and final battery drawing.
- Verify actual flat space in the case.
- Confirm charger voltage from the final cell datasheet.
- Confirm GPS breakout voltage and screen power connector.
- Final fuse, wire and connector checks.
- Real current and runtime test.
- Final KiCad electrical schematic and PCB.

I am keeping these as open tasks instead of pretending they are finished.
