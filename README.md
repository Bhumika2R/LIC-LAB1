# LIC-LAB1
# Experiment 1: CS Amplifier Characterization in LTspice using 180nm Technology
# 1.Aim:
Design CS Amplifier using NMOSFET in tsmc 180nm using VDD=2V, P<=1.5mW, C=1pF, Ln=560nm
# 2.Theory:
The MOSFET structure has become the most important device structure in the Electronics industry. It dominates the integrated circuit technology in Very Large Scale Integrated (VLSI) digital circuits based on n-channel MOSFETs and Complementary n- Channel and p-channel MOSFETs (CMOS). The technical importance of the MOSFET results from Its low power consumption, simple geometry, and small size, resulting in very high packing Densities and compatibility with VLSI manufacturing technology. Two of the most popular Configurations of small-signal MOSFET amplifiers are the common source and common drain Configurations. The common source circuit is shown below. The common sources, like all MOSFET amplifiers, have the characteristic of high input impedance. High input impedance is Desirable to keep the amplifier from loading the signal source. This high input impedance is Controlled by the bias resistor). Normally the value of the bias resistors is chosen as High as possible. However, too big a value can cause a significant voltage drop due to the gate Leakage current. A large voltage drop is undesirable because it can disturb the bias point. For Amplifier operation the MOSFET should be biased in the active region of the characteristics.
# Circuit Design-1 without Capacitor:
<img width="893" height="650" alt="image" src="https://github.com/user-attachments/assets/77bbda1d-4a91-4f6c-bcea-9902065919d6" />

# 3.Procedure:

Step 1: Create a New Schematic
Launch LTspice and open a new schematic window. Save the schematic with a suitable file name in the same directory where the TSMC technology model file is stored.

Step 2: Insert Required Components Add the following components to the schematic:
• NMOS transistor (CMOSN / 180 nm NMOS technology model)
• Resistor
• Two voltage sources (one for DC supply and one for input signal)
• Ground terminal (mandatory reference node for simulation)

Step 3: Assign Component Parameters set the component values as follows:

• DC Supply (V1) = 2 V
  (connected to the drain through resistor R1)

• Input Source (V2) = SINE(0.9 10m 1k)
  → 0.9 V DC bias
  → 10 mV AC amplitude
  → 1 kHz signal frequency

• Resistor R1 = 5 kΩ
  (placed between V1 and the drain terminal)

• MOSFET (M1) = 180 nm NMOS model
  → Drain connected to R1
  → Source connected to ground
  → Gate connected to input source V2

Import the CMOS/NMOS model file containing threshold voltage and device parameters into the schematic.

Step 4: Set Up Simulation Commands
Open “Simulation → Edit Simulation Cmd” and include:

• DC Operating Point Analysis:
      .op
  (used to determine bias conditions)

• AC Analysis:
      .ac dec 10 0.1 100G
  (used to evaluate gain and frequency response)

• Transient Analysis:
      .tran 5m
  (used to observe time-domain waveform)

Place all simulation directives onto the schematic.

Step 5: Execute Simulation
Click the Run button (green play icon). The waveform viewer will open displaying simulation outputs such as
DC operating values, frequency response, and transient waveforms.

Step 6: Analyze Results
• For DC analysis, verify VGS, VDS, and ID to ensure
  the MOSFET operates in the intended region.
• For AC analysis, examine voltage gain and bandwidth
  from the frequency response plot.
• For transient analysis, observe the output waveform
  and confirm that signal amplification occurs.


# 4.Calculation:
# 4.1 Power constraint:
   Assuming ID =200µA which satisfy P<=1.5mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.5mW)

# 4.2 Drain Resistance
  We know                   VDD-ID*RD=VD
  
  2-200×10−6×RD=1

  therefore RD=5K ohms

# 4.3 Width calculation:
   Kn′=μnCox

   Kn′= 230×10^−6 A/V^2

   VGS​=VG​−VS​
   VGS=0.9−0
   VGS=0.9V

   ID​=​K′*W/L​(Vov​)^2

   W=1.07×10−6 m
# 5. DC analysis:
<img width="842" height="626" alt="image" src="https://github.com/user-attachments/assets/958341dc-f297-4642-9311-10a5a378c2d8" />




From the simulation results, Vout = 1.23 V, Vin = 0.9 V andthe obtained drain current is approximately 153 µA.Since the calculated current differs from the simulated value,the transistor width is adjusted while keeping the channellength constant at 180 nm to achieve the required current.
# Length-Width vs Drain Current (Id)

