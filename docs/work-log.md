# Work log

I keep this page so I can see what changed in the project.

## 31 October 2026 – compact battery redesign

Changed the battery direction after checking the case layout.

Updated:
- `README.md` – changed the battery and runtime direction.
- `BOM.csv` – changed the battery and charger rows.
- `docs/BOM.md` – changed the battery and charger plan.
- `docs/battery-pack-spec.md` – selected a supplier-built 4S1P 15 Ah Gotion 33140 pack as the design target.
- `docs/battery-and-charging.md` – removed the unconfirmed charger models.
- `docs/power-budget.md` – recalculated runtime for 192 Wh.
- `docs/electrical-design.md` – changed the battery architecture and clarified KiCad status.
- `docs/case-fit.md` – changed the battery layout.
- `hardware/power-overview/README.md` – updated the power design notes.
- `docs/work-log.md` – recorded this update.

## Current decisions

- Battery direction: supplier-made 4S1P LiFePO4 pack using four 3.2 V 15 Ah Gotion 33140 cells.
- Nominal pack: 12.8 V, 15 Ah, 192 Wh.
- Cell-only layout: about 140 × 133 × 33.2 mm before holders, BMS and wiring.
- Matched 4S LiFePO4 BMS from the pack supplier.
- Pi power: Geekworm Pi5-5V5APD.
- Screen power: Pololu D24V50F5.
- Charger: not selected until the pack supplier confirms the correct charge profile.

## Important things found

- The earlier pouch-cell idea had a large face and would leave little room for the other electronics.
- Gotion 33140 cells are listed at 3.2 V, 15 Ah and about 33.2 × 140 mm each.
- The Waveshare 8DP-CAPLCD screen is specified at about 4 W.
- These are calculations and catalogue values, not a finished build test.

## Not done yet

- Get the exact Gotion cell datasheet and a supplier-built pack quote.
- Get the pack dimensioned drawing and confirm BMS details.
- Check the available flat area inside the case.
- Confirm charger voltage/current with the pack supplier.
- Confirm exact GPS breakout and screen connector.
- Verify fuse, cable and connector ratings.
- Finish the real KiCad electrical schematic and PCB, then run ERC/DRC.
- Test real current, temperatures and runtime.

I am keeping these as open tasks instead of pretending they are finished.

## 31 October 2026 – second design review

Checked the current repository files against the current product specifications.

Found and corrected:
- `README.md` still described the old battery. It now matches the 15 Ah cylindrical-cell design.
- `docs/battery-pack-spec.md` had an unverified finished-pack size. Removed it because only the cell-only size is known.
- `docs/battery-and-charging.md` had old charger headings and a charger link even though no charger is selected. Clarified this.
- `docs/case-fit.md` had one leftover reference to the earlier battery layout.
- `hardware/power-overview/OFFGRID-Power.kicad_sch` still showed old battery labels. Updated its labels, but it remains a planning drawing, not an electrical schematic.

Important electrical finding:
- Geekworm's published test table shows that output voltage changes with its jumper setting and load. I need to test its output and cable drop carefully before deciding whether this module is suitable for the Pi 5.

Not done:
- No PCB is released or ready to manufacture.
- No battery pack or charger has been ordered.
- Need to check the real pack drawing, BMS and connector before drawing final power PCB.

## 31 October 2026 – runtime calculation correction

I found an error in the earlier runtime calculation. The 15 W and 19 W estimates did not include the 90% converter-efficiency factor. I corrected the calculation using 192 Wh × 0.8 usable energy × 0.9 converter efficiency = 138.24 Wh.

The corrected estimates are:
- 12 W average load: about 11.5 hours
- 15 W average load: about 9.2 hours
- 19 W average load: about 7.3 hours

The previous values of 10.2 hours and 8.1 hours were wrong. This is a correction to the calculation, not a change to a measured result. Nothing has been built or tested.
