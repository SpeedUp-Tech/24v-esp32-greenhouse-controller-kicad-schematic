# Engineering Limitations

This repository contains a generated 24V ESP32 Greenhouse Controller schematic-stage draft for engineering review. It does not establish that the design is electrically correct, safe, compliant, production-ready, or suitable for fabrication.

## Project-specific review items

- Confirm the real 24 V supply range, available current, reverse-polarity events, cable inductance, TVS energy, fuse coordination, MOSFET safe operating area, regulator thermal rise, and capacitor voltage derating.
- Define the actual water pump, valve, nutrient pump, auxiliary, and lighting loads. Verify startup current, inductive energy, duty cycle, connector ratings, cable protection, flyback strategy, copper width, and fault behavior for each channel.
- Select the lighting fuse only after the fixture input capacitance, inrush current, cable, connector, and switching method are known.
- Verify the ESP32-S3 power, enable, reset, strapping pins, boot-state GPIO behavior, programming and recovery path, USB-C interface, and firmware safe states. Pumps, valves, and lights should remain off during reset, programming, brownout, and watchdog recovery.
- Treat `EC_ANALOG_IN` as an input for an already conditioned signal; this project does not contain a complete conductivity excitation and measurement circuit.
- Validate the pH probe interface for input bias current, leakage, contamination, guarding, shielding, cable motion, reference stability, filtering, calibration, and temperature compensation.
- Prove that each ADS1115 input remains inside its permitted range while the ADC is powered from 3.3 V and portions of the analog front end use 5 V, including startup, sensor disconnection, and fault conditions.
- Define the connection between `PGND`, `DGND`, and `AGND` based on the eventual PCB current paths and mixed-signal noise requirements.
- Independently verify every symbol pin number, footprint assignment, package geometry, polarity, component rating, lifecycle, and source availability before PCB layout or procurement.

## Outputs not included

The public release does not include standalone symbol or footprint libraries, a completed PCB layout, board outline, routing, vias, copper zones, Gerbers, firmware, simulation, bench validation, environmental or ingress testing, EMC or safety testing, manufacturing documentation, or production engineering sign-off.
