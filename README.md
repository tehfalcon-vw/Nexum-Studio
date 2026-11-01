<p align="center">
  <img src="https://repository-images.githubusercontent.com/1441675652/4b2af090-6ad5-4cd4-855a-325f3766d4ec" width="180" alt="Nexum Studio application icon">
</p>

<h1 align="center">Nexum Studio</h1>

<p align="center">
  A native macOS calibration, diagnostics, logging, and controller-service workspace for OEM Group vehicles.
</p>

## Download

Download **Nexum Studio 1.0.0** from the [latest release](https://github.com/tehfalcon-vw/Nexum-Studio/releases/latest).

- Apple silicon Mac
- macOS 14 or newer
- Production build only; no demo is published here
- SHA-256: `aa149843e860e839ecc93ee2a2a7dc696a50099b6c42c9d8d05e11c608649b3c`

The application is ad-hoc signed for integrity but is not Apple-notarized. On first launch, macOS may require an explicit **Open** from Finder's shortcut menu.

## Functions

- Open and edit BIN, ORI, and MSTRO ECU files
- Contained definition library for ME7, MED9/MED9.5, ME/MED17, EDC15/16/17, Simos 18, and supported transmission controllers
- Scaled 1D/2D tables, synchronized secondary addresses, interactive 3D surfaces, compare, undo/redo, and change review
- ECU-aware calibration wizards and patch workflows, including user-supplied Simos BTP patches
- Gasoline- and diesel-aware logging with multi-parameter graphing, playback, per-cylinder knock where supported, and CSV export
- Datalog-guided **Optimize** analysis for an existing calibration
- Checksum inspection and repair for supported engine and transmission controller families
- Guided controller identification, reading, and flashing with exact profile and interface capability checks
- Gateway module discovery and module diagnostics: DTCs, identification, measuring values, diagnostic sessions, security access, coding/long coding, adaptations, basic settings, output tests, factory file flashing, and dataset loading where supported
- Vehicle Backup and identity-matched Restore Vehicle workflows
- Guided MQB DSG Basic Settings and wastegate relearn
- MSTRO and STT conversion tools and Simos unlock-file preparation

## VCI support

Availability is automatically limited by the protocol and controller selected.

| Interface | Supported use |
| --- | --- |
| Tactrix OpenPort 2.0 | Diagnostics, logging, identification, and supported CAN, TP2.0, ISO-TP/UDS, and K-line flashing |
| Scanmatik 2 Pro | Diagnostics, logging, identification, and supported CAN, TP2.0, and ISO-TP/UDS flashing; no K-line |
| ESP32 / Macchina A0 CAN Bridge, USB or BLE | Diagnostics, logging, identification, guided routines, and supported ISO-TP/UDS flashing; no raw-CAN TP2.0 or K-line |
| Experimental VNCI 6154A | Supported 500 kbit request-level ISO-TP/UDS diagnostics, logging, routines, and flashing |
| Experimental FTDI Cable | Cable discovery and cable-only handshake test; live ECU logging and flashing are not exposed |
| Common BLE OBD adapters | Generic OBD diagnostics only |

## Safety

Nexum Studio can change safety-critical controller data. Incorrect tuning, flashing, coding, adaptations, basic settings, or output tests can damage hardware, prevent a vehicle from starting, or change vehicle behavior and functionality. Use stable battery support, confirm the exact controller and software identity, keep recoverable originals, and follow the vehicle manufacturer's workshop procedures. You are responsible for every operation performed with the application.

This application is not affiliated with, endorsed by, or associated with Volkswagen AG or its subsidiaries.

## Open-source material and credits

Nexum Studio includes or derives portions of its contained support from the following projects. Complete applicable license texts and corresponding source required by those licenses are included inside the application bundle.

- [MEDC17 Checksum Tool](https://github.com/ConnorHowell/medc17-checksum-tool), Connor Howell — MIT
- [ME7Sum](https://github.com/nyetlabs/ME7Sum), 360trev and nyet — BSD-style license
- [ZedSuite](https://github.com/LeZed97/ZedSuite), LeZed97 and contributors — GPL-3.0
- [VW_Flash](https://github.com/bri3d/VW_Flash), Brian Ledbetter and contributors — BSD-2-Clause
- [NefMoto ME7 ECU Flasher](https://github.com/NefMoto/NefMotoOpenSource), Nefarious Motorsports Inc and contributors — GPL-3.0
- [BinToolz](https://github.com/Switchleg1/BinToolz), SwitchLEG — BTP file-format reference; no patches or source from the project are bundled
- [PQ-flasher](https://github.com/I-CAN-hack/pq-flasher), Willem Melching — MIT
- [openport-j2534](https://github.com/bisak/openport-j2534), Biser Atanasov and contributors — GPL-3.0-or-later
- [esp32-isotp-ble-bridge](https://github.com/Switchleg1/esp32-isotp-ble-bridge), Switchleg1 — MIT
- [sm2can](https://github.com/aldoguzman97/sm2can), Aldo Guzman — MIT
- Bleak and PyObjC — MIT
- libusb — LGPL-2.1-or-later
- Brotli — MIT

Third-party project and product names are used only for compatibility and attribution.

## License

Nexum Studio itself is proprietary software. Distribution of the production binary does not grant a license to copy, modify, reverse engineer, redistribute, sublicense, or sell the application except where applicable law or a bundled third-party license expressly requires otherwise.
