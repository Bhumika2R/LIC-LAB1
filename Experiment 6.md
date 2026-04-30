# Inverting Summing Amplifier :

An inverting summing amplifier combines multiple input signals using an op-amp with negative feedback.
All inputs are applied to the inverting terminal through resistors, while the non-inverting terminal is grounded, creating a virtual ground.
The input currents add at the inverting node and flow through the feedback resistor.
The output is a weighted sum of inputs and is inverted (180° phase shift).

$$Vout = −Rf × (V1/R1 + V2/R2 + ... + Vn/Rn)$$

<img width="1599" height="796" alt="image" src="https://github.com/user-attachments/assets/bb6dc910-8327-41d4-9486-a7196f17519f" />


$$y₂(t) = −[10x₁(t) + 2x₂(t)]$$

Given:
$$x1(t) = 0.5 V$$
$$x2(t) = 0.5V$$

$$Vout = − (Rf x V1/R1 + Rf x V2/R2)$$

from this R1 = 1 kΩ , R2 = 5 kΩ , Rf = 10 kΩ 

$$Vout = −(10 × 0.5 V + 2 × 0.5 V)$$

$$Vout = −(5 V + 1 V)$$

$$Vout = −6 V$$

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

$$Vout = (1 + Rf / R1) × (V1 × Rb / (Ra + Rb)) − (V2 × Rf / R1)$$

$$y₃(t) = x₁(t) − 3x₂(t)$$

Given: x1(t) = 0.5 V x2(t) = 0.5V

$$Vout = (1 + Rf / R1) × (V1 × Rb / (Ra + Rb)) − (V2 × Rf / R1)$$

from this R1 = 1 kΩ , Ra = 3 kΩ , Rf = 3 kΩ , Rb = 1 kΩ

$$Vout = (1k / (3k + 1k)) × ((3k + 1k) / 1k) × 0.5 V − (3k / 1k) × 0.5 V$$

$$Vout = (1/4 × 4) × 0.5 V − (3) × 0.5 V$$

$$Vout = 0.5 V − 1.5 V$$

$$Vout = −1.0 V$$

## Circuit:

 <img width="1103" height="582" alt="image" src="https://github.com/user-attachments/assets/da7a25dd-c250-40d0-9bf9-370f35fbc11c" />

## Input and Output Waveforms:

<img width="1915" height="445" alt="image" src="https://github.com/user-attachments/assets/404645b7-c080-4779-9713-8a085ebb606c" />

Analysis of the Waveforms:

### Input Signal Analysis

V(vin1): This represents the non-inverting input x_1(t). The waveform shows a constant DC voltage maintained at 0.5 V
V(vin2): This represents the inverting input x_2(t). Similar to V(vin1), it remains at a steady DC level of 0.5 V

### Output Signal Analysis

V(vout): This represents the output of the operational amplifier circuit.
Voltage Level: The waveform is located at approximately -0.999 V, which closely matches the expected value of -1 V from the equation y₃(t) = x₁(t) − 3x₂(t)

Since the inputs (x₁ and x₂) are constant DC values, the output is also a constant DC value, resulting in a flat line.
There is no time variation in the input signals, so the output does not change with time.

## Inference:

The subtractor circuit successfully produces an output proportional to the difference between the input signals.
For equal DC inputs, the output reflects the weighted subtraction as defined by the resistor ratios.
The output remains constant, indicating a stable DC operation of the circuit.
The result closely matches the theoretical value, confirming correct circuit design and implementation.
Overall, the subtractor effectively performs accurate signal difference and amplification.
