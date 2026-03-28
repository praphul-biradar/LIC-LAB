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


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-27%20164551.png)


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


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-27%20164543.png)


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



The differential amplifier operates in the linear region only when both transistors (M1 and M2) remain in saturation.
 

#    Condition for Linear Operation

For MOS differential pair:

V_id < √2 × V_ov  

 

#  Given

V_ov = 0.39 V  
 

#  Calculation

V_id(max) = √2 × V_ov  

V_id(max) = 1.414 × 0.3  

V_id(max) ≈ 0.42 V  

 

#  Final Range

-0.42 V ≤ V_id ≤ 0.42 V  

 

### 🔹 Conclusion

For |V_id| < 0.42 V → circuit behaves as linear amplifier  

For |V_id| > 0.42 V → one transistor turns OFF → nonlinear behavior occurs  


# 7. Output Voltage Range

Minimum output voltage:

V_out(min) = V_S + V_ov = -0.7 + 0.3 = -0.4 V  

Maximum output voltage:

V_out(max) = V_DD = 0.9 V  


## Transient Analysis and Linearity Observation

Transient analysis is performed to observe the linear behavior of the differential amplifier.

A load capacitor is connected at the output:

C_L = 10 pF  


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-27%20164439.png)


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


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-27%20170759.png)


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


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-27%20164251.png)


# Midband Gain

From AC simulation (cursor reading):

A_v = 12.45 dB  

The corresponding linear gain is:

A_v = 10^(12.45/20) ≈ 4.19  


# Theoretical Gain Calculation


# Given Values

Drain current: I_D = 0.61 mA  
Overdrive voltage: V_ov = 0.3 V  
Drain resistance: R_D = 1.47 kΩ  
Channel length modulation parameter: λ = 0.1  



# Step 1: Transconductance (g_m)

g_m = 2I_D / V_ov  

g_m = (2 × 0.61 mA) / 0.3  

g_m ≈ 4.07 mS  



#  Step 2: Output Resistance (r_o)

r_o = 1 / (λ × I_D)  

r_o = 1 / (0.1 × 0.61 mA)  

r_o = 1 / 0.000061  

r_o ≈ 16.4 kΩ  



# Step 3: Effective Load Resistance

R_eff = R_D || r_o  

R_eff = (1.47 kΩ × 16.4 kΩ) / (1.47 kΩ + 16.4 kΩ)  

R_eff ≈ 1.35 kΩ  



# Step 4: Voltage Gain

A_v = g_m × R_eff  

A_v = 4.07 × 10⁻³ × 1350  

A_v ≈ 5.5  


Reason for Difference Between Theoretical and Simulated Gain

The theoretical gain is higher than the simulated gain due to the following reasons:

- Theoretical calculations neglect parasitic effects  
- Channel length modulation reduces gain  
- Finite output resistance of MOSFET reduces effective load  
- Presence of load capacitance affects gain  
- Simulation uses real device models (TSMC 0.18)  
- Gain is measured as single-ended output instead of differential output  

Hence, the simulated gain is lower than the theoretical value.

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


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20163100.png)


# Unity Gain Bandwidth (UGB)

Unity Gain Bandwidth (UGB) is defined as the frequency at which the gain becomes 1 (0 dB).



# From AC Plot

From the graph:

The gain crosses **0 dB** at approximately:

UGB ≈ 45.9 MHz  



 Final Result

UGB ≈ 45.9 MHz  


#  Observation

Gain is constant in midband region
Gain decreases at higher frequencies due to capacitive effects  
The roll-off indicates limited bandwidth  



#  Conclusion

The AC analysis shows that the differential amplifier has a high bandwidth. The gain decreases at higher frequencies due to parasitic capacitances and load capacitor effects. The amplifier demonstrates a gain-bandwidth trade-off.



## Circuit 2


## Differential Amplifier (Active Load) – Analysis



##  Aim

To design and analyze a MOS differential amplifier with active load, determine its DC operating point, and evaluate its performance in terms of gain, linearity, and frequency response using LTspice.



# Introduction

A differential amplifier amplifies the difference between two input signals while rejecting common-mode signals. In this circuit, an active load (current mirror) is used instead of resistors, which increases gain and improves performance.



# Circuit Description

The circuit consists of:

- M1, M2 → NMOS differential pair  
- M3, M4 → PMOS current mirror (active load)  
- M5 → Tail current source  


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20172015.png)


# Given Parameters

V_DD = 0.9 V  
V_SS = -0.9 V  
Power P = 2.2 mW  
V_T ≈ 0.4 V  
V_ov ≈ 0.39 V  
L = 540 nm  


# Design Calculations

# Tail Current

I_SS = P / (V_DD - V_SS)  

I_SS = 2.2 mW / 1.8 V  

I_SS ≈ 1.22 mA  



# Branch Current

I_D = I_SS / 2  

I_D ≈ 0.61 mA  



# Bias Voltage

V_GS = V_T + V_ov  

V_GS = 0.34 + 0.3 = 0.64 V  

V_B = V_S + V_GS  

V_B = -0.9 + 0.64  

V_B ≈ -0.26 V  



## DC Analysis (Simulation)


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20172139.png)


## 🔹 Results

