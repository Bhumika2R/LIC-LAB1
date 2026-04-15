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

* Q1 & Q2 (NMOS Transistors):These form the differential pair and are responsible for amplifying the difference between the two input voltages.

* I_bias (Current Source): This provides a constant tail current to the differential pair, ensuring proper operation. It sets the total current available for both transistors and controls the amplifier’s gain and biasing.

* R1 & R2 (Load Resistors): These resistors convert the drain currents of Q1 and Q2 into voltage signals.

* +V (Supply Voltage): Provides the necessary power for the circuit.

* Vin1 & Vin2 (Differential Inputs): These are the input signals applied to the gates of Q1 and Q2.

* Vout1 & Vout2 (Differential Outputs): The output is taken from the drains of Q1 and Q2. The differential output is Vout = Vout1 - Vout2.

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

* #### Source Voltage

Given:

$$Vp = −0.7 V$$

Assuming:

$$VS = Vp$$

$$VS = −0.7 V$$

* #### Gate-Source Voltage

$$VGS = VG − VS$$

$$VGS = 0 − (−0.7)$$

$$VGS = 0.7 V$$

* #### Overdrive Voltage

Given:

$$VT ≈ 0.36 V$$

$$VOV = VGS − VT$$

$$VOV = 0.7 − 0.36$$

$$VOV = 0.34 V$$

* #### Drain Voltage

From previous result:

$$Vout1 = Vout2 = 0 V$$

So,

$$VD = 0 V$$

* #### Drain-Source Voltage

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

## 2. DC Analysis:

 <img width="1910" height="847" alt="image" src="https://github.com/user-attachments/assets/5a15f523-7bf2-415f-b5bf-56578fbc08ff" />



By varying width:

* ### W1 = W2 =19.978 µm → Id = 0.416 mA

## 3. Input Common Mode Range (ICMR):

Input Common Mode Range (ICMR)

The input common-mode range is the range of input voltage over which all transistors in the differential amplifier remain in saturation and operate properly.

### 3.1 Minimum Input Common Mode Voltage

For proper operation, the NMOS transistors must remain ON:

Condition:
$$VGS ≥ VT$$

We know:
$$VGS = VICM − VS$$

So,

$$VICM(min) = VS + VT$$

Substituting values:
$$VS = −0.7 V$$
$$VT = 0.36 V$$

$$VICM(min) = −0.7 + 0.36$$

$$VICM(min) = −0.34 V$$

### 3.2 Maximum Input Common Mode Voltage

To keep the transistors in saturation:

Condition:
$$VDS ≥ VOV$$

Given:
$$VD = 0 V$$
$$VS = −0.7 V$$

$$VDS = VD − VS = 0 − (−0.7) = 0.7 V$$

Now,

$$VICM(max) = VD + VT$$

Substituting:

$$VICM(max) = 0 + 0.36$$

$$VICM(max) = 0.36 V$$

Final Range

$$−0.34 V ≤ VICM ≤ 0.36 V$$

 ## 4. Output Common Mode Range

The output common mode voltage range ensures that all transistors remain in saturation.

Maximum Output Voltage:

$$VOCM(max) <= VDD$$
$$VOCM(max) = 0.9 V$$

### 4.1 Minimum Output Voltage:

Condition: VDS >= VOV

$$VDS = VD - VS$$

At saturation limit:

$$VD - VS = VOV$$

So,

$$VD = VS + VOV$$

Since VD = VOCM(min):

$$VOCM(min) = VS + VOV$$

Substitute values:

$$VS = -0.7 V$$
$$VOV = 0.34 V$$

$$VOCM(min) = -0.7 + 0.34$$
$$VOCM(min) = -0.36 V$$

Final Range:

$$-0.36 V <= VOCM <= 0.9 V$$

## 5. Differential Input Voltage Range (Linear Region)

The differential amplifier operates linearly only when both transistors remain in saturation and the current is nearly equally shared.

Condition for linear operation:

$$|Vid| <= 2 * VOV$$

