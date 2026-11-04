# Smart Grid Fault Detector

An open-source hardware fault detector designed to monitor voltage and current in smart grid applications. Powered by an ATmega328P microcontroller, this board detects grid anomalies and isolates loads using a hardware-latched P-Channel MOSFET load switch, ensuring microsecond-level response times to overcurrent or fault conditions.

## Key Features

* **Microcontroller:** ATmega328P (DIP-28) for ADC polling, threshold evaluation, and status indication.
* **Precision Current Sensing:** Texas Instruments INA180A1 current sense amplifier (20V/V gain) paired with a 50mΩ shunt resistor for accurate high-side load monitoring.
* **Hardware Fault Latching:** A CD4013 Dual D-Type Flip-Flop provides instantaneous hardware latching to cut power immediately upon a fault, bypassing MCU processing delays.
* **Robust Load Switching:** An AO3407 P-Channel MOSFET driven by an MMBT2222A NPN transistor reliably toggles the load.
* **Transient Protection:** Input and output nodes are protected by SMBJ16A TVS diodes and BAT54S dual Schottky barrier diodes.
* **Power Delivery:** Accepts 12V DC input, regulated down to clean 5V logic via an onboard AMS1117-5.0 LDO.

## Hardware Specifications

| Component | Specification |
| :--- | :--- |
| **Logic Voltage** | 5V DC |
| **Input Voltage** | 12V DC (Nominal) |
| **MCU** | Microchip ATmega328P-P |
| **Current Amp** | INA180A1 (SOT-23-5) |
| **Current Shunt** | 0.05Ω (SMD 0805) |
| **Load Switch** | AO3407 P-MOSFET |
| **Connectors** | 2-pin Screw Terminals (Power IN, Load OUT) |
| **EDA Tool** | KiCad 10.0 |

## Repository Structure

* `/hardware` - KiCad project files (`.pro`, `.sch`, `.kicad_pcb`).
* `/docs` - Schematic PDFs, 3D PCB renders, and layer routing diagrams.

## Status Indicators

* **D1 (LED):** General status / MCU driven.
* **D2 (LED):** Fault state indicator.
* **SW1 (Tactile Pushbutton):** Manual fault reset switch to clear the CD4013 latch and restore load power.

## License
This hardware design is released under the [CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S) / MIT License - *Update as needed*].