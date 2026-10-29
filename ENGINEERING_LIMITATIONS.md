# Engineering limitations — v0.2.0

This is a schematic-stage draft for engineering review. Source files were preserved without circuit repairs. No firmware, simulation, bench, thermal, EMC, environmental, or production-validation evidence is supplied in this public package.

## Checks performed on 2026-10-29

- KiCad 10.0.5 exported all seven supplied schematic sheets successfully.
- ERC with the supplied configuration: 13 errors and 94 warnings. The errors comprise 11 `power_pin_not_driven` and 2 `pin_not_driven` findings. Warnings comprise 93 `pin_to_pin` and 1 `no_connect_dangling` findings. Some checks are disabled in the supplied project configuration; these counts are not an exhaustive electrical validation.
- CSV BOM: 52 grouped rows, 143 total reference quantities. The copied BOM and engineering files match the supplied source bytes.
- The local source PCB contains 147 footprints, 1,262 track segments, 202 vias, and 25 zones. These counts indicate geometry is present, not successful routing, manufacturability, or electrical performance. A fresh PCB DRC attempt crashed in the installed KiCad executable; no new DRC pass is claimed. The PCB is not part of this public schematic package.

## Engineering review still required

Review symbol electrical types and pin assignments, unpowered-input ERC findings, float-switch interlock behavior, startup/reset states, eFuse fault behavior, inductive suppression, regulator stability, high-current connectors and copper, isolation spacing, pH transmitter compatibility, and all actual component ratings. Validate the target load currents and temperature range with the selected supply, loads, enclosure, and wiring.

Firmware is required to implement scheduling, sequential dosing, persistent runtime accounting, recovery behavior, Modbus polling, and user controls. A hardware schematic does not establish those functions. The new pH interface expects an external RS-485 transmitter; it is not a raw-electrode input, and no built-in EC measurement is provided.

Standalone library provenance remains unresolved and those assets are excluded. Embedded schematic symbols and footprint assignment strings must still be checked before fabrication. Legacy ESP32 limitations are preserved separately in `docs/ESP32-v0.1.1-ENGINEERING_LIMITATIONS.md`.