Substituting value:

$$VOV = 0.34 V$$

$$|Vid| <= 2 * 0.34$$

$$|Vid| <= 0.68 V$$

Final Range:

$$-0.68 V <= Vid <= 0.68 V$$

## 6. Transient Analysis and Linearity Observation

The linear behavior of the differential amplifier is verified using transient analysis.

Condition for Linearity

$$|Vid| < 2 * VOV$$

Using a refined condition:

$$2 * VOV ≈ 1.414 * VOV$$

Substituting value:

$$VOV = 0.34 V$$

$$2 * VOV ≈ 1.414 * 0.34$$

$$2 * VOV ≈ 0.48 V$$

* ### Case 1: Linear Region

Input applied:

$$Vid = 200 mV$$

Since:

$$200 mV < 0.48 V$$

The amplifier operates in the linear region.

<img width="1910" height="921" alt="image" src="https://github.com/user-attachments/assets/27498cc9-4c7b-4319-9a4d-2b21652174d5" />

* ### Case 2: Non-Linear Region

Input applied:

$$Vid = 700 mV$$

Since:

$$700 mV > 0.48 V$$

The amplifier operates in the non-linear region.

<img width="1907" height="912" alt="image" src="https://github.com/user-attachments/assets/99169ebc-01e3-416e-9c84-5a1d17f1399f" />

## 7. Comparison of Linear and Non-Linear Operation

| Parameter              | Case 1: Linear Region | Case 2: Non-Linear Region |
|------------------------|----------------------|----------------------------|
| Condition              | Vid < 2 * VOV        | Vid > 2 * VOV              |
| Input (Vid)            | 200 mV               | 700 mV                     |
| Output waveform        | Sinusoidal           | Distorted / Clipped        |
| Gain                   | Constant             | Reduced / Non-linear       |
| Transistor operation   | Both in saturation   | One enters cutoff          |
| Current distribution   | Equal sharing        | Current shifts to one side |

## 8. Theoretical Gain


Assume channel length modulation:

$$λ = 0.1 V⁻¹$$

### 8.1 Output Resistance

The output resistance of each MOSFET is:

$$ro = 1 / (λ × ID)$$

Substituting values:

$$ID = 0.416 mA = 0.416 × 10⁻³ A$$

$$ro = 1 / (0.1 × 0.416 × 10⁻³)$$

$$ro = 24 kΩ$$

### 8.2 Effective Output Resistance

Since two transistors are present:

$$ro_eff = ro1 || ro2$$

$$ro_eff = 24 kΩ || 24 kΩ$$

$$ro_eff = 12 kΩ$$

### 8.3 Transconductance

$$gm = (2 × ID) / VOV$$

$$gm = (2 × 0.416 × 10⁻³) / 0.34$$

$$gm ≈ 2.44 mS$$

### 8.4 Total Output Resistance

$$Rout = RD || ro_eff$$

$$Rout = 2.163 kΩ || 12 kΩ$$

$$Rout ≈ 1.83 kΩ$$

Final Values

$$ro = 24 kΩ$$
$$ro_eff = 12 kΩ$$
$$gm ≈ 2.44 mS$$
$$Rout ≈ 1.83 kΩ$$

## 9. Simulated Gain

### 9.1 Input Signal Parameters

Measured Peak-to-Peak Values

$$Vin(p-p) = 100 mV − (−100 mV) = 200 mV$$

$$Vout(p-p) = 350 mV − (−350 mV) = 1.03 V$$

Voltage Gain

$$Av = Vout(p-p) / Vin(p-p)$$

$$Av = (1.03) / (200 × 10^-3)$$

$$Av = 5.15 V/V$$

### 9.2 Gain in dB

$$Av(dB) = 20 log10(Av)$$

$$Av(dB) = 20 log10(5.15)$$

$$Av(dB) = 14.23 dB$$

## 10. Differential Gain

$$Ad = gm × Rout$$

$$Ad = 2.44 × 10^-3 × 1.83 × 10^3$$

