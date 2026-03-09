# Experiment 02


# Circuit 01


# CMOS Amplifier Using NMOS with PMOS Active Load


# AIM

The aim of this experiment is to design and analyze a CMOS amplifier circuit in which an NMOS transistor functions as the main amplifying device and a PMOS transistor acts as the active load. The circuit is implemented using TSMC 180 nm CMOS technology and its behavior is studied using LTspice simulation software.


The amplifier is designed to operate under the following specifications:


Supply voltage (VDD) = 1.2 V


Drain current (ID) = 250 µA


Load capacitance (CL) = 0.5 pF


Channel length (L) = 360 nm


The performance of the amplifier is examined using three types of analysis: DC operating point analysis, transient analysis, and AC small-signal analysis.


# COMPONENTS REQUIRED


The components used for this experiment include the following:


• NMOS transistor (TSMC 180 nm model)


• PMOS transistor (TSMC 180 nm model)


• Source resistor (RS)


• DC voltage sources for biasing


• Input signal voltage source


• Load capacitor (CL)


## THEORY


MOSFET transistors are essential devices used in modern integrated circuit design. Because of their small size and low power consumption, they are widely used in analog and digital electronics. CMOS technology combines both NMOS and PMOS transistors in a single circuit structure, which helps reduce power dissipation while maintaining good performance.


In this experiment a CMOS amplifier configuration is implemented. The NMOS transistor acts as the main amplifying element. It converts variations in input voltage into variations in current. The PMOS transistor is connected as an active load instead of a passive resistor. Using an active load increases the achievable gain of the amplifier and improves efficiency.


A resistor is connected to the source terminal of the NMOS transistor. This resistor provides source degeneration. Source degeneration helps stabilize the operating point and also reduces signal distortion during amplification.


This amplifier configuration provides several advantages such as higher voltage gain, improved bias stability, high input impedance, and reduced distortion.


For the circuit to operate as an amplifier, both MOSFETs must remain in the saturation region. In saturation, the MOSFET behaves like a controlled current source. This operating condition allows the circuit to amplify small signals applied at the input.


# SATURATION CONDITIONS


For an NMOS transistor to operate in saturation, the following conditions must be satisfied:


VGS > VT


VDS ≥ VOV


where


VOV = VGS − VT


For a PMOS transistor the saturation conditions are:


VSG > |VT|


VSD ≥ VOV


where


VOV = VSG − |VT|


# PROCEDURE


## 1. Inclusion of Technology Model


The TSMC 180 nm device model was first included in LTspice by adding the following library command:
.lib tsmc018.lib


This step allows LTspice to simulate the MOSFET devices accurately according to the selected technology.


## 2. Circuit Construction


The CMOS amplifier circuit was then created in LTspice. In this configuration, the PMOS transistor is connected to the supply voltage VDD and works as the load device. The NMOS transistor forms the amplifying stage and is connected to a source resistor. The output voltage is taken from the drain node of the NMOS transistor. Appropriate bias voltages are applied to the gate terminals of the transistors. A load capacitor is connected at the output node to represent the capacitive load.


## 3. Selection of Device Parameters


The channel length for both MOSFET devices was fixed as:

L = 360 nm


Initial width values for the NMOS and PMOS transistors were estimated using design calculations and later adjusted through simulation.


## 4. DC Operating Point Analysis


DC operating point analysis was performed using the LTspice command `.op`. This analysis provides information about the steady-state operating conditions of the circuit, including node voltages and drain current.


## 5. Bias Adjustment


The transistor widths were slightly modified during simulation until the desired operating point was obtained. The target operating conditions were a drain current close to 250 µA and an output voltage near 0.8 V.


## 6. Transient Analysis


A small sinusoidal input signal was applied to the circuit and transient analysis was performed using the `.tran` command. This analysis helps observe how the output signal changes with time.


## 7. AC Small-Signal Analysis


AC analysis was carried out by setting the AC input magnitude to 1 V and running the `.ac` command in LTspice. This analysis provides the frequency response of the amplifier and allows the determination of gain and bandwidth.


# DESIGN CALCULATIONS


