# Experiment-4
# Differential Amplifier Analysis
A MOS differential amplifier is a fundamental analog circuit used to amplify the difference between two input signals while rejecting common-mode noise. It is widely used as the input stage of operational amplifiers due to its high gain and good noise immunity.

The circuit consists of two matched NMOS transistors whose sources are connected together and biased using a constant tail current source(ISS).The input voltages V1 and V2are applied to the gate terminals, and the output is taken from the drain terminals. The drains are connected to load elements such as resistors or active loads.

When both inputs are equal, the circuit is in a balanced condition, and the tail current splits equally between the two transistors. When there is a small difference between the input voltages, the current redistributes—one transistor conducts more current while the other conducts less. This results in a voltage difference at the output, which is the amplified version of the input difference.
The amplifier operates in the saturation region, where MOSFETs act as controlled current sources. This allows small input variations to produce large output changes, resulting in high gain.

The tail current source ensures that the total current remains constant, making the circuit sensitive only to the difference between the inputs. This leads to a high Common Mode Rejection Ratio (CMRR), meaning the amplifier effectively rejects noise that is common to both inputs.

The overall gain of the amplifier depends on the transconductance gm of the MOSFETs and the load resistance RD

## Key Equations:
* ### Differential input voltage:

    Vid = V1 - V2
	​
* ### Differential gain:

    Ad = gm x RD
 
# COMPONENTS USED:

Q1 & Q2 (NMOS Transistors):These form the differential pair and are responsible for amplifying the difference between the two input voltages.

I_bias (Current Source): This provides a constant tail current to the differential pair, ensuring proper operation. It sets the total current available for both transistors and controls the amplifier’s gain and biasing.

R1 & R2 (Load Resistors): These resistors convert the drain currents of Q1 and Q2 into voltage signals.

+V (Supply Voltage): Provides the necessary power for the circuit.

Vin1 & Vin2 (Differential Inputs): These are the input signals applied to the gates of Q1 and Q2.

Vout1 & Vout2 (Differential Outputs): The output is taken from the drains of Q1 and Q2. The differential output is Vout = Vout1 - Vout2.

## Design Specification : 

* V_DD = 0.9V 
* P <= 1.5mW
* Vicm = 0V
* Vocm = 0V
* Vp = -0.7V
* Ln = 360nm
* VSS = -0.9V

# Circuit 1: Differential Amplifier with a Resistive Load:

# 1. Circuit diagram :

<img width="1882" height="925" alt="image" src="https://github.com/user-attachments/assets/098e3319-521a-459a-882e-51bb9be68aa6" />

## Circuit Analysis:

### 1.1 Calculation of Tail Current (ISS)

The tail current is calculated using the power relation:

$$P = (VDD − VSS) × ISS$$

Substitute the given values:

$$1.5 mW = (0.9 V − (−0.9 V)) × ISS$$

$$1.5 mW = 1.8 V × ISS$$

Now solve for ISS:

$$ISS = 1.5 mW / 1.8 V$$

$$ISS = 0.833 mA$$

### 1.2 Drain Current Calculation

Under balanced input conditions:

$$Vin1 = Vin2$$

The differential amplifier operates symmetrically, and the tail current splits equally between the two transistors.

$$ID1 = ID2 = ISS / 2$$

Substituting the value:

$$ID1 = ID2 = 0.833 mA / 2$$

$$ID1 = ID2 = 0.416 mA$$

### 1.3 Load Resistance Calculation

Given:

$$VOCM = 0 V$$

So,

$$Vout1 = Vout2 = 0 V$$

The output voltage equation is:

$$Vout = VDD − ID × RD$$

Substituting the values:

$$0 = 0.9 − ID × RD$$

$$ID × RD = 0.9$$

Solving for RD:

$$RD = 0.9 / ID$$

Substituting ID =0.416 mA:

$$RD = 0.9 / (0.416 × 10⁻³)$$

$$RD = 2.163 kΩ$$

### 1.4 Bias Point Calculation

Given:

$$Vin,CM = 0 V$$

So,

$$VG1 = VG2 = 0 V$$

Source Voltage

Given:

$$Vp = −0.7 V$$

Assuming:

$$VS = Vp$$

$$VS = −0.7 V$$

#### Gate-Source Voltage

$$VGS = VG − VS$$

$$VGS = 0 − (−0.7)$$

$$VGS = 0.7 V$$

#### Overdrive Voltage

Given:

$$VT ≈ 0.36 V$$

$$VOV = VGS − VT$$

$$VOV = 0.7 − 0.36$$

$$VOV = 0.34 V$$

#### Drain Voltage

From previous result:

$$Vout1 = Vout2 = 0 V$$

So,

$$VD = 0 V$$

#### Drain-Source Voltage

$$VDS = VD − VS$$

$$VDS = 0 − (−0.7)$$

$$VDS = 0.7 V$$

Saturation Condition Check

Condition:

$$VDS > VOV$$

$$0.7 > 0.34$$

Hence, both transistors operate in saturation region.

Final Bias Point

$$VG = 0 V$$
$$VS = −0.7 V$$
$$VD = 0 V$$
$$VGS = 0.7 V$$
$$VDS = 0.7 V$$

### 1.5 Width Calculation

The drain current in saturation is given by:

$$ID = (1/2) × μnCox × (W/L) × (VOV)²$$

Rearranging to find width:

$$W = (2 × ID × L) / (μnCox × (VOV)²)$$

Substituting Values

$$ID = 0.416 mA = 0.416 × 10⁻³ A$$
$$L = 360 nm = 360 × 10⁻⁹ m$$
$$μnCox = 230.6 μA/V² = 2.306 × 10⁻⁴$$
$$VOV = 0.34 V$$

Calculation

$$W = (2 × 0.416 × 10⁻³ × 360 × 10⁻⁹) / (2.306 × 10⁻⁴ × (0.34)²)$$

$$W = (299.52 × 10⁻¹²) / (2.306 × 10⁻⁴ × 0.1156)$$

$$W = (299.52 × 10⁻¹²) / (2.266 × 10⁻⁵)$$

$$W ≈ 11.235 μm$$







​