$$Ad ≈ 4.47$$

### 10.1 Gain in dB

$$Ad(dB) = 20 log10(Ad)$$

$$Ad(dB) = 20 log10(4.47)$$

$$Ad(dB) ≈ 13 dB$$

## 11. AC Analysis:

<img width="1915" height="922" alt="image" src="https://github.com/user-attachments/assets/9132b14e-c30b-46d8-93e7-b7b01f7ee6a3" />

### 11.1 Midband Gain

From AC simulation:

$$Av = 16.152 dB$$

−3 dB Gain

$$Av − 3 =16.152  − 3$$

$$Av − 3 = 13.152 dB$$

### 11.2 Cutoff Frequencies

Lower cutoff frequency:

$$fL = 0 Hz$$

* Upper cutoff frequency:

$$fH = 5.594 GHz$$

* Bandwidth

Bandwidth is defined as:

$$BW = fH − fL$$

$$BW = 5.594 − 0$$

$$BW = 5.594 GHz$$

## 12. Unity Gain Bandwidth (UGB)

Since the 0 dB crossing point is not visible in the AC plot, the unity gain bandwidth cannot be measured directly.

So, it is estimated using the relation:

$$UGB = Av × BW$$

Substituting Values

$$Av = 5.15$$
$$BW = 5.627 GHz$$

$$UGB =  5.15 × 5.627 GHz$$

$$UGB = 28.106 GHz$$

## 13. Inference: 

The MOS differential amplifier with a resistive load successfully amplifies the difference between two input signals while rejecting common-mode noise. The circuit operates properly when both transistors remain in saturation, ensuring stable biasing and linear amplification.

From the analysis, it is observed that for small differential input voltages, the amplifier behaves linearly with constant gain. As the input increases beyond the linear range, the circuit enters the non-linear region, leading to distortion and unequal current distribution.

The gain of the amplifier depends on the transconductance (gm) and the load resistance (RD). Due to the presence of channel length modulation, the output resistance also affects the overall gain.

The simulated results closely match the theoretical calculations, with slight variations due to non-ideal effects. The amplifier exhibits a reasonable bandwidth and unity gain bandwidth, making it suitable for analog signal processing applications.


# Circuit 2: Differential Amplifier with PMOS active load and an NMOS current source

# 1. Circuit diagram :

<img width="1005" height="825" alt="image" src="https://github.com/user-attachments/assets/61ad0e14-d848-4772-916c-420e4a04cbfb" />


## Circuit Analysis:

### 1.1 Calculation of Tail Current (ISS):

The tail current is calculated using the power relation:

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

* #### Source Voltage

Given:

$$Vp = −0.7 V$$

Assuming:

$$VS = Vp$$

$$VS = −0.7 V$$

* #### Gate-Source Voltage

$$VGS = VG − VS$$

$$VGS = 0 − (−0.7)$$

$$VGS = 0.7 V$$

* #### Overdrive Voltage

Given:

$$VT ≈ 0.36 V$$

$$VOV = VGS − VT$$

$$VOV = 0.7 − 0.36$$

$$VOV = 0.34 V$$

* #### Drain Voltage

From previous result:

$$Vout1 = Vout2 = 0 V$$

So,

$$VD = 0 V$$

* #### Drain-Source Voltage

$$VDS = VD − VS$$

$$VDS = 0 − (−0.7)$$

$$VDS = 0.7 V$$

Saturation Condition Check

Condition:

$$VDS > VOV$$

$$0.7 > 0.34$$

Hence, both transistors operate in saturation region.

* #### NMOS Current Source (M5)

Given:

Source voltage: 

$$VS = VSS = -0.9 V$$
Drain voltage: 

$$VD = Vp = -0.7 V$$

Drain-Source Voltage:
$$VDS = VD - VS$$

$$VDS = -0.7 - (-0.9)$$

$$VDS = 0.2 V$$

Saturation Condition:
For NMOS to operate in saturation:

