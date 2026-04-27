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


 
