# OFFGRID – Portable Field Intelligence Station

OFFGRID is a rugged, portable field computer designed to work without internet or cellular service. It brings offline navigation, local tools and independent LoRa messaging into one portable case.

## Version 1 – First working build

The first version will focus on the essential features:

- **Main computer:** Raspberry Pi 5 with 8 GB RAM.
- **Storage:** 512 GB NVMe SSD.
- **Display:** 8-inch HDMI touchscreen mounted in the lid of the SC001 case.
- **Offline navigation:** GNSS receiver and preloaded OpenStreetMap data for Slovenia.
- **LoRa messaging:** Long-range text communication between the main station and a separate handheld terminal, without mobile networks.
- **Local AI and document search:** A local assistant that can search stored documents without cloud access, depending on performance and available memory.
- **Power system:** Custom power-management PCB, rechargeable battery and monitoring.
- **Portable construction:** 3D-printed mounts and a custom layout inside the rugged case.

The initial battery-life target is around 10 hours, but this is not yet confirmed. Actual runtime will be measured after the hardware is assembled.

## Version 2 – Future expansion

The following features are intentionally postponed so the first version stays achievable and affordable:

- **RTL-SDR receiver:** Software-defined radio for receiving and analysing permitted radio signals.
- **Two independent GPS/LoRa trackers:** Separate devices that transmit their locations back to OFFGRID.
- **Tracker interface:** Displaying the tracker positions and history on the main station.
- **Further radio and field-monitoring features:** Additional modules can be added after the core system is stable.

These features are not part of the Version 1 shopping list or initial build.

## Build approach

The project is being developed as a modular system. The first goal is to build and test a reliable offline computer, navigation and messaging platform. Once that works, Version 2 modules can be added without redesigning the entire device.

## Current status

The project is in the planning and hardware-selection stage. Component choices, prices and runtime estimates may change as dimensions, power consumption and compatibility are tested.
