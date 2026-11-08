<p align="center">
  <img src="https://repository-images.githubusercontent.com/1441675652/4b2af090-6ad5-4cd4-855a-325f3766d4ec" width="180" alt="Nexum Studio application icon">
</p>

<h1 align="center">Nexum Studio</h1>

<p align="center">
  A tuning, diagnostics, logging, and quick utility workspace for VAG Group vehicles on macOS and Windows.
</p>

## Download

Download the currently available **macOS build** from the [latest release](https://github.com/tehfalcon-vw/Nexum-Studio/releases/latest). Windows downloads are temporarily withdrawn while single portable EXE packaging is validated.

Submit Bugs/Issues [Here](https://github.com/tehfalcon-vw/Nexum-Studio/issues/new?template=bug_report.md).

| Platform | Download | Requirements |
| --- | --- | --- |
| macOS | `Nexum-Studio-macOS-arm64-v1.0.0.zip` | Apple silicon, macOS 14 or newer |
| Windows x64 | Portable EXE — in preparation | Windows 11 x64, Intel or AMD processor |
| Windows ARM64 | Portable EXE — in preparation | Windows 11 ARM64 |

**macOS:** Extract the ZIP and open **Nexum Studio.app**. The application is ad-hoc signed for integrity but is not Apple-notarized. On first launch, macOS may require an explicit **Open** from Finder's shortcut menu, or **Open Anyway** in System Settings → Privacy & Security.

**Windows:** The replacement builds will be single portable EXEs containing the application, runtime, resources, and helpers. Windows downloads remain unavailable until those builds pass validation. Interface drivers are installed separately.

SHA-256 checksums are included with each release. Windows and macOS share the same editing, logging, diagnostics, utility, and programming workflows; interface drivers are platform-specific. Software and simulated tests do not establish physical vehicle or recovery qualification.

## Functions

- Open and edit BIN, ORI, and MSTRO ECU files
- Contained definition library for ME7/7.5, MED9/9.1/9.5, ME/MED17/17.5/17.5.6, EDC15/16/17, Simos 18, and DSG Transmissions.
- Scaled 1D/2D tables, synchronized secondary addresses, interactive 3D surfaces, compare, undo/redo, and change review
- ECU-aware calibration wizards and patch workflows, including user-supplied Simos BTP patches
- Gasoline and diesel aware logging with multi-parameter graphing, playback, per-cylinder knock where supported, and CSV export
- Datalog-guided **Optimize** automatically optimizes the loaded tune for safety and smoothness.
- Checksum inspection and repair for supported engine and transmission controller families
- Guided controller identification, reading, and flashing with exact profile and interface capability checks
- Gateway module discovery and module diagnostics: DTCs, identification, measuring values, diagnostic sessions, security access, coding/long coding, adaptations, basic settings, output tests, factory firmware flashing, and dataset loading where supported
- Vehicle Backup and identity-matched Restore Vehicle workflows
- Guided MQB DSG Basic Settings and wastegate relearn
- MSTRO and STT decrypt tools and Simos unlock-file preparation

## Work in Progress

- ECU Tune Simulation
- Dataset Editor
- MQB Light Configuration Utility
- MQB Drive Profile Editor
- MQB Amplifier Editor
- MQB 2Q0 Camera Patcher
- MQB Gateway Patcher
- MQB & PQ Radar Patcher
- PQ EPS Patcher
- PQ TRW450 Patcher
- PQ BCM EEPROM Editor
- VAS5054A VCI Support

## VCI support

Availability is automatically limited by the protocol and controller selected.

Windows driver requirements:

- **SM2 driver required** for Scanmatik interfaces.
- **OpenPort 2.0 driver required** for Tactrix OpenPort 2.0.
- **FTDI driver required** for the supported FTDI cable.

Drivers are installed separately and are not included with Nexum Studio.

| Interface | Supported use |
| --- | --- |
| Tactrix OpenPort 2.0 | Diagnostics, logging, identification, and supported CAN, TP2.0, ISO-TP/UDS, and K-line flashing |
| Scanmatik 2 Pro | Diagnostics, logging, identification, and supported CAN, TP2.0, and ISO-TP/UDS flashing; no K-line |
| ESP32 / Macchina A0 CAN Bridge, USB or BLE | Diagnostics, logging, identification, guided routines, and supported ISO-TP/UDS flashing; no raw-CAN TP2.0 or K-line |
| VNCI 6154A (macOS, experimental) | Supported 500 kbit request-level ISO-TP/UDS diagnostics, logging, routines, and flashing |
| Exact supported FTDI cable | CAN diagnostics, logging, and supported programming through the cable's protocols; K-line identification/programming for supported controllers. Unrelated FTDI cables are not selected. |
| Common BLE OBD adapters | Generic OBD diagnostics only |

## Safety

Nexum Studio can change safety-critical controller data. Incorrect tuning, flashing, coding, adaptations, basic settings, or output tests can damage hardware, prevent a vehicle from starting, or change vehicle behavior and functionality. Use stable battery support, confirm the exact controller and software identity, keep recoverable originals, and follow the vehicle manufacturer's workshop procedures. You are responsible for every operation performed with the application.

*This application is not affiliated with, endorsed by, or associated with Volkswagen AG or its subsidiaries.*

## Open-source material and credits

Nexum Studio includes or derives portions of its contained support from the following projects. Applicable license texts and notices are included with the application. Corresponding open-source support material is included inside the macOS bundle and the Windows archive's `OpenSource` folder.

- [MEDC17 Checksum Tool](https://github.com/ConnorHowell/medc17-checksum-tool), Connor Howell — MIT
- [ME7Sum](https://github.com/nyetlabs/ME7Sum), 360trev and nyet — BSD-style license
- [ZedSuite](https://github.com/LeZed97/ZedSuite), LeZed97 and contributors — GPL-3.0
- [VW_Flash](https://github.com/bri3d/VW_Flash), Brian Ledbetter and contributors — BSD-2-Clause
- [LZSS (bundled with VW_Flash)](https://github.com/bri3d/VW_Flash/tree/master/lib/lzss), Michael Dipperstein — LGPL-2.1-or-later
- [NefMoto ME7 ECU Flasher](https://github.com/NefMoto/NefMotoOpenSource), Nefarious Motorsports Inc and contributors — GPL-3.0
- [BinToolz](https://github.com/Switchleg1/BinToolz), SwitchLEG — BTP file-format reference; no patches or source from the project are bundled
- [PQ-flasher](https://github.com/I-CAN-hack/pq-flasher), Willem Melching — MIT
- [openport-j2534](https://github.com/bisak/openport-j2534), Biser Atanasov and contributors — GPL-3.0-or-later
- [esp32-isotp-ble-bridge](https://github.com/Switchleg1/esp32-isotp-ble-bridge), Switchleg1 — MIT
- [sm2can](https://github.com/aldoguzman97/sm2can), Aldo Guzman — MIT
- [python-can](https://github.com/hardbyte/python-can) 4.6.1, python-can contributors — LGPL-3.0-only
- [PyUSB](https://github.com/pyusb/pyusb) 1.3.1, Wander Lairson Costa and PyUSB contributors — BSD-3-Clause
- Bleak and PyObjC — MIT
- libusb — LGPL-2.1-or-later
- Brotli — MIT
- [Lucide](https://lucide.dev/), Lucide contributors — ISC; Windows application icons

## License

Nexum Studio is forever free. 
Any sale, commercial distribution, or non-credited claiming of the developer and open source material developers is strictly prohibited. 

THE SOFTWARE HERE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

*Long Live RIGHT TO REPAIR and the control of the things you own!*
