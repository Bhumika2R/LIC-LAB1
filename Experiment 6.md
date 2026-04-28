# Inverting Summing Amplifier :

An inverting summing amplifier combines multiple input signals using an op-amp with negative feedback.
All inputs are applied to the inverting terminal through resistors, while the non-inverting terminal is grounded, creating a virtual ground.
The input currents add at the inverting node and flow through the feedback resistor.
The output is a weighted sum of inputs and is inverted (180° phase shift).

$$Vout = −Rf × (V1/R1 + V2/R2 + ... + Vn/Rn)$$

<img width="1599" height="796" alt="image" src="https://github.com/user-attachments/assets/bb6dc910-8327-41d4-9486-a7196f17519f" />


y₂(t) = −[10x₁(t) + 2x₂(t)]

Given:
x1(t) = 0.5 V
x2(t) = 0.5V

Vout = − (Rf x V1/R1 + Rf x V2/R2)

from this R1 = 1 kΩ , R2 = 5 kΩ , Rf = 10 kΩ 

Vout = −(10 × 0.5 V + 2 × 0.5 V)

Vout = −(5 V + 1 V)

Vout = −6 V

## Circuit:

<img width="856" height="467" alt="image" src="https://github.com/user-attachments/assets/2f01d0d5-78af-40e7-855c-c2aa9796335b" />

## Input and Output Waveforms:

<img width="1915" height="431" alt="image" src="https://github.com/user-attachments/assets/c3e69551-29a9-423c-9fcb-a5e94c6c9fac" />

Analysis of the Waveforms:

V(x1) and V(x2):
Both signals are constant at 500 mV (0.5 V), indicating steady DC input sources.

V(vout):
The output is observed using the scale on the left, which ranges approximately from −5.992 V to −6.005 V.

Observation:
The red waveform lies almost exactly at −6.000 V, confirming that the output is a constant DC value of −6 V, as expected from the summing amplifier calculation.

Since the inputs (x₁ and x₂) are constant DC values, the output is also a constant DC value, resulting in a flat line.
There is no time variation in the input signals, so the output does not change with time.
If x₁ or x₂ were time-varying signals (like sine waves), the output would also vary accordingly, appearing as a scaled and inverted waveform.

## Inference:

The summing amplifier correctly produces the weighted sum of the input signals as a constant DC output.
Since the inputs are fixed DC values, the output remains steady, resulting in a flat waveform.
The circuit performs accurate addition and inversion as expected from theory.
This confirms proper operation of the op-amp and resistor network.
If time-varying inputs were applied, the output would also vary accordingly.

# Subtractor:

A subtractor is an op-amp circuit that produces an output proportional to the difference between two input signals.
It uses both inverting and non-inverting inputs with a proper resistor network to achieve subtraction.
The circuit amplifies the difference (V2 − V1) while rejecting common signals.
The circuit is widely used in signal conditioning and measurement systems for extracting small differential signals in the presence of noise.

$$Vout = (1 + Rf / R1) × (V1 × R2 / (R2 + R3)) − (V2 × Rf / R1)$$


 
