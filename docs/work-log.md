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
- Pi power: Geekworm Pi5-5V5APD terminal-block version.
- Screen power: Pololu D24V50F5.
- Charger: not selected until the pack supplier confirms the correct charge profile.

## Important things found

- The 25 Ah pouch cell face was about 239 × 155 mm. Four in series would leave little room for the other electronics.
- Gotion 33140 cells are listed at 3.2 V, 15 Ah and about 33.2 × 140 mm each.
- A 192 Wh pack gives about 10.2 h at 15 W and 8.1 h at 19 W, assuming 80% usable energy and 90% converter efficiency.
- The Waveshare 8DP-CAPLCD screen is specified at about 4 W.
- These are calculations and catalogue values, not a finished build test.

## Not done yet

- Get the exact Gotion cell datasheet and a supplier-built pack quote.
- Get the pack dimensioned drawing and confirm BMS details.
- Measure the real flat area inside the case.
- Confirm charger voltage/current with the pack supplier.
- Confirm exact GPS breakout and screen connector.
- Verify fuse, cable and connector ratings.
- Finish the real KiCad electrical schematic and PCB, then run ERC/DRC.
- Test real current, temperatures and runtime.

I am keeping these as open tasks instead of pretending they are finished.
