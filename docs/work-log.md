# Work log

I keep this page so I can see what changed in the project.

## 31 October 2026

Added:

- `docs/power-budget.md` – first estimate of power use and battery size.
- `docs/battery-and-charging.md` – LiFePO4 battery, wall charger and car charging plan.
- `docs/power-test-plan.md` – how I plan to test the real runtime.
- `docs/design-decisions.md` – main parts and choices in one place.
- `docs/case-fit.md` – screen and battery size check for the case.

Updated:

- `README.md` – current status and links to the new pages.
- `docs/BOM.md` – exact screen model and power parts notes.
- `docs/electrical-design.md` – separate power outputs and charging plan.
- `docs/system-block-diagram.md` – updated power flow.
- `BOM.csv` – battery and charger placeholders.

## Important things found

- The Waveshare screen in the BOM is model 8DP-CAPLCD.
- Raspberry Pi recommends a 5 V, 5 A supply for Pi 5.
- The rough system power estimate is 11–19 W. I used 15 W for the first battery calculation.
- 12.8 V, 20 Ah gives about 256 Wh nominal energy.
- Most standard 12.8 V 20 Ah battery blocks are too thick for the measured 58 mm bottom space. The battery still needs a different shape or layout.
- The 10-hour runtime is not proven. It needs a real test.

## Not done yet

- No battery has been selected or ordered.
- No final DC/DC converters have been selected.
- No final fuse, wire or connector ratings have been selected.
- No KiCad schematic or PCB has been made.
- No physical fit test or runtime test has been done.

I am keeping these as open tasks instead of pretending they are finished.
