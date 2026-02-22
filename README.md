LIC LAB

EXPERIMENT  01


Aim
To create a PMOS Common Source amplifier with 180 nm CMOS technology with specified voltage and power limit, and to investigate its functioning in DC analysis,
transient analysis, and AC analysis in LTspice. 



Given Specifications

1. Supply voltage (VDD) = 1.2 V
2.Maximum power ≤ 0.4 mW
3.Load capacitance (CL) = 0.5 pF
4.Channel length (L) = 360 nm



Components Required
PMOS transistor (TSMC 180 nm model), drain resistor, DC source, signal source and capacitor.



Theory

The most significant feature of modern integrated circuits is the contribution of MOSFETs owing to the reduction in size, low power requirements,
large-input impedance, and capability to employ scaled VLSI technology. They may exist in the form of NMOS or PMOS and may be used in three common source,
source follower and common gate modes of amplifiers. The Common Source arrangement is the most implemented in an analog circuit of these, due to its high voltage gain and phase inversion. 
The PMOS transistor must be made to be in a saturation state where it behaves as a voltage-controlled current source in order to be correctly amplified. The following are the conditions of saturation:

1. VSG > |VT|
2.VSD ≥ VSG − |VT|

Overdrive voltage:
VOV = VSG − |VT|


Procedure

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


Design Calculations

1. Drain Current
Power relation:
P = VDD × ID
ID = P / VDD = 0.4 mW / 1.2 V = 0.333 mA

We will choose value less than 0.333mA :
ID ≈ 250 uA


2. PMOS Width Calculation
Having equation of saturation current:
ID = (1/2) μp Cox (W/L) (VOV)^2
up = 0.0115689 m^2/V·s
Cox = 0.0084207 F/m^2
L = 360 nm = 360 × 10^-9m 
VOV = 0.2094 V
ID = 250 uA = 250 × 10⁻^6A

On substitution :
W ≈ 42 um


3. Output Voltage
VD ≈ VDD / 2 = 0.6 V


4. Drain Resistance
RD = VD / ID = 0.6 / (250 uA) = 2.4 kΩ


5. Gate-Source Voltage
|VT| = 0.3906 V
Choose VSG ≈ 0.6 V
Overdrive voltage:
VOV = 0.6 − 0.3906 = 0.2094 V


6. Gate Voltage
VS = 1.2 V
VG = VS − VSG = 1.2 − 0.6 = 0.6 V


7. Saturation Verification
VSD = VS − VD = 1.2 − 0.6 = 0.6 V
VOV< VSD    Mosfet is in saturation.


Final Calculated Values
Id ≈ 250 uA
Vd ≈ 0.6 V
Rd = 2.4 ohm
Vg = 0.6 V
VOV = 0.2094 V


CIRCUIT 

![Image description](PASTE_FILENAME_HERE)











