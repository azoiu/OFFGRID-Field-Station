# OFFGRID power overview

Open `OFFGRID-Power.kicad_pro` and `OFFGRID-Power.kicad_sch` with KiCad.

The selected power plan is:

- 4S1P LiFePO4 pouch pack, 12.8 V, 25 Ah (supplier-built)
- matched 4S LiFePO4 BMS
- 10 A main fuse as a starting value, to be verified
- 15 A DC main switch
- Geekworm Pi5-5V5APD terminal-block version for Pi 5 USB-C 5 V/5 A
- Pololu D24V50F5 for the 5 V screen supply

The drawing is a wiring architecture diagram. It is not yet a finished electrical schematic with verified component symbols, footprints and nets. No PCB has been designed yet.

The DC/DC converter boards are bought as modules. The future PCB should only distribute power and hold the connectors/fuse/switch wiring. It should not contain a home-designed high-current switching regulator.

Do not build hardware from the drawing alone. Check the final battery datasheet, connector polarity, current, fuse and wire ratings first.
