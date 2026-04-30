# Integrator circuit

<img width="1600" height="501" alt="image" src="https://github.com/user-attachments/assets/ba1399be-9127-4f73-a648-1f8b47f80339" />

An integrator is an op-amp circuit that produces an output proportional to the time integral of the input signal.
It is formed by replacing the feedback resistor in an inverting amplifier with a capacitor, while the input is applied through a resistor.
Due to the virtual ground at the inverting terminal, the input current flows through the capacitor, causing it to charge or discharge over time.
The output voltage is given by:

$$Vout​(t) = − RC1 ​∫ Vin​(t) dt$$

The negative sign indicates a phase inversion. The circuit is widely used in waveform generation, analog computation, and signal processing applications.

## Circuit Parameters:

Parameters (Point Form)

Input Resistor: R₁ = 0.5 kΩ

Feedback Capacitor: C_F = 200 nF

Feedback Resistor: R_F = 10 kΩ

Compensation Resistor: R_comp = 476 Ω

Input Peak Voltage: Vₚ = 1 V

Input Frequency: f = 2.5 kHz

## Design Calculations
