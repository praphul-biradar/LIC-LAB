# LIC LAB


# EXPERIMENT  01


# Aim:
To create a PMOS Common Source amplifier with 180 nm CMOS technology with specified voltage and power limit, and to investigate its functioning in DC analysis,
transient analysis, and AC analysis in LTspice. 


Given Specifications:


1. Supply voltage (VDD) = 1.2 V


2.Maximum power ≤ 0.4 mW


3.Load capacitance (CL) = 0.5 pF


4.Channel length (L) = 360 nm


Components Required:


PMOS transistor (TSMC 180 nm model), drain resistor, DC source, signal source and capacitor.


# Theory:


The most significant feature of modern integrated circuits is the contribution of MOSFETs owing to the reduction in size, low power requirements,
large-input impedance, and capability to employ scaled VLSI technology. They may exist in the form of NMOS or PMOS and may be used in three common source,
source follower and common gate modes of amplifiers. The Common Source arrangement is the most implemented in an analog circuit of these, due to its high voltage gain and phase inversion. 
The PMOS transistor must be made to be in a saturation state where it behaves as a voltage-controlled current source in order to be correctly amplified. The following are the conditions of saturation:


1. Vsg > |VT|


2.Vsd ≥ Vsg − |VT|


Overdrive voltage:
Vov = Vsg − |VT|


# Procedure:


1. Install LTspice library of TSMC 180 nm technology.
2. Caught PMOS Common Source circuit with:
   * Source connected to VDD
   Load resistor Drain attached to load resistor.
   DC biased and AC signal on the gate.
   * Body tied to source
   Load capacitor is related to the output.
3. Set an initial width and set channel length to 360 nm.
4. Run DC op analysis.
5. Adjust transistor width until current and voltage desired within power limit is achieved.
6. Check saturation condition.
7. Apply input sinuoid analysis, transient analysis.
8. Small signal analysis of 1 V AC Analytics.
9. Compare theoretical and simulated data.


# Design Calculations:


1. Drain Current:
Power relation:
P = VDD × ID
Id = P / VDD = 0.4 mW / 1.2 V = 0.333 mA


We will choose value less than 0.333mA :


# Id ≈ 250 uA


2. PMOS Width Calculation:


Having equation of saturation current:
Id = (1/2) μp Cox (W/L) (Vov)^2
up = 0.0115689 m^2/V·s
Cox = 0.0084207 F/m^2
L = 360 nm = 360 × 10^-9m 
Vov = 0.2094 V
Id = 250 uA = 250 × 10⁻^6A

# On substitution :
# W ≈ 42 um


3. Output Voltage:
Vd ≈ VDD / 2 = 0.6 V


4. Drain Resistance:
RD = Vd / ID = 0.6 / (250 uA) = 2.4 kΩ


5. Gate-Source Voltage:
|VT| = 0.3906 V
# Choose Vsg ≈ 0.6 V
Overdrive voltage:
Vov = 0.6 − 0.3906 = 0.2094 V


6. Gate Voltage:
Vs = 1.2 V
Vg = Vs − Vsg = 1.2 − 0.6 = 0.6 V


7. Saturation Verification:
Vsd = Vs − Vd = 1.2 − 0.6 = 0.6 V
# Vov< Vsd    Mosfet is in saturation.


# Final Calculated Values:
Id ≈ 250 uA


Vd ≈ 0.6 V


Rd = 2.4 ohm


Vg = 0.6 V


Vov = 0.2094 V


# CIRCUIT: 

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/WhatsApp%20Image%202026-02-20%20at%207.34.26%20PM.jpeg)


# DC Analysis


DC analysis determines the Q point of operation of the transistor and determines that the transistor is in saturation; thereby ensuring that it amplifies linearly with minimal distortion. It also will help in the examination of bias and component stability. 


Initial simulation results:
ID ≈ 149 uA
Vout ≈ 0.359 V

Such values differed with theoretical values due to real-life effects on such devices such as short-channel effects and loss of mobility.

With increased width to 72 um new results were:

# ID ≈ 247 uA
# Vout ≈ 0.59 V

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-02-22%20171140.png)



# Transient Analysis


Transient analysis Transient analysis is an analysis of response of an amplifier with time. It allows one to observe the amplification of signals, inversion of phases, distortion and dynamic properties. 



![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/WhatsApp%20Image%202026-02-20%20at%207.32.55%20PM.jpeg)



# Gain Calculation


Theoretical Gain:
gm = 2Id / Vov = 2.39 mS


Av = gm × RD = 5.736


Gain (dB) = 20 log10(Av) = 15.16 dB


Simulated Gain:
Input peak-to-peak = 20 mV
Output peak-to-peak = 136.05 mV

Av = 136.05 / 20 = 6.80
Gain (dB) = 20 log(Av) = 16.65 dB


Difference is caused due to  channel length modulation, output resistance and short-channel effects.


# AC Analysis
AC analysis is used to determine frequency response, mid-band gain and bandwidth.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/WhatsApp%20Image%202026-02-20%20at%207.50.11%20PM.jpeg)


Mid-Band Gain:


From AC plot:


Gain ≈ 16.912 dB ≈ 6.8 V/V


Bandwidth:


# BW = 1 / (2 *pi *RD* CL) = 132.63 MHz


# Simulated bandwidth ≈ 131.8 MHz


Unity Gain Bandwidth:


# UGB = Av × BW = 6.8 × 131.8 ≈ 896 MHz
# Observed ≈ 913 MHz.



# Result


The PMOS Common Source amplifier circuit was successfully designed and simulated using 180 nm CMOS technology within the given power and voltage constraints. 
The DC analysis result showed that the transistor was in the saturation region with a drain current of about 247 µA and an output voltage of about 0.59 V,
which are very close to the expected values. 
The transient analysis result confirmed that the amplification took place with a 180° phase difference between the input and output signals, thus validating the Common Source amplifier circuit.
The AC analysis result showed that the amplifier was stable with a mid-band gain of about 6.8 V/V (or 16.9 dB) and a bandwidth very close to the theoretical value of about 132 MHz.


# Inference


Te design method is justified by the fact that the theoretical values are closely close to the results of the simulated values.
Adequate saturation bias: ensured linear amplification Transient analysis: signal behavior Transient analysis: signal behavior AC analysis: gain and bandwidth as desired This explains that PMOS Common Source amplifiers can be useful in designing a g CMOS circuits.