$$VDS >= VOV$$

So,
$$0.2 >= VOV$$

* #### Choosing Overdrive Voltage:
  
To ensure saturation while maximizing current:

$$VOV ≈ 0.2 V$$

Gate-Source Voltage:

$$VGS = VT + VOV$$

$$VGS = 0.36 + 0.2$$

$$VGS = 0.56 V$$

Gate Voltage:

$$VG = VS + VGS$$

$$VG = -0.9 + 0.56$$

$$VG = -0.34 V$$

Saturation Check:

$$VDS >= VOV$$

$$0.2 >= 0.2$$

Thus, M5 operates at the edge of saturation and provides the required tail current.

* #### PMOS Active Load (M3 and M4)

For PMOS:

Source is connected to:

$$VDD = 0.9 V$$

Drain is at:

$$VD = 0 V$$

Source-Drain Voltage:

$$VSD = VDD - VD$$

$$VSD = 0.9 - 0$$

$$VSD = 0.9 V$$


Saturation Condition:
For PMOS to operate in saturation:

$$VSD > VOV$$

So,
$$0.9 > VOV$$

Conclusion for M3 and M4:
Since VSD (0.9 V) exceeds the required overdrive voltage, both PMOS transistors operate in saturation.

## 1.5 Width Calculation:


The drain current in saturation is given by:

$$ID = (1/2) × μnCox × (W/L) × (VOV)²$$

Rearranging to find width:

$$W = (2 × ID × L) / (μnCox × (VOV)²)$$

Substituting Values

$$ID = 0.416 mA = 0.416 × 10⁻³ A$$
$$L = 360 nm = 360 × 10⁻⁹ m$$
$$μnCox = 230.6 μA/V² = 2.306 × 10⁻⁴$$
$$VOV = 0.34 V$$

#### Calculation

$$W = (2 × 0.416 × 10⁻³ × 360 × 10⁻⁹) / (2.306 × 10⁻⁴ × (0.34)²)$$

$$W = (299.52 × 10⁻¹²) / (2.306 × 10⁻⁴ × 0.1156)$$

$$W = (299.52 × 10⁻¹²) / (2.266 × 10⁻⁵)$$

$$W ≈ 11.235 μm$$

## NMOS Current Source (M5)

From previous calculations:

$$ID = ISS = 0.833 mA = 0.833 × 10⁻³ A$$

$$VOV₅ = 0.2 V$$

Substituting:

$$W = (2 ×  0.833 × 10⁻³ × 360 × 10⁻⁹) / (2.365 × 10⁻⁴ × (0.2)²)$$

$$W = (5.99 ×10⁻¹⁰) / (2.365 × 10⁻⁴ × 0.04)$$

$$W = (5.99 ×10⁻¹⁰) / (9.46 × 10⁻⁶)$$

$$W ≈ 63.3 μm$$

## PMOS Current Source (M3 and M4)

$$ID = (1/2) × μnCox × (W/L) × (VOV)²$$

$$W = (2 × ID × L) / (μpCox × (VOV)²)$$

$$W = (2 × 0.4165 × 10^-3 × 360 × 10^-9) / (9.754 × 10^-4 × (0.51)²)$$

$$W = 11.82 × 10^-6 m = 11.82 µm$$

# 2. DC Analysis:

<img width="1756" height="820" alt="image" src="https://github.com/user-attachments/assets/c8410f4d-cf58-4635-83f7-161852859c6c" />

# 3. Input Common Mode Range (ICMR):

Input Common Mode Range (ICMR)

The input common-mode range is the range of input voltage over which all transistors in the differential amplifier remain in saturation and operate properly.

## 3.1 Minimum Input Common Mode Voltage

For proper operation, the NMOS transistors must remain ON:

Condition:

$$VGS ≥ VT$$

We know:

$$VGS = VICM − VS$$

So,

$$VICM(min) = VS + VT$$

Substituting values:

$$VS = -0.7 V$$

$$VT = 0.36 V$$

