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



Gain(dB) = -57.407 dB

Gain(V/V) = 1.348 mV/V

Frequency at -3dB gain = 53.304KHz

GBP = 71.853 Hz

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




