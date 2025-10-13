💻 Workflow X: The Analog Control Deck (PROTOTYPE)
A custom-designed, 20-key mechanical macropad built on the Raspberry Pi Pico W, featuring precise linear and rotary analog controls for streamlined workflow optimization.

⚠️ DANGER ZONE: PROTOTYPE AND UNTESTED WARNING ⚠️
THIS IS A PROTOTYPE. BUILD AT YOUR OWN RISK.

This project is currently in the beta hardware stage. The design files have not been manufactured, assembled, or tested for fundamental functionality. We cannot guarantee the electrical connections, component footprints, or power integrity are correct. Proceed only if you are an experienced DIY user willing to troubleshoot and modify the design.

Key Features 🚀
The Workflow X is engineered for maximum precision and efficiency, focusing purely on control inputs:

20-Key Matrix: A 4-column by 5-row layout for extensive custom macros and shortcuts.

Microcontroller: Powered by the Raspberry Pi Pico W (RP2040) with full QMK Firmware support.

Linear Analog Control: PTA6043-2015DPB103 sliding potentiometer for smooth, linear input control (e.g., volume, brush size, timeline scrubbing).

Tactile Rotary Encoder: EC11E15244B2 encoder (24 detents/12 pulses) with a push-button switch for versatile control.

Per-Key RGB: SK6812mini-E addressable LEDs for vibrant, customizable lighting effects.

Clean Design: Custom PCB eliminates internal wires and features an external USB-C port.

Technical Specifications (The Build List) 🛠️
Component

Detail

Status/Notes

Microcontroller

Raspberry Pi Pico W

Processing logic and QMK interface.

Sliding Pot

PTA6043-2015DPB103

Confirmed: Connected to an ADC pin (GP26, GP27, or GP28) using AGND reference.

Encoder

EC11E15244B2

Confirmed: Assumed to have a push-button; connects via RC filter to 3 Digital GPIOs.

RGB LEDs

SK6812mini-E (20 LEDs)

Power Critical: Powered directly from 5V VBUS.

Logic Shifter

SN74AHCT1G126DBVR (or similar)

Essential for 3.3V→5V conversion on RGB data line.

USB Interface

Custom USB-C Connector

Wired to Pico W's underside test points (TP2/TP3).

Firmware and Customization (QMK) ⌨️
The QMK firmware is built based on the theoretical pinout and is not yet tested on hardware.

Analog Input: The firmware reads the sliding pot's ADC pin and maps the linear value across a control range (e.g., system volume or scroll speed).

Control Input: QMK handles the three encoder inputs (rotation A, rotation B, and push-button) and the 20-key matrix.

RGB System: The data line is routed through a logic level shifter and configured in the firmware via RGB_MATRIX_LED_COUNT.

Manufacturing and Assembly Guide 📐
PCB Files: The final Gerber files are provided in the /pcb/gerbers folder. USE AT YOUR OWN RISK.

Assembly: Designed for hand-soldering using accessible 0805 SMD components and SOD-123FL diodes.

Power Warning: Always connect the board to a USB 3.0 port or powered hub to safely supply the ~720mA current required by the LEDs.

Getting Started (Build it Yourself!)
Clone the Repository:

git clone [https://github.com/YourUsername/WorkflowX.git](https://github.com/YourUsername/WorkflowX.git)

Build & Flash:
(Detailed instructions on setting up the RP2040 toolchain and flashing the firmware will be added here.)

Customize:
Modify the keymaps/default/keymap.c file to assign your ultimate productivity shortcuts!