## Drain Current Selection


The design drain current was selected as:


ID = 250 µA


## Source Resistor Calculation


The voltage across the source resistor was assumed to be:


VRS = 0.2 V


RS = VRS / ID


RS = 0.2 / (250 × 10⁻⁶)


RS = 800 Ω


## Output Voltage


To allow maximum signal swing, the output voltage was chosen near the middle of the supply range.


Vout = VDD/2 + IDRS


Vout = 0.6 + 0.2


Vout = 0.8 V


## Gate Voltage


For the NMOS transistor:


VGS ≈ 0.61 V


Source voltage:


VS = IDRS


VS = 0.2 V


Therefore the gate bias voltage becomes:


VB1 = VGS + VS


VB1 = 0.61 + 0.2


VB1 = 0.81 V


## Device Dimensions


After theoretical calculations and simulation adjustments, the final transistor sizes were selected as:


Wn = 30 µm


Wp = 128.5 µm


L = 360 nm

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-09%20224748.png)


# DC ANALYSIS

DC analysis is used to determine the quiescent operating point of the amplifier and to ensure that the MOSFET devices operate in the saturation region.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-09%20224821.png)


From the LTspice operating point simulation:

Drain current


ID ≈ 250 µA


Output voltage


Vout ≈ 0.798 V


The simulated output voltage is very close to the designed value of 0.8 V, confirming that the circuit biasing is correct.


# TRANSIENT ANALYSIS


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-09%20225009.png)


Transient analysis studies how the circuit responds to a time-varying input signal.


From the waveform obtained during simulation:


Maximum output voltage


Vmax = 930.23 mV


Minimum output voltage


Vmin = 634.74 mV


Output peak-to-peak voltage:


Vout(pp) = Vmax − Vmin


Vout(pp) = 930.23 −634.74


Vout(pp) = 295.49 mV


Input peak-to-peak voltage:


Vin(pp) = 20 mV


## Voltage Gain


Av = Vout(pp) / Vin(pp)


Av = 295.49 / 20


Av ≈ 14.77 V/V


## Gain in Decibels


Gain(dB) = 20 log10(Av)


Gain ≈ 23.38 dB


# AC ANALYSIS

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-09%20225438.png)


AC analysis determines how the amplifier gain changes with frequency.


From the AC magnitude plot, the midband gain is approximately:


Gain ≈ 23.7 dB


Converting to linear scale:


Av = 10^(23.7 / 20)


Av ≈ 15.34


# Bandwidth


The −3 dB bandwidth occurs at approximately:


BW ≈ 15 MHz


This frequency corresponds to the point where the gain falls by 3 dB from the midband gain.



# Unity Gain Bandwidth


Unity gain bandwidth is calculated using:


UGB = Av × BW


UGB = 15.34 × 15 MHz


UGB ≈ 230 MHz


From the simulation plot, the unity gain frequency is approximately:


UGB ≈ 244 MHz


The slight difference is mainly due to parasitic capacitances and non-ideal transistor behavior.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-09%20225704.png)


# RESULT


The CMOS amplifier using an NMOS transistor with a PMOS active load was successfully designed and simulated using TSMC 180 nm CMOS technology.


DC analysis confirmed a drain current close to 250 µA and an output voltage near 0.8 V. Transient analysis showed that the output signal was amplified to approximately 295 mV peak-to-peak for an input signal of 20 mV. This corresponds to a voltage gain of about 14.77 V/V (23.38 dB).


AC analysis indicated a midband gain of approximately 23.7 dB and a bandwidth of about 15 MHz. The unity gain bandwidth obtained from the calculations was around 230 MHz, which closely matches the simulated value.


# INFERENCE


From this experiment it can be concluded that the CMOS amplifier configuration using an NMOS transistor with a PMOS active load operates as expected. DC analysis confirmed proper biasing and ensured that the transistors operate in the saturation region. Transient analysis demonstrated the amplification of small input signals. AC analysis showed the gain and bandwidth characteristics of the amplifier. The close agreement between calculated values and simulation results indicates that the amplifier design is correct and effective.