$$VICM(min) = -0.7 + 0.36$$

$$VICM(min) = -0.34 V$$

## 3.2 Maximum Input Common Mode Voltage

To keep the transistors in saturation:

Condition:

$$VDS ≥ VOV$$

Given:

$$VD = 0 V$$

$$VS = -0.7 V$$

$$VSD = VD − VS = 0 − (-0.7) = 0.7 V$$

Now,

$$VICM(max) = VD + VTP$$

Substituting:

$$VICM(max) = 0 + 0.39$$

$$VICM(max) = 0.39 V$$

Final Range:

$$-0.34 V ≤ VICM ≤ 0.39 V$$

# 4. Output Common Mode Range (OCMR):

The output common-mode range is defined as the range of output voltage for which all transistors remain in saturation.

## Minimum Output Common Mode Voltage

For minimum output voltage, the NMOS input transistors (M1 and M2) must remain in saturation.

Condition:

$$VDS1 ≥ VOV$$

Using:

$$VDS1 = Vout − VS$$

So,
$$Vout(min) − VS ≥ VOV$$

$$Vout(min) ≥ VS + VOV$$

Substituting:

$$VS = -0.7 V$$

$$VOV = 0.34 V$$

$$Vout(min) = -0.7 + 0.34$$

$$Vout(min) = -0.36 V$$

## Maximum Output Common Mode Voltage

For maximum output voltage, the PMOS load transistors (M3 and M4) must remain in saturation.

Condition:

$$VSD ≥ VOVp$$

Using:
$$VSD = VDD − Vout$$

So,
$$VDD − Vout(max) ≥ VOVp$$

$$Vout(max) ≤ VDD − VOVp$$

Substituting:
$$VDD = 0.9 V$$
$$VOVp ≈ 0.25 V$$

$$Vout(max) = 0.9 − 0.25$$

$$Vout(max) = 0.65 V$$

Final Output Common Mode Range

$$-0.36 V ≤ Vout ≤ 0.65 V$$

# 5. Differential Input Voltage Range (Linear Region)

The differential amplifier operates linearly only when both transistors remain in saturation and the current is nearly equally shared.

Condition for Linear Operation:

$$|Vid| ≤ 2 × VOV$$

Substituting value:
$$VOV = 0.34 V$$

$$|Vid| ≤ 2 × 0.25$$

$$|Vid| ≤ 0.5 V$$

Final Range:

$$-0.5 V ≤ Vid ≤ 0.5 V$$

# 6. Transient Analysis and Linearity Observation

The linear behavior of the differential amplifier is verified using transient analysis.

Condition for Linearity:

$$|Vid| < √2 × VOV$$

Using a refined condition:

$$√2 × VOV ≈ 1.414 × VOV$$

Substituting value:

$$VOV = 0.25 V$$

$$√2 × VOV ≈ 1.414 × 0.25$$

$$√2 × VOV ≈ 0.34 V$$

* ## Case 1: Linear Region:

**Input applied:**

$$Vid = 200 mV$$

Since:

$$200 mV < 0.34 V$$

The amplifier operates in the linear region.


<img width="1913" height="913" alt="image" src="https://github.com/user-attachments/assets/24ef8d3b-2971-4f70-87b7-ef98f39fe607" />

* ## Case 2: Non-Linear Region:

**Input applied:**

$$Vid = 700 mV$$

Since:

$$700 mV > 0.34 V$$

The amplifier operates in the non-linear region.

<img width="1918" height="912" alt="image" src="https://github.com/user-attachments/assets/3d858b45-7071-457b-95b2-220fcb132e82" />


# 7. Comparison Table:

| Parameter            | Case 1: Linear Region  | Case 2: Non-Linear Region   |
| -------------------- | ---------------------- | --------------------------- |
| Condition            | Vid < √2  × VOV          | Vid > √2 × VOV               |
| Input (Vid)          | 200 mV                 | 700 mV                      |
| Output waveform      | Sinusoidal             | Distorted / Clipped         |
| Gain                 | Constant               | Reduced / Non-linear        |
| Transistor operation | All in saturation      | One NMOS in cutoff          |
| Current distribution | Shared between M1 & M2 | Current flows in one branch |

