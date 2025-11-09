# L293D-Motor-Driver
# Project #3: L293D Motor Driver Module

![3D Render of L293D Board](3d_renders/image_1b275e.png)

This is Project 3 of my #50BoardChallenge. This is a 2-channel H-Bridge motor driver board, designed to control the speed and direction of two DC motors.

This project was a major step up in complexity, focusing on **power management** and **heatsinking**.

## Features
* Drives two DC motors with full forward, reverse, and speed control.
* Based on the L293D H-Bridge IC.
* Dual power inputs: a `+V` (Motor) supply and a `VCC` (Logic) supply.
* On-board jumpers to enable "Always On" mode or allow for PWM speed control.
* Screw terminals for all high-current connections (power and motor outputs).

## Professional Design Rules
This board was designed to handle high currents and manage heat:

* **Heatsinking:** Used a **top-layer copper pour** connected directly to the L293D's 4 central `GND` pins to act as a heatsink and pull heat away from the chip.
* **Net Classes:** Set up three distinct Net Classes:
    * **`MOTOR_POWER` (60 mil):** For all high-current motor and `+V` traces.
    * **`LOGIC_POWER` (20 mil):** For the `VCC` and logic `GND` traces.
    * **`Default` (8 mil):** For all low-current logic signals (`IN1-4`, `EN1-2`).
* **Solid `GND` Plane:** Used a solid copper pour on the **bottom layer** for a stable, low-noise ground reference.
* **DRC:** The final design passed all Design Rules Checks with **0 errors and 0 warnings**.