I_SS ≈ 1.23 mA  
I_D1 = I_D2 ≈ 0.615 mA  
V_p ≈ -0.724 V  
V_out1 ≈ V_out2 ≈ -0.055 V  


#  Input Common Mode Range (ICMR)

The input common-mode range is defined as the range of input voltage for which all transistors remain in saturation.



# Minimum Input Common Mode Voltage

Condition:

Input NMOS must remain ON:

V_GS ≥ V_T  

Using:

V_GS = V_ICM − V_S  

So,

V_ICM(min) = V_S + V_T  

Now,

V_S = V_SS + V_ov  

V_S = -0.9 + 0.3 = -0.6 V  

Therefore:

V_ICM(min) = -0.6 + 0.4  

V_ICM(min) = -0.2 V  



# Maximum Input Common Mode Voltage

Condition:

Input NMOS must remain in saturation:

V_DS ≥ V_ov  

Using:

V_D ≈ V_DD − V_ov  

V_D = 0.9 − 0.3 = 0.6 V  

Now,

V_ICM(max) = V_D − V_ov  

V_ICM(max) = 0.6 − 0.3  

V_ICM(max) = 0.3 V  

# Final Input Common Mode Range

-0.2 V ≤ V_ICM ≤ 0.3 V  



# Differential Input Voltage Range (Linear Region)

For linear operation:

V_id < √2 × V_ov  

V_id < 1.414 × 0.3  

V_id < 0.42 V  



# Conclusion

- ICMR: -0.2 V to 0.3 V  
- Linear region condition: V_id < 0.42 V  


# ifferential Input Voltage Range (Linear Region)

The differential amplifier operates in the linear region only when both transistors (M1 and M2) remain in saturation.

 

#  Condition for Linear Operation

For MOS differential pair:

V_id < √2 × V_ov  

 

#  Given

V_ov = 0.39 V  

 

# 🔹 Calculation

V_id(max) = √2 × V_ov  

V_id(max) = 1.414 × 0.3  

V_id(max) ≈ 0.42 V  

 

#   Final Range

-0.42 V ≤ V_id ≤ 0.42 V  

 
#  Conclusion

For |V_id| < 0.42 V → circuit behaves as linear amplifier  

For |V_id| > 0.42 V → one transistor turns OFF → nonlinear behavior occurs  



# Step 2: Transient Analysis and Linearity Observation

Transient analysis is performed to observe the linear behavior of the differential amplifier with active load.

Load capacitor:

C_L = 10 pF  


# (a) Case 1: V_id < √2 V_ov

Condition:

V_id < 1.414 × V_ov  

V_id < 1.414 × 0.3 ≈ 0.42 V  

Set small differential input:

V_in1 = +10 mV  
V_in2 = -10 mV  

V_id = 20 mV < 0.42 V  

## Observation:

- Output waveforms are sinusoidal  
- No distortion observed  
- Outputs are equal in magnitude  
- Outputs are 180° out of phase  
- Circuit operates in linear region  


# (b) Case 2: V_id > √2 V_ov


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20194740.png)


Condition:

V_id > 0.42 V  

Set large differential input:

V_in1 = +300 mV  
V_in2 = -300 mV  

V_id = 600 mV > 0.42 V  

# Observation:

- Output becomes distorted  
- Peaks are clipped or flattened  
- One transistor carries most of the current  
- Other transistor goes near cutoff  
- Nonlinear behavior is observed  


# (c) Comparison and Interpretation

| Condition      | Input (V_id)   | Output Behavior  | Operation |
| V_id < √2 V_ov | Small (20 mV)  | Clean sinusoidal | Linear    |
| V_id > √2 V_ov | Large (600 mV) | Distorted        | Nonlinear |


# Conclusion

The differential amplifier with active load behaves as a linear amplifier for small input signals. When the input exceeds √2 × V_ov, the circuit enters nonlinear region and distortion occurs.

## 🔷 AC Analysis

In AC analysis, the frequency response of the differential amplifier is observed.


 ![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20194658.png)
 

#  Midband Gain

From the flat region of the plot:

A_v ≈ 6 dB  

Convert to linear:

A_v = 10^(6/20) ≈ 2  

 
#  Cutoff Frequencies

Lower cutoff frequency:

f_L ≈ 0 Hz  

 

Upper cutoff frequency:

From graph at −3 dB point:

A_v - 3 = 6 - 3 = 3 dB  

f_H ≈ 3 GHz to 5 GHz (approx)

 

#  Bandwidth

BW = f_H - f_L  

BW ≈ 4 GHz  

  # Unity Gain Bandwidth (UGB)


  ![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20194209.png)
  

Unity Gain Bandwidth is defined as the frequency at which the gain becomes 0 dB.

From AC plot:

UGB ≈ 5.035 GHz  

   

#  Observation

- Gain crosses 0 dB at ≈ 5 GHz  
- Phase at this point ≈ −90°  
- Indicates stable amplifier behavior  
  

# Conclusion

The Unity Gain Bandwidth of the differential amplifier is approximately 5.035 GHz.
#  Conclusion

The amplifier shows a flat midband gain of approximately 6 dB with a very high bandwidth in the GHz range. The gain starts decreasing after the upper cutoff frequency, indicating typical high-frequency roll-off behavior.





