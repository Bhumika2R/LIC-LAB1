# LIC-LAB1
# Experiment 1: CS Amplifier Characterization in LTspice using 180nm Technology
# Aim:
Design CS Amplifier using NMOSFET in tsmc 180nm using VDD=2V, P<=1.5mW, C=1.5pF, Ln=560nm
# Theory:
The MOSFET structure has become the most important device structure in the Electronics industry. It dominates the integrated circuit technology in Very Large Scale Integrated (VLSI) digital circuits based on n-channel MOSFETs and Complementary n- Channel and p-channel MOSFETs (CMOS). The technical importance of the MOSFET results from Its low power consumption, simple geometry, and small size, resulting in very high packing Densities and compatibility with VLSI manufacturing technology. Two of the most popular Configurations of small-signal MOSFET amplifiers are the common source and common drain Configurations. The common source circuit is shown below. The common sources, like all MOSFET amplifiers, have the characteristic of high input impedance. High input impedance is Desirable to keep the amplifier from loading the signal source. This high input impedance is Controlled by the bias resistor). Normally the value of the bias resistors is chosen as High as possible. However, too big a value can cause a significant voltage drop due to the gate Leakage current. A large voltage drop is undesirable because it can disturb the bias point. For Amplifier operation the MOSFET should be biased in the active region of the characteristics.
# Circuit Design:
<img width="893" height="650" alt="image" src="https://github.com/user-attachments/assets/77bbda1d-4a91-4f6c-bcea-9902065919d6" />


# Calculation:
1) Assuming ID =200µA which satisfy P<=1.5mW (P=V*I ; 2×200×10^−6 ; 400µW<=1.5mW)

2) We know VDD-ID*RD=VDS

   2-200×10−6×RD=1

   therefore RD=5K ohms

3) Kn′=μnCox

   Kn′= 230×10^−6 A/V^2

4) VGS​=VG​−VS​=0.9−0=0.9V

   ID​=​K′*W/L​(Vov​)^2

   W=1.07×10−6m
# DC analysis:
<img width="842" height="446" alt="image" src="https://github.com/user-attachments/assets/442407ca-2b4e-4388-9f92-9e42acd0a08d" />

From the simulation results, Vout = 1.23 V, Vin = 0.9 V andthe obtained drain current is approximately 153 µA.Since the calculated current differs from the simulated value,the transistor width is adjusted while keeping the channellength constant at 180 nm to achieve the required current.
## Length-Width vs Drain Current (Id)

| Length (µm) | Width (µm) | Id (µA) |
|-------------|------------|---------|
| 1900        | 1500       | 10.92   |
| 1900        | 1650       | 15.92   |
| 1900        | 1700       | 17.89   |
| 1900        | 1750       | 22.57   |
| 1900        | 1750       | 25.20   |


To verify the operating region of the MOSFET, the conditionfor saturation is checked:

     VDS ≥ VOV

Here,
VDS = VD − VS = 1 − 0 = 1 V

Since VDS is greater than the overdrive voltage (VOV),the MOSFET operates in the saturation region.

Therefore, the operating (Q) point of the circuit is:

        Q-point = 1 V, 200 µA
# Transfer Characteristics:
<img width="1600" height="348" alt="image" src="https://github.com/user-attachments/assets/6a2411e7-ea2d-46dc-98e8-0231d65a31e9" />

# Transient Analysis:
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/81c78091-9eba-4fc7-9ffd-1a6ce1e28d52" />

The voltage gain of the circuit is determined from thetransfer characteristics obtained from the graph.

* **Voltage Gain:**
        Av = ΔVout / ΔVin
        Av = 0.057 / 0.0186 = 3.06

* **Gain in decibels:**
        Gain(dB) = 20 log10(Av)
                  = 20 log10(3.06)
                  = 9.71 dB


* **Transconductance Calculation:**
        gm = 2Id / Vov
           = 7.49 × 10⁻⁴ S

* **Small-signal Voltage Gain:**
        Av = gm × RD
           = (7.49 × 10⁻⁴) × (5 × 10³)
           = 3.74

* **Gain in decibels:**
        Gain(dB) = 20 log10(Av)
                  = 11.36 dB
# AC Analysis without capacitor:
<img width="1918" height="423" alt="image" src="https://github.com/user-attachments/assets/74391439-a202-4901-a983-d95ce97a225c" />
* **Voltage Gain:**
The measured voltage gain of the amplifier is found to be

        Av = 9.4 ≈ 6.4 dB

* **Cutoff Frequency:**
The frequency at which the gain drops to the −3 dB levelis observed as

        Cutoff Frequency = 42.33 GHz

* **Bandwidth:**
Since this is a single-pole response, the bandwidth of the circuit is equal to the cutoff frequency.
         Bandwidth = 42.33 GHz
# AC Analysis with capacitor:
<img width="1912" height="416" alt="image" src="https://github.com/user-attachments/assets/6c055c25-c12e-492d-9092-8a1e01f139c9" />
* **Capacitance used:**
the coupling capacitor selected for the circuit is 
      C = 1.5 pF
* **Voltage Gain:**
The amplifier provides a voltage gain of
      Av = 9.4-3 = 6.4dB
* **Bandwidth:**
The operating frequency range of the amplifier,measured from the AC response is
      Bandwidth = 24.27MHz







