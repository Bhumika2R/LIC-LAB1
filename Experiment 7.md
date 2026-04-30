# Integrator circuit

<img width="1600" height="501" alt="image" src="https://github.com/user-attachments/assets/ba1399be-9127-4f73-a648-1f8b47f80339" />




An integrator is an op-amp circuit that produces an output proportional to the time integral of the input signal.
It is formed by replacing the feedback resistor in an inverting amplifier with a capacitor, while the input is applied through a resistor.
Due to the virtual ground at the inverting terminal, the input current flows through the capacitor, causing it to charge or discharge over time.
The output voltage is given by:

$$Vout​(t) = − (1 / RC1) ​∫ Vin​(t) dt$$

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

$$fc = 1 / (2π x R_F x C_F)$$

$$fc = 1 / (2π x  R_F x C_F)$$

$$fc = 1 / (2π × 10k × 200nF)$$

$$fc = 1 / (0.01257)$$

$$fc ≈ 79.6 Hz$$

Where,

fc → Cutoff frequency

R_F → Feedback resistor

C_F → Feedback capacitor

## Operating Region Analysis

The input frequency is 2500 Hz, while the cutoff frequency is approximately 79.6 Hz.
Since the input frequency is much higher than the cutoff frequency, the circuit operates well within the integration region.
This means the integrator behaves almost ideally, and the approximation of an ideal integrator can be safely used.

## Output Voltage Calculation

The input signal is a sinusoidal wave given by:
$$Vin(t) = Vp sin(2πft)$$

For an ideal integrator, the output is the integral of the input scaled by −1/(R₁C_F).
After substituting the input, the output becomes a cosine waveform with reduced amplitude:
$$Vout(t) = (Vp / (ωR₁C_F)) cos(ωt)$$

Here, the angular frequency is ,

$$ω = 2πf = 5000π ≈ 15708 rad/s.$$

$$Voutp = 1 / (15708 × 500 × 200 × 10⁻⁹)$$

$$Voutp = 1 / (15708 × 0.0001)$$

$$Voutp = 1 / 1.5708$$

$$Voutp ≈ 0.6366 V$$

So,

$$Vout(t) = 0.6366 cos(15708 t)$$

## Circuit Diagram

<img width="1221" height="712" alt="image" src="https://github.com/user-attachments/assets/78b43dbf-2167-414a-a155-ab8e6e4d5525" />

## Transient Analysis

<img width="1905" height="452" alt="image" src="https://github.com/user-attachments/assets/fa909621-0075-428f-8ad6-d92c2c443dd6" />

### Key Observations:

The output lags the input by 90° → characteristic of an integrator.
The amplitude is reduced due to the factor 1 / (ωRC).
The waveform is smooth and stable → indicates proper integrator operation.
Slight waveform tilt at the start may be due to initial capacitor charging (transient response).

## AC Analysis

<img width="1905" height="833" alt="image" src="https://github.com/user-attachments/assets/349c94a5-6d30-41f2-a36b-4b3f118761a2" />

### Low-frequency region :

Gain is high (~20–30 dB) → acts like an amplifier
This is due to Rf (10k) in parallel with capacitor

### Mid-frequency region:

Gain decreases with slope ≈ −20 dB/decade

### High-frequency region:

Gain flattens and then drops

### Phase plot (dotted line):

Around mid frequencies ≈ −90°

### Important Observation :

The integration region is not very wide

This happens because:

* Cutoff frequency is relatively high

* µA741 has limited gain-bandwidth product

### Unity Gain Frequency (f₍unity₎)

The unity gain frequency is the frequency at which the gain becomes 0 dB.

Theoretical f₍unity₎:

$$f₍unity₎ = 1 / (2π Rᵢₙ C_F)$$

$$f₍unity₎ = 1 / (2π × 0.5 x 10³ × 200× 10⁻⁹)$$

$$f₍unity₎ ≈ 1.59 kHz$$

## Inference 

The circuit behaves as a practical integrator with performance closely matching theoretical predictions.
At low frequencies, it acts as an amplifier with constant gain determined by the resistor ratio.
Beyond the cutoff frequency, the gain decreases at −20 dB/decade and the phase approaches 90°, confirming proper integration behavior.
The cutoff and unity gain frequencies observed in the simulation closely align with calculated values, validating the design.
Overall, the circuit demonstrates stable and accurate operation as a frequency-dependent integrator.

