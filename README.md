## Project Overview
This project is an analog bass guitar pedal distortion circuit. It utilizes a dual-path architecture to solve the common issue of low-end loss in bass distortion pedals. By splitting the signal into a "Clean" path and a "Dirty" path, the user can blend the two signals to maintain the fundamental low-frequency "thump" of the bass while adding harmonic grit from the distortion stage.

The circuit design was validated using OrCAD PSpice simulations to ensure frequency response stability across the audible bass spectrum.

## Circuit Architecture
The design is built around the LM358 dual operational amplifier and consists of three primary stages:

1. **Splitter/Buffer Stage**: The input signal is buffered to prevent impedance loading of the instrument pickups and split into two parallel paths.
2. **Distortion Path**: A non-inverting gain stage with hard-clipping diodes. This stage includes a high-cut filter (low-pass) to remove harsh high-frequency artifacts typical of distortion.
3. **Blending and Output Stage**: A passive mixer utilizing a linear potentiometer allows the user to sweep between the two signals. A final master volume control sets the overall output level.

## Technical Specifications
* **Operating Voltage**: 9V DC (Battery or regulated power supply).
* **Active Component**: LM358 Dual Op-Amp.
* **Control Layout**:
    * **Gain**: Adjusts the intensity of the distortion (Logarithmic A500K).
    * **Blend**: Balances Clean and Dirty signals (Linear B100K).
    * **Volume**: Sets the final output level (Logarithmic A100K).
* **Frequency Response**: Designed to remain flat down to 31Hz (Low B on a 5-string bass).

## Simulation Data
Included in the repository are OrCAD PSpice simulation files:
* **AC Sweep**: Analyzes the frequency response. The clean path maintains a flat response from 10Hz to 20kHz, while the distortion path features a tuned mid-frequency hump for better mix penetration.
* **DC Sweep**: Visualizes the clipping threshold of the diode stage.