| Length (nm) | Width (µm) | Id (µA) |
|---------    |------------|---------|
| 180         | 1.07       | 153.76  |
| 180         | 1.20       | 167.84  |
| 180         | 1.30       | 178.53  |
| 180         | 1.40       | 189.06  |
| 180         | 1.51       | 200     |


To verify the operating region of the MOSFET, the conditiont for saturation is checked:

 VDS ≥ VOV

Here,
VDS = VD − VS = 1 − 0 = 1 V

Since VDS is greater than the overdrive voltage (VOV),the MOSFET operates in the saturation region.

Therefore, the operating (Q) point of the circuit is:

 Q-point = 1 V, 200 µA
# 6. Transfer Characteristics:
<img width="1600" height="348" alt="image" src="https://github.com/user-attachments/assets/6a2411e7-ea2d-46dc-98e8-0231d65a31e9" />

# 7.Transient Analysis:
Vin
<img width="1600" height="787" alt="image" src="https://github.com/user-attachments/assets/4f05d822-7ff8-4d2b-8e33-b29879ac1734" />
Vout
<img width="1600" height="781" alt="image" src="https://github.com/user-attachments/assets/346b70f5-0a02-45b4-831c-5a6763fa82de" />
Vin and Vout
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/81c78091-9eba-4fc7-9ffd-1a6ce1e28d52" />

The voltage gain of the circuit is determined from the transfer characteristics obtained from the graph.
# 7.1 Simulated Results:

* **Voltage Gain:**
        Av = ΔVout / ΔVin
        Av = 0.057 / 0.019 = 3

* **Gain in decibels:**
        Gain(dB) = 20 log10(Av)
                  = 20 log10(3)
                  = 9.54 dB


* **Transconductance Calculation:**
        gm = 2Id / Vov
           = 7.407 × 10⁻⁴ S
# 7.2 Theoritical Results:
* **Small-signal Voltage Gain:**
        Av = gm × RD
           = (7.407× 10⁻⁴) × (5 × 10³)
           = 3.70

* **Gain in decibels:**
        Gain(dB) = 20 log10(Av)
                 = 20log(3.70)
                 = 11.36 dB
# 8. AC Analysis without capacitor:
<img width="1918" height="423" alt="image" src="https://github.com/user-attachments/assets/74391439-a202-4901-a983-d95ce97a225c" />

* **Voltage Gain:**
The measured voltage gain of the amplifier is found to be

  Av = 9.4-3 ≈ 6.4 dB

* **Cutoff Frequency:**
The frequency at which the gain drops to the −3 dB level is observed as

  Cutoff Frequency = 41.88 GHz

* **Bandwidth:**
Since this is a single-pole response, the bandwidth of the circuit is equal to the cutoff frequency.

   Bandwidth = 41.88 GHz

# Circuit Design-2 with Capacitor:
<img width="1473" height="855" alt="image" src="https://github.com/user-attachments/assets/685e48f2-ade9-4df6-b09c-e4109b5c4c54" />

# 9. AC Analysis with capacitor:
<img width="1912" height="416" alt="image" src="https://github.com/user-attachments/assets/6c055c25-c12e-492d-9092-8a1e01f139c9" />


* **Capacitance used:**
the coupling capacitor selected for the circuit is 

    C = 1 pF
  
* **Voltage Gain:**
The amplifier provides a voltage gain of

     Av = 9.4-3 = 6.4dB
* **Bandwidth:**
  The operating frequency range of the amplifier,measured from the AC response is

    Bandwidth = 36.300 MHz
# 10. Comparision Table:

| Parameter   | Theoretical | Simulated |
|-------------|-------------|-----------|
| Gain (V/V)  | 3.7         | 3         |
| Gain (dB)   | 11.36 dB    | 9.54 dB   |
| ID          | 200 µA      | 153 µA    |
| W           | 1.07 µm     | 1.51 µm   |

# 11. Inference:
AC Analysis:
AC analysis studies circuits supplied by alternating current sources, where voltage and current vary periodically with time. It evaluates the steady-state response of the circuit using phasor representation, impedance concepts, and frequency response characteristics.

DC Analysis:
DC analysis deals with circuits powered by direct current sources in which voltage and current remain constant with respect to time. Circuit parameters are determined using Ohm’s law, Kirchhoff’s voltage and current laws, and basic network theorems.

Transient Analysis:
Transient analysis investigates circuit behavior during the transition between two steady-state conditions. It involves solving time-dependent differential equations associated with energy-storing elements such as capacitors and inductors.






