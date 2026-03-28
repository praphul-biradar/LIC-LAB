## Experiment 04


## Differential Amplifier Analysis


# Aim


To design and analyze a MOS differential amplifier with resistive load, determine its DC operating point, and evaluate its performance in terms of gain, input common-mode range (ICMR), and linearity using simulation.


# Introduction


A differential amplifier is a fundamental building block in analog circuit design that amplifies the difference between two input signals while rejecting any common-mode signals. It is widely used in applications such as operational amplifiers, comparators, and signal processing circuits.

In MOS-based differential amplifiers, two matched transistors share a common current source, ensuring symmetrical operation. The circuit provides high gain for differential inputs and good noise rejection capability.

In this experiment, a MOS differential amplifier with resistive load is designed and analyzed. The focus is on determining the biasing conditions, calculating key parameters such as gain and input common-mode range (ICMR), and verifying the performance using simulation tools.


# Theory

 
 Differential Amplifier with Resistive Load

A MOS differential amplifier consists of two identical MOSFETs whose sources are connected together and biased using a constant current source. The drains are connected to resistive loads. The circuit amplifies the difference between two input signals while rejecting common-mode signals.

 Working Principle

When equal voltages are applied to both inputs, the tail current splits equally between the two transistors, resulting in equal output voltages.

When a differential input is applied:

One transistor conducts more current
The other conducts less current

This causes opposite voltage variations at the outputs, producing amplified differential signals.

# Power Constraint

The total current is limited by the supply voltages:

P = (VDD − VSS) × ISS

This determines the tail current ISS, which controls the operating point of the amplifier.

# Drain Current

In a symmetrical differential amplifier:

ID = ISS / 2

Each transistor carries half of the tail current under balanced conditions.

# Load Resistance

The drain resistor converts current into voltage:

RD = (VDD − Vout) / ID

It plays a major role in determining the gain.

# Bias Point

The bias point ensures that the MOSFET operates in saturation.

Important voltages:

VG (Gate voltage)
VS (Source voltage)
VD (Drain voltage)

Condition for saturation:

VDS > VGS − VT

# Width Calculation

The drain current equation is:

ID = (1/2) μnCox (W/L) (Vov)²

This is used to calculate the required transistor width W.

# Input Common Mode Range (ICMR)

ICMR is the range of input voltage for which transistors remain in saturation.

Minimum value:

VICM(min) = VS + VT + VGS

Maximum value:

VICM(max) = VD + VT

# Output Common Mode Range

The output voltage must stay within limits to maintain saturation. It is bounded by supply voltages and saturation conditions.

# Differential Input Voltage Range (Linear Region)

For linear operation:

Vid < √2 × Vov

If this condition is violated, the amplifier becomes nonlinear and distortion occurs.

# Transient Analysis and Linearity

Transient analysis studies time-domain behavior:

Small input → linear, sinusoidal output
Large input → distorted output
# Theoretical Gain

Without channel length modulation:

Av = gm × RD

With channel length modulation:

Av = gm × (RD || ro)

Where:

gm = 2ID / Vov
ro = 1 / (λID)

# AC Analysis

AC analysis determines frequency response:

Midband gain → constant gain region
Cutoff frequencies → where gain drops
Bandwidth → frequency range of operation

## Circuit 01


## 🔷 Working of the Circuit

The MOS differential amplifier operates based on the principle of current steering between two matched transistors.

When equal voltages are applied at both inputs (common-mode input), the tail current **I_SS** splits equally between the two transistors:

 I_D1 = I_D2 = I_SS / 2  
 Output voltages at both drains are equal  

Hence, no differential output is produced.


## 🔹 Differential Operation

When a differential input is applied:

# Case 1: V_in1 > V_in2

Transistor M1 conducts more current  
Transistor M2 conducts less current  
Voltage drop across R_D of M1 increases → V_out1 decreases  
Voltage drop across R_D of M2 decreases → V_out2 increases  


# Case 2: V_in2 > V_in1

 Transistor M2 conducts more current  
 Transistor M1 conducts less current  
 V_out2 decreases and V_out1 increases  



# 🔹 Output Characteristics

 Outputs are equal in magnitude  
 Outputs are 180° out of phase  


## DC Analysis


![Image description](PASTE_FILENAME_HERE)


#  Design Calculations

# Given Parameters

 V_DD = 0.9 V  
 V_SS = -0.9 V  
 Power P = 2.2 mW  
 V_outCM = 0 V  
 V_S = -0.7 V  
 V_T = 0.4 V  
 V_ov = 0.3 V  
 L = 540 nm  



# 🔹 1. Tail Current Calculation

I_SS = P / (V_DD - V_SS)

I_SS = 2.2 mW / (0.9 - (-0.9))  
I_SS = 2.2 mW / 1.8 V  

