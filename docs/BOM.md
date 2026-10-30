# OFFGRID – Bill of Materials (BOM)

> **Status:** Draft for Fallen / design-stage estimate  
> **Last updated:** 2026-10-30 (user selections incorporated)  
> **Project:** OFFGRID – Portable Field Intelligence Station  
> **Repository:** https://github.com/azoiu/OFFGRID-Field-Station

This document lists the hardware planned for **OFFGRID v1**. It distinguishes parts already owned from parts to purchase and items that still need a final selection. Prices and stock are indicative and must be rechecked before ordering. A TBD item is not a confirmed purchase.

## 1. Project scope (v1)

OFFGRID is a portable, rugged, offline-first field computer in an existing SC001 hard case. The v1 target is:

- Raspberry Pi 5 (8 GB) as the main computer.
- 8-inch HDMI capacitive touchscreen (Waveshare 8DP-CAPLCD selected as the current design choice).
- 512 GB NVMe storage.
- Offline hiking navigation with preloaded OpenStreetMap data for Slovenia.
- Local AI assistant and local document search.
- Direct LoRa text messaging with a separate handheld terminal; users can compose free text.
- Custom power-management PCB designed by the project author.
- Target battery runtime: approximately 10 hours, subject to measured power consumption and final battery choice.

**Explicitly out of v1 scope:** RTL-SDR/radio monitoring and the two GPS/LoRa tracking devices. These are reserved for a possible v2 and are not included in this BOM.

## 2. Bill of Materials

