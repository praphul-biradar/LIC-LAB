#  EXPERIMENT 03 VIRTUAL LAB


# Characterization and Parameter extraction of M741 Operations Amplifier (µA741).

 
# Aim :
To find key parameters of the experiment on µA741 operational amplifier experimentally and compare experimental results with the standard datasheet values. 

 
# Apparatus Required


* µA741 operational amplifier IC

  
* Dual DC power supply

  
* Digital multimeter (DMM)

  
* Function generator / A.F. oscillator


A functional generator that can be operated as either an arreste contacted oscillator or a free oscillator, with the frequency adjustable according to the needs of a specific user application.<|human|>A functional generator may be made with the same design, but intended to be an arreste contacted oscillator (an arreste contacted oscillator) or a free oscillator (a free oscillator), with the frequency adjusted to suit the requirements of the particular use.


* CRO / DSO

  
* Breadboard and wires connection.

 
# Measurement of Inverting Bias Current (IB 1 )

![Image description]( https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214623.png)

where IB 1 is the current flowing between the two areas of the capacitor, and V 1, V 2, and V 3 denote the voltages across the capacitor, resistor, and load, respectively, in the circuit below:


Current through the area of the capacitor is equal to the difference of the voltages across the capacitor and resistor: V 1 IB - V 2, V 3 IB - V 2.
Substituting V 1, V 2


1. Put the necessary electronic parts on the workstation.


2. As inverting bias current measurement, connect the circuit as depicted in the circuit diagram below.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214703.png)

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214718.png)


3. Confirm the connections with the aid of the Check Connection option.


4. After the connections are right, monitor the voltage on the digital multimeter.


5. Inverting bias current is calculated with the help of:


IB₁ = Vo / Rf


Given:


Vo = 0.024 V


Rf = 470 kΩ = 470000 Ω


# Calculation:


IB₁ = 0.024 / 470000


IB₁ = 5.106 × 10⁻⁸ A


Converting to nanoampere:


IB₁ ≈ 51 nA


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214735.png)


# The measurement of Non-Inverting Bias Current (IB 2 ) is achieved using the method of measurement of a current.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214744.png)


1. Connect the circuit as shown in the circuit diagram in determining the bias current non-inverting.


2. Check the wiring connections.

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214756.png)  


3. Record the value of the multiplexed voltage on the multimeter.


4. Divide the non inverting bias current by:


IB₂ = Vo / R₁


# Given:


Vo = −0.020 V


R₁ = 470 kΩ = 470000 Ω


# Calculation:


IB₂ = −0.020 / 470000


IB₂ = −4.255 × 10⁻⁸ A


# Considering magnitude:


IB₂ ≈ 42.6 nA


# Input Bias Current (IB)


The mean current of the input bias of the op-amp is as follows:


IB = (IB₁ + IB₂) / 2


Substituting values:


IB = (51 + 42.6) / 2


IB ≈ 46.8 nA


Input Offset Current (Iio) can also be measured.


1. Set the circuit as shown in the input offset current measurement diagram.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214805.png)


2. Test the circuit connections.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214814.png)


3. Measure the output voltage through the use of the digital multimeter.


4. Input offset current is computed by using:


Iio = Vo / Rf


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214827.png)


Given:


Vo = 0.003 V


Rf = 470 kΩ = 470000 Ω


Calculation:


Iio = 0.003 / 470000


Iio = 6.38 × 10⁻⁹ A


Converting units:


Iio = 6.38 nA


Iio = 0.00638 µA


Measurement of Input Offset Voltage (Vio) - adjusting the input offset voltage will allow the power output to be set to the desired level.Measurement of the Input Offset Voltage (Vio) - it is the adjustment of the input offset voltage that will allow the power output to be adjusted to the desired level.


1. Connect the circuit as illustrated in the diagram by having the circuit components in place.

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214836.png)


2. Before going ahead, check out all connections.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214843.png)


3. Record the value of the DMM output.

![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214850.png)


4. Input offset voltage is given as;


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214900.png)


Vio = Vo / (1 + Rf / Ri)


Given:


Vo = 0.106 V


Rf = 100 kΩ


Ri = 10 kΩ


Calculation:


Vio = 0.106 / (1 + 100k / 10k)


Vio = 0.106 / (1 + 10)


Vio = 0.106 / 101


Vio = 0.001048 V


Converting to millivolts:


Vio ≈ 1.048 mV


# Measurement of Slew Rate (SR)


1. Connect the circuit of slew rate measurement.


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214909.png)


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214914.png)


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214921.png)


2. Use a feed-in signal of the function generator.


3. Attack the input signal to Channel-1 of the CRO and the output of the op-amp to Channel-2.


4. Increase the input signal frequency gradually till the output waveform turns to a triangle shape.


5. Note this frequency as the highest frequency (f max ).


6. The computation of slew rate is based on the following:


SR = 2π fmax Vm / 10⁶  V/µs


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214941.png)


![Image description](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-06%20214949.png)


Given:


Vm = 3 V


fmax = 25 kHz = 25000 Hz


Calculation:


SR = (2π × 25000 × 3) / 10⁶


SR = 471000 / 10⁶


SR ≈ 0.471 V/µs


# Result


The values of the µA741 parameters were determined in the following way:


* Inverting Bias Current (IB₁) = 51 nA


* Non-Inverting Bias Current (IB 2 ) = 42.6 n A.


*average input bias current (IB): = 46.8 nA.


* Input Offset Current (Iio) = 6.38 nA


* Input Offset Voltage (Vio) = 1.048 mV


* Slew Rate (SR) = 0.471 V/µs


The measured values are nearly similar to the standard specifications listed in µA741 datasheet. 


# Inference


The experiment was able to identify important parameters of the µA741 operational amplifier. The input bias current with the offset current and offset voltage and slew rate are measured values that are expected to have datasheet values. Because the analysis was conducted through a simulated/controlled environment then the practical considerations like temperature changes and component tolerances played no significant role in the analysis. The experiment verifies the common performance features of the µA741 op-amp and its application in low-frequency analogous tasks.
