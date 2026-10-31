# Work log

I keep this page so I can see what changed in the project.

## 31 October 2026 – power design update

Added earlier:

- `docs/power-budget.md` – first estimate of power use and battery size.
- `docs/battery-and-charging.md` – battery and charging plan.
- `docs/power-test-plan.md` – how I plan to test runtime.
- `docs/design-decisions.md` – main choices in one place.
- `docs/case-fit.md` – case and screen size notes.
- `docs/battery-pack-spec.md` – battery pack specification.
- `hardware/power-overview/README.md` – KiCad project notes.
- `hardware/power-overview/OFFGRID-Power.kicad_pro` – KiCad project.
- `hardware/power-overview/OFFGRID-Power.kicad_sch` – editable power architecture drawing.

Updated in this power-design pass:

- `README.md` – current battery and power architecture.
- `BOM.csv` – updated battery, converter and charger rows.
- `docs/BOM.md` – parts list and selected modules.
- `docs/battery-pack-spec.md` – selected 4S1P pouch-cell pack specification.
- `docs/battery-and-charging.md` – selected wall and car charger models.
- `docs/power-budget.md` – recalculated estimate for 320 Wh battery.
- `docs/electrical-design.md` – selected power modules, wiring and protection.
- `docs/case-fit.md` – corrected battery layout idea.
- `hardware/power-overview/README.md` – updated selected architecture.
- `hardware/power-overview/OFFGRID-Power.kicad_sch` – updated block diagram.

## Current decisions

- Battery: supplier-made 4S1P LiFePO4 pouch pack, 12.8 V, 25 Ah, 320 Wh.
- Battery size target: maximum 245 × 175 × 45 mm, including BMS and protection.
- BMS: matched 4S LiFePO4 BMS with balancing and temperature protection.
- Pi power: Geekworm Pi5-5V5APD terminal-block version.
- Screen power: Pololu D24V50F5.
- Main fuse: 10 A starting value, must be checked against measured current and cable size.
- Main switch: DC rated for at least 15 A at 16 V.
- Wall charger: Victron Blue Smart IP65 12/5, 14.2 V Li-ion mode only if the pack maker approves it.
- Car charger: Victron Orion-Tr Smart 12/12-18A isolated, configure for the pack and limit to 5 A.

## Important things found

- Raspberry Pi 5 needs 5.1 V. The Geekworm module gives a USB-C 5 V/5 A PD output and needs more than 30 W input for full output. Check voltage at the Pi under full load.
- Pololu D24V50F5 accepts 6–38 V and gives 5 V output. Its real current depends on cooling.
- Topwell lists a 25 Ah LiFePO4 pouch cell around 239 × 155 × 6.6 mm. Four cells in series have about 26.4 mm cell thickness before pack protection and compression.
- A 320 Wh pack gives an estimate of about 17.1 h at 15 W and 13.5 h at 19 W, using 80% usable energy and 90% converter efficiency.
- The complete battery is not confirmed to fit until the supplier gives a dimensioned drawing and I measure the real case.

## Not done yet

- Battery quote, final datasheet and dimensioned drawing.
- Measure the real flat area inside the case.
- Confirm charging voltage and charger compatibility with the exact cells.
- Confirm exact GPS breakout and screen connector.
- Verify fuse, cable and connector ratings.
- Make the final KiCad electrical schematic and PCB carrier board.
- Test real current, temperatures and runtime.

I am keeping these as open tasks instead of pretending they are finished.
