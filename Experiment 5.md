# 1. Inverting Amplifier:

An inverting amplifier is a basic op-amp configuration where the input signal is applied to the inverting terminal (−) through an input resistor, while the non-inverting terminal (+) is grounded. A feedback resistor is connected between the output and the inverting terminal to provide negative feedback.

Due to the high gain of the op-amp and negative feedback, the inverting terminal is at virtual ground (approximately 0 V). The current flowing through the input resistor is equal to the current through the feedback resistor, since the input current to the op-amp is nearly zero.

The output voltage is given by:

$$Vout = − (Rf / R1) × Vin$$

The negative sign indicates that the output is 180° out of phase with the input (signal inversion).

The voltage gain depends only on the ratio of resistors, making it stable and predictable. The circuit also provides high input impedance (determined by Rin) and low output impedance.

Inverting amplifiers are widely used in signal processing, filtering, and analog computation due to their simplicity, linearity, and precise gain control.

## 1.1 Design & Circuit Description:

Given:

$$Vcc = 12 V$$

$$-Vcc = 0 V$$

$$Av = -5 V/V$$

Design:

$$Av = − (Rf / R1)$$

$$-5 = - (Rf / R1)$$

$$5 x R1 = Rf$$

Assuming R1 as 1 KΩ

$$Rf = 5 KΩ$$

<img width="927" height="421" alt="image" src="https://github.com/user-attachments/assets/2b98e076-dade-48b9-b87d-fb683397e7cd" />

## 1.2 Transient Analysis:

<img width="1908" height="902" alt="image" src="https://github.com/user-attachments/assets/20524bbc-4726-452c-8325-5e07d3e3601b" />

* Output peak voltage = 3 V x 5 = 15 V 

* Output waveform = sine wave from −15 V to +15 V

* The op-amp is powered with 0 V to 12 V (single supply)

* The required output (±15 V) exceeds the supply limits

As a result:

* The output cannot go below 0 V

* The output cannot exceed approximately 10–11 V (due to op-amp limitations)

* The waveform becomes clipped and distorted

## 1.3 Frequency Response:

<img width="1896" height="903" alt="image" src="https://github.com/user-attachments/assets/54a51499-d492-44ac-82c9-1ff7d29f1cf5" />



$$Gain(dB) = -57.407 dB$$

$$Gain(V/V) = 1.348 mV/V$$

$$Frequency at -3dB gain = 53.304KHz$$

$$GBP = 71.853 Hz$$

## 1.4 Inference:

Although the circuit is correctly designed for a gain of −5, the output waveform is clipped due to supply voltage limitations.
To obtain an undistorted output:
A dual power supply (±12 V) should be used, or
The input amplitude should be reduced to keep the output within the allowable range.


# 2 Voltage Follower:


A voltage follower is an op-amp configuration where the output is directly fed back to the inverting terminal (−), and the input signal is applied to the non-inverting terminal (+). This creates a unity feedback system.

In this configuration, the output voltage follows the input voltage, meaning:

$$Vout = Vin$$

The voltage gain is equal to 1 (unity gain), but the circuit plays an important role in impedance matching. It has very high input impedance and very low output impedance.

Because of this, the voltage follower is used as a buffer to isolate different stages of a circuit, preventing loading effects. It allows maximum signal transfer without loss of voltage.

Voltage followers are widely used in signal conditioning, sensor interfacing, and analog circuits where maintaining signal integrity is important.

## 2.1 Design & Circuit Description:


Given:

$$Vcc = 12 V$$

$$-Vcc = 0 V$$

$$Av = -5 V/V$$

Design:

For a voltage follower:

$$Rf = 0$$
$$R1 = ∞$$

$$Av = 1 + (Rf / R1)$$

$$Av = 1 + (0 / ∞ )$$

$$Av = 1$$

<img width="1912" height="907" alt="image" src="https://github.com/user-attachments/assets/29475cea-81a6-4a37-9aa8-08a84908a477" />

## 2.2 Transient Analysis:

<img width="1912" height="907" alt="image" src="https://github.com/user-attachments/assets/7560883f-2234-4501-a80c-21fbbb040d0c" />

### Analysis of the Waveforms:

Top Plot (V(vin))
The top waveform represents the input signal, which is a sinusoidal wave. It corresponds to the source defined as SINE(0 3 1k), meaning zero DC offset, 3 V peak amplitude, and a frequency of 1 kHz. The waveform clearly shows a peak-to-peak variation from +3 V to −3 V, confirming correct input behavior.

Bottom Plot (V(vout))
The bottom waveform represents the output signal. As expected from a voltage follower configuration, the output closely tracks the input. It is in phase with the input and maintains the same amplitude, ranging approximately from −3 V to +3 V.

Minor deviations near the peaks may be observed, which are due to non-ideal characteristics of the op-amp (such as finite gain and offset errors). These effects are typical in practical or simulated models like the µA741, even when using dual supply operation.

## 2.3 Frequency Response:

<img width="1907" height="902" alt="image" src="https://github.com/user-attachments/assets/5b8b3301-1af4-4a6c-88f4-5f790f34cb03" />

$$Gain (dB) = -107.926 dB$$

$$Gain (V/V) = 4.015 uV/V$$

$$Frequency at -3 dB gain = 53.297 kHz$$

$$GBP =0.213 Hz$$

## 2.4 Inference:

The voltage follower provides unity gain, meaning the output voltage closely follows the input voltage without amplification.
It offers very high input impedance and very low output impedance, making it ideal for impedance matching.
The circuit effectively isolates different stages, preventing loading effects on the signal source.
The output waveform remains in phase with the input and preserves the signal shape.
Minor deviations may occur due to non-ideal characteristics of the op-amp.
Overall, it acts as an efficient buffer, ensuring maximum signal transfer with minimal distortion.











