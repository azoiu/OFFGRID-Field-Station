# OFFGRID power overview

Open `OFFGRID-Power.kicad_pro` and `OFFGRID-Power.kicad_sch` with KiCad.

Current V1 power direction:

- supplier-built 4S1P LiFePO4 pack using four 3.2 V 15 Ah Gotion 33140 cells
- 12.8 V nominal, 15 Ah, 192 Wh
- matched 4S LiFePO4 BMS
- 10 A main fuse as a starting value, to be verified
- 15 A DC main switch
- Geekworm Pi5-5V5APD terminal-block version for Pi 5
- Pololu D24V50F5 for the screen

The battery changed from the large 25 Ah pouch-cell idea because that cell face would take almost the whole case floor. The 33140 layout should leave more room for the other parts. The complete pack dimensions are not confirmed yet.

The current schematic file is still a planning drawing, not a complete electrical schematic. No routed PCB is ready for manufacturing yet.

The future PCB should distribute power and hold connectors, fuse and switch wiring. The converter boards are bought modules. Do not design a high-current switching regulator from scratch.

Do not build hardware from the drawing alone. Check the final battery datasheet, BMS, connector polarity, current, fuse and wire ratings first.
