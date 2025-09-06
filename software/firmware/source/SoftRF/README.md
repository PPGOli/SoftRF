# nrf52_flash_msc_tool

## Overview

This tool is a QSPI flash diagnostic and mass storage sketch for nRF52840-based boards, including **ThinkNode M1**, SoftRF TEcho, and Seeed T1000E.  
It detects, tests, and exposes the external QSPI flash as a USB Mass Storage device, allowing you to verify hardware operation and diagnose faults.

## Features

- **Board selection** for supported hardware via `SOFTRF_BOARD_SELECT` macro.
- **JEDEC and size detection** for multiple flash chips.
- **Write/read/erase diagnostics** with verbose serial output.
- **Bad block mapping** and retry logic.
- **USB Mass Storage Class interface**: mount on host and verify function.
- **Command-line interface over Serial** for advanced diagnostics and operations.

## Supported Boards

- SoftRF TEcho (SOFTRF_BOARD_SELECT=0)
- Seeed T1000E (SOFTRF_BOARD_SELECT=1)
- ThinkNode M1 (SOFTRF_BOARD_SELECT=2)

## Usage

1. Open `nrf52_flash_msc_tool.ino` in PlatformIO or Arduino IDE.
2. Set `SOFTRF_BOARD_SELECT` at the top of the file to match your board.
3. Flash to your device.
4. Open Serial Monitor at 115200 baud.
5. Use available commands (see serial output) to probe, erase, format, and test QSPI flash.

## Troubleshooting

- If the tool reports `flash.begin() FAIL`, your QSPI chip may be faulty or not soldered.
- Use commands like `RAWID`, `PROBE`, `FULLERASE`, `MAKEFAT`, and `INFO` to diagnose.
- Devices with QSPI hardware faults may still run Meshtastic/SoftRF firmware but cannot use external flash features.

## License

MIT or your chosen license.

---

*Contributions and suggestions welcome!*