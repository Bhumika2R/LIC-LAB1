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