I_SS ≈ 1.22 mA  

Since the circuit is symmetrical:

I_D = I_SS / 2  
I_D ≈ 0.61 mA  


# 2. Load Resistance Calculation

R_D = (V_DD - V_out) / I_D  

R_D = (0.9 - 0) / 0.61 mA  

R_D ≈ 1.47 kΩ  



#  3. Bias Point Calculation

V_G = 0 V  
V_S = -0.7 V  
V_D = 0 V  

V_GS = V_G - V_S = 0 - (-0.7) = 0.7 V  
V_DS = V_D - V_S = 0 - (-0.7) = 0.7 V  

Since V_DS > V_ov, the MOSFET operates in saturation.



# 4. Width Calculation

I_D = (1/2) μ_n C_ox (W/L) (V_ov)^2  

Assuming μ_n C_ox ≈ 200 μA/V²:

W/L ≈ 67.8  

W = 67.8 × 540 nm  

W ≈ 37 μm  


![Image description](PASTE_FILENAME_HERE)


# 🔹 5. Input Common Mode Range (ICMR)

Minimum value:

V_ICM(min) = V_S + V_T  
V_ICM(min) = -0.7 + 0.4 = -0.3 V  

Maximum value:

V_ICM(max) = V_D + V_T  
V_ICM(max) = 0 + 0.4 = 0.4 V  

Final range:

-0.3 V ≤ V_ICM ≤ 0.4 V  



# 6. Differential Input Voltage Range (Linear Region)

For linear operation:

V_id < √2 × V_ov  

V_id < 1.414 × 0.3 ≈ 0.42 V  



# 7. Output Voltage Range

Minimum output voltage:

V_out(min) = V_S + V_ov = -0.7 + 0.3 = -0.4 V  

Maximum output voltage:

V_out(max) = V_DD = 0.9 V  


## Transient Analysis and Linearity Observation

Transient analysis is performed to observe the linear behavior of the differential amplifier.

A load capacitor is connected at the output:

C_L = 10 pF  


![Image description](PASTE_FILENAME_HERE)


# Condition for Linear Operation

For linear operation:

V_id < √2 × V_ov  

V_id < 1.414 × 0.3 ≈ 0.42 V  



# (a) Case 1: V_id < √2 V_ov

Set a small differential input:

Example:  
V_in1 = +20 mV  
V_in2 = -20 mV  

So,

V_id = 40 mV < 0.42 V  

# Observation:

 Output is sinusoidal  
 No distortion observed  
 Outputs are equal in magnitude and opposite in phase  
 Circuit operates in linear region  



# (b) Case 2: V_id > √2 V_ov


![Image description](PASTE_FILENAME_HERE)


Set a large differential input:

Example:  
V_in1 = +300 mV  
V_in2 = -300 mV  

So,

V_id = 600 mV > 0.42 V  

 Observation:

 Output becomes distorted  
 Peaks are flattened  
 One transistor carries most of the current  
 Other transistor approaches cutoff  
 Nonlinear behavior is observed  


# (c) Comparison and Interpretation

| Condition      | Input Level  | Output Behavior    | Operation |
| V_id < √2 V_ov | Small signal | Clean sinusoidal   | Linear    |
| V_id > √2 V_ov | Large signal | Distorted waveform | Nonlinear |


# Conclusion

The differential amplifier operates linearly only for small input signals. When the input exceeds the limit √2 × V_ov, the circuit enters nonlinear region and distortion occurs.


# 🔷 1.4 AC Analysis

In AC analysis, the frequency response of the differential amplifier is observed.

The midband gain is obtained from the flat region of the Bode plot.  
The bandwidth is defined as the range between the lower cutoff frequency (f_L) and upper cutoff frequency (f_H), measured at the −3 dB points.


![Image description](PASTE_FILENAME_HERE)


# Midband Gain

From AC simulation (cursor reading):

A_v = 12.45 dB  

The corresponding linear gain is:

A_v = 10^(12.45/20) ≈ 4.19  



# −3 dB Gain

A_v(−3 dB) = 12.45 − 3  

A_v(−3 dB) = 9.45 dB  



# Cutoff Frequencies

Lower cutoff frequency:

f_L ≈ 0 Hz  

Upper cutoff frequency (from graph):

f_H ≈ 316.2 MHz  


# Bandwidth

BW = f_H − f_L  

BW ≈ 316.2 MHz  



 


#  Observation

Gain is constant in midband region
Gain decreases at higher frequencies due to capacitive effects  
The roll-off indicates limited bandwidth  



#  Conclusion

The AC analysis shows that the differential amplifier has a high bandwidth. The gain decreases at higher frequencies due to parasitic capacitances and load capacitor effects. The amplifier demonstrates a gain-bandwidth trade-off.