| ID | Component | Qty. | Status | Purpose / notes | Product link |
|---|---|---:|---|---|---|
| C-01 | Raspberry Pi 5, 8 GB | 1 | **To buy** | Main computer. Exact selected Farnell item: RPI5-8GB-SINGLE, order code 4256000. | [Farnell Slovenia](https://si.farnell.com/raspberry-pi/rpi5-8gb-single/raspberry-pi-5-model-b-8gb-2-4ghz/dp/4256000) |
| C-02 | 8-inch HDMI capacitive touchscreen, Waveshare 8DP-CAPLCD | 1 | **Selected** | 1280×800 IPS, 10-point capacitive touch, HDMI video and USB touch. Manufacturer lists 5 V supply and 4 W typical/maximum product power specification. | [Waveshare product](https://www.waveshare.com/8DP-CAPLCD.htm) · [Wiki/specifications](https://www.waveshare.com/wiki/8DP-CAPLCD) |
| C-03 | NVMe SSD, 512 GB, M.2 2230 or 2242, M-key | 1 | To buy – exact model TBD | Local OS, map data, AI model(s), documents and application data. Must be compatible with the selected M.2 adapter. Do not buy an M.2 2280 drive for the standard Raspberry Pi M.2 HAT+. | TBD |
| C-04 | Raspberry Pi M.2 HAT+ (standard, not Compact) | 1 | Candidate – confirm | Connects the NVMe SSD to the Pi 5 PCIe interface. Standard HAT+ supports M.2 2230 and 2242; includes ribbon cable and mounting hardware. | [Official Raspberry Pi documentation](https://www.raspberrypi.com/documentation/accessories/m2-hat-plus.html) |
| C-05 | Raspberry Pi Active Cooler | 1 | Recommended – to buy | Active cooling for Pi 5 under sustained CPU/AI workloads. Mechanical clearance with the M.2 HAT+ and custom case mount must be checked. | [Official product page](https://www.raspberrypi.com/products/active-cooler/) |
| C-06 | GNSS receiver with antenna | 1 | TBD – select module | Position for offline navigation. Prefer a Pi-compatible USB or UART receiver with a suitable antenna. Final model and antenna still need selection. | TBD |
| C-07 | LoRa radio interface for Raspberry Pi, EU 868 MHz | 1 | TBD – select | Connects the main Raspberry Pi station to the handheld terminal. Select a Pi-compatible SPI/UART/USB radio with an antenna connector. | TBD |
| C-08 | Integrated ESP32-S3 + SX1262 LoRa handheld board, EU 868 MHz | 1 | **Selected architecture – exact board TBD** | Dedicated handheld terminal with integrated ESP32 and LoRa radio. Candidate: Heltec ESP32-S3 + SX1262 board with OLED. Confirm exact 868 MHz variant, display, input method and connector before purchase. | Candidate: [Heltec ESP32-S3 + SX1262 board](https://www.hestore.eu/en/prod_10044569.html) |\n| C-09 | LoRa antennas, 868 MHz | 2 | TBD – select | One antenna for the Raspberry Pi radio and one for the handheld board. Connector type must match each selected board. | TBD |
| C-10 | Handheld terminal text input | 1 | TBD – required | The integrated board candidate includes a small display, but a practical way to enter arbitrary free-form messages is still needed (for example a compact keyboard or a suitable button-based text-entry design). | TBD |
| C-11 | Handheld terminal battery and charging/protection | 1 set | TBD | Portable power for the second LoRa terminal. Battery chemistry, capacity, charger and enclosure must be selected together. | TBD |
| C-12 | LiFePO4 battery pack for OFFGRID, protected | 1 | TBD – dimension-critical | Main battery. Must fit the case's shallow lower compartment; do not select a pack until its dimensions, BMS current rating and usable energy are checked. Approx. 10-hour runtime is a target, not yet verified. | TBD |
| C-13 | LiFePO4 charger, matched to selected pack | 1 | TBD | Correct charging profile for the final battery pack. Must match its series count and BMS requirements. | TBD |
| C-14 | DC-DC converter, battery rail to regulated 5 V | 1 | TBD – size after power budget | Supplies the Pi 5 and display. Pi 5 can require a 5 V / 5 A supply; converter must be selected for real peak load, thermal conditions and efficiency. | TBD |
| C-15 | Custom power-management PCB | 1 | **Designed by project author – not yet fabricated** | Power distribution, protection, switching and monitoring. Final schematic, PCB layout and component-level BOM will be added when designed. | Project KiCad files: TBD |
| C-16 | Main power switch, fuse, wiring and connectors | 1 set | TBD / check existing stock | Safe battery isolation and protected distribution. Fuse rating and wire gauge must follow the final battery and load calculations. | TBD |
| C-17 | Battery voltage/current monitoring | 1 | TBD / may be integrated on PCB | Allows the software to display battery state and power consumption. Exact sensing IC/module to be selected with the power PCB. | TBD |
| C-18 | HDMI and USB cables / adapters | 1 set | Partly included with display candidate | Display candidate normally includes several connection accessories; check the package contents before buying extra cables. | [Waveshare package/specifications](https://www.waveshare.com/wiki/8DP-CAPLCD) |
| C-19 | SC001 rugged hard case | 1 | **Already owned** | Existing portable enclosure. Approximate external dimensions 28 × 23 × 10 cm; internal fit and usable depth must be measured before final layout. | Existing item – no purchase |
| C-20 | 3D-printed mounts and brackets | 1 set | **Can be made in-house** | Mounting for Pi, screen, battery and terminal components. Designed and printed by the project author. | CAD files: to be added |
| C-21 | Screws, standoffs, spacers, insulation and cable management | 1 set | Partly owned / verify | Mechanical assembly and electrical insulation. Only missing quantities should be included in the final purchase list. | TBD |
| C-22 | Main keyboard | 1 | **Already owned** | User input for the main OFFGRID station only. It is not counted as the handheld terminal keyboard. | Existing item – no purchase |
| C-23 | ESP32 development boards | 2 | **Already owned – exact models unknown** | Existing generic boards. Not currently counted as the selected handheld terminal hardware; may be used for prototyping or spare modules once their exact models are identified. | Existing items – no purchase |

## 3. Owned parts and in-house work

The following are currently understood to be available and should **not** be requested as grant purchases unless the inventory changes:

- SC001 hard case.
- Two generic ESP32 development boards (exact model not yet confirmed; currently reserved for prototyping/spares).
- One main keyboard for the OFFGRID station. No handheld terminal keyboard is currently owned/confirmed.
- 3D printer and ability to manufacture custom mounts.
- Some general cables, switches and electronic components (exact inventory not yet checked).

The custom power-management PCB is planned as original project work. Its fabrication and electronic components may still need funding, but the PCB itself is not yet a completed/owned board.

## 4. Estimated cost and purchasing status

A reliable total cannot yet be stated because the battery, GNSS receiver, SSD, LoRa implementation and power electronics are not finalized. These are intentionally marked TBD rather than filled with guessed prices.

The selected Raspberry Pi 5 listing was observed on Farnell Slovenia at approximately **€151.67 excluding VAT** at the time this document was prepared. Farnell pricing, stock and delivery dates can change; confirm them on the product page before submission or purchase.

## 5. Design and safety notes

- The battery pack must have suitable protection/BMS and a charger designed for its exact chemistry and cell configuration.
- Add a correctly rated fuse close to the battery output. Final fuse, wiring and connector ratings must be based on the measured maximum current.
- The Pi 5 power rail must remain within its required voltage under peak load. A nominal “5 V” converter is not sufficient unless its current and transient performance are adequate.
- The 10-hour runtime target must be validated with a measured power budget and a real runtime test.
- Keep the battery physically restrained and electrically insulated inside the case. Avoid placing a battery in a location where it can be crushed by the lid or mounting hardware.
- LoRa frequency, transmit power, antenna and duty-cycle settings must comply with the applicable EU/Slovenian rules for the selected band.
- The final enclosure layout must be checked for heat, airflow, cable strain relief and serviceability.

## 6. Items to confirm before this becomes the final Fallen BOM

1. Exact model of the two ESP32 boards (photo or product link).
2. Whether the 8-inch display should definitely have touch. Current candidate is Waveshare 8DP-CAPLCD.
3. Whether the handheld LoRa terminal should use one of the ESP32 boards already owned, or an integrated ESP32-S3 + SX1262 board.
4. Exact keyboard(s) already owned and whether a separate keyboard is needed for the handheld terminal.
5. Maximum battery dimensions available inside the case, measured in millimetres (especially height/thickness).
6. Whether the 512 GB NVMe SSD is final, and whether you prefer a 2230 or 2242 drive.
7. Whether GNSS should connect by USB (simpler) or UART (more compact/integrated).

## 7. Items to add to the repository for a complete design/build submission

- Finalized BOM with exact manufacturer part numbers, quantities, suppliers, prices and ownership status.
- Power budget and battery runtime calculation.
- Power PCB schematic, PCB layout and fabrication files (Gerbers/BOM/CPL where applicable).
- CAD/STEP files for the enclosure mounts and mechanical assembly.
- Firmware/source code for the LoRa terminal and power monitoring.
- Assembly instructions and wiring diagram.
- Evidence of the working physical build (photos and demo video) when the build is complete.

---

**Important:** This is a transparent design-stage BOM, not a claim that all listed parts have been purchased, tested or finalized. Update each status as the design progresses.