# 8. Theoretical Gain

Assume channel length modulation:

$$λ = 0.1 V⁻¹$$

## 8.1 Output Resistance

The output resistance of each MOSFET is:

$$ro = 1 / (λ × ID)$$

Substituting values:

$$ID = 0.416 mA = 0.416 × 10⁻³ A$$

$$ro = 1 / (0.1 × 0.416 × 10⁻³)$$

$$ro = 24 kΩ$$

## 8.2 Effective Output Resistance

Since two transistors are present:

$$ro_eff = ro1 || ro2$$

$$ro_eff = 24 kΩ || 24 kΩ$$

$$ro_eff = 12 kΩ$$

## 8.3 Transconductance

$$gm = (2 × ID) / VOV$$

$$gm = (2 × 0.416 × 10⁻³) / 0.24$$

$$gm ≈ 3.46 mS$$

## 8.4 Total Output Resistance

$$Rout = ro_eff$$

$$Rout =  12 kΩ$$

$$Rout ≈ 12 kΩ$$


## 8.4 Differential Gain

$$Ad = gm × Rout$$

$$Ad = 2.44 × 10⁻³ × 12 × 10³$$

$$Ad ≈ 29.28$$

## 8.5 Gain in dB

$$Ad(dB) = 20 log10(Ad)$$

$$Ad(dB) = 20 log10(29.28)$$

$$Ad(dB) ≈ 29.33 dB$$

# 9. Simulated Gain

## 9.1 Input Signal Parameters

Measured Peak-to-Peak Values:

$$Vin(p-p) = 99.95 mV − (−99.92 mV) = 0.199V$$

$$Vout(p-p) = 212.98 mV − (−159.26 mV) ≈ 0.372 V$$

Voltage Gain:

$$Av = Vout(p-p) / Vin(p-p)$$

$$Av = 0.372 / (0.199)$$

$$Av = 1.86 V/V$$

## 9.2 Gain in dB

$$Av(dB) = 20 log10(Av)$$

$$Av(dB) = 20 log10(1.86)$$

$$Av(dB) ≈ 5.39 dB$$

# 10. AC Analysis:

<img width="1912" height="891" alt="image" src="https://github.com/user-attachments/assets/6400859c-bd47-4866-8f5d-e803183e1ef4" />

## 10.1 Midband Gain

From AC simulation:

$$Av =5.637 dB$$

-3 dB Gain:

$$Av - 3 = 5.637 - 3$$

$$Av - 3 = 2.637 dB$$

## 10.2 Cutoff Frequencies

Lower cutoff frequency:
$$fL = 0 Hz$$

Upper cutoff frequency:
$$fH = 26.639 MHz$$

Bandwidth

Bandwidth is defined as:

$$BW = fH − fL$$

$$BW = 26.639 − 0$$

$$BW = 26.639 MHz$$

# 11. Unity Gain Bandwidth (UGB)
Since the 0 dB crossing point is not visible in the AC plot, the unity gain bandwidth cannot be measured directly.

So, it is estimated using the relation:

$$UGB = Av × BW$$

Substituting Values

$$Av = 1.86 BW = 26.639 MHz$$

$$UGB = 1.86 ×  26.639 MHz$$

$$UGB = 49.548 MHz$$

# 12. Inference:

The differential amplifier with a PMOS active load and an NMOS current source achieves good voltage gain due to high output resistance.

It provides stable biasing through the NMOS current source, ensuring proper operation of the circuit.

The PMOS active load improves gain without requiring large resistors.

The amplifier operates linearly only for small differential input voltages.

For larger inputs, one transistor enters cutoff, leading to nonlinearity and distortion.

The output swing is limited by saturation conditions of the transistors.

Overall, it offers a good trade-off between gain, linearity, and power efficiency.























​

