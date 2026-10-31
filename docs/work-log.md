# Work log

I keep this page so I can see what changed in the project.

## 31 October 2026

Added:

- `docs/power-budget.md` – first estimate of power use and battery size.
- `docs/battery-and-charging.md` – LiFePO4 battery, wall charger and car charging plan.
- `docs/power-test-plan.md` – how I plan to test the real runtime.
- `docs/design-decisions.md` – main parts and choices in one place.
- `docs/case-fit.md` – screen and battery size check for the case.
- `docs/battery-pack-spec.md` – proposed 4S4P pack using 32700 LiFePO4 cells and supplier requirements.
- `hardware/power-overview/README.md` – notes about the KiCad drawing.
- `hardware/power-overview/OFFGRID-Power.kicad_pro` – KiCad project file.
- `hardware/power-overview/OFFGRID-Power.kicad_sch` – editable power architecture block drawing.

Updated:

- `README.md` – new battery proposal and KiCad links.
- `docs/BOM.md` – battery proposal and supplier links.
- `docs/battery-and-charging.md` – changed the capacity target to 24 Ah.
- `docs/case-fit.md` – added the possible 32700 cell layout.
- `docs/electrical-design.md` – updated the power plan and KiCad status.

## Important things found

- The Waveshare screen in the BOM is model 8DP-CAPLCD.
- Raspberry Pi recommends a 5 V, 5 A supply for Pi 5.
- The rough system power estimate is 11–19 W. I used 15 W for the first battery calculation.
- A 4S4P pack using 16 cells of 3.2 V and 6 Ah would be 12.8 V, 24 Ah and about 307 Wh nominal.
- Akkuplus lists a 32700 LiFePO4 cell at about 70 × 32 mm and 132 g. A 4 by 4 layout could fit the case footprint on paper if the cells lie on their sides.
- The battery layout is not confirmed. The BMS, insulation, wiring and enclosure need extra space. A supplier must confirm final dimensions and safety.
- The 10-hour runtime is still not proven. It needs a real test.

## Not done yet

- No battery has been ordered. The proposed 4S4P pack needs a supplier quote and dimensional drawing.
- No final DC/DC converters have been selected.
- No final fuse, wire or connector ratings have been selected.
- The KiCad file is only a block diagram. It is not a finished electrical schematic and there is no PCB yet.
- No physical fit test or runtime test has been done.

I am keeping these as open tasks instead of pretending they are finished.
