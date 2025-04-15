# -Experiment-3-Current-mirror-EC086
## Current Mirror
## Aim:1. To design and analyze a current mirror circuit as a load in an amplifier circuit and evaluate its performance through DC, AC, and transient analysis.
## Design Question:
Design a current mirror circuit with Av>10V/V, Vdd=1.8V, P <=1mW for the current mirror ratio 1:1 and 1:2.
![WhatsApp Image 2025-03-23 at 18 11 29_e757dcd2](https://github.com/user-attachments/assets/c572efeb-975c-4756-9084-6cc557031bc8)

and incorporate the design in the differential amplifier circuit with specifications as in exp -3.
## Theory:
 A current mirror is a circuit that copies a reference current to another branch of the circuit. It consists of two MOSFETs (M1 and M2) connected so that their gate terminals are tied together, ensuring that they operate at the same gate-to-source voltage (Vgs). The source of M1 is connected to a reference current source, which sets the gate voltage for both transistors. Since both transistors have the same Vgs, the current through M1 is mirrored to M2, provided that both transistors are in the saturation region.

In an amplifier circuit, using a current mirror as the load increases the gain by providing a high output impedance. The voltage gain of a common-source amplifier with a current mirror load is given by:
**Av = g<sub>m</sub>*R<sub>d</sub>** ;g<sub>m</sub> = 2*I<sub>d</sub>*V<sub>ov</sub> 

![WhatsApp Image 2025-03-24 at 19 06 04_008f5f88](https://github.com/user-attachments/assets/7cafab1b-26ab-4373-8526-e2b957a77876)

The current mirror improves the amplifier’s gain because the output resistance of the mirror increases the overall impedance at the output, which enhances the gain. The mirrored current depends on the size ratio of the transistors, which is expressed as:
**I<sub>out</sub> = I<sub>r</sub> * (w/l)<sub>1</sub>/(w/l)<sub>2</sub>**;Ir = Reference current.

For ideal current mirroring, the mirrored current should match the reference current. However, due to real-world effects like **channel length modulation and threshold voltage mismatch**, there can be small variations in the mirrored current.

#### **Channel-Length Modulation in MOSFET**
In an ideal MOSFET operating in the saturation region, the drain current is independent of the drain-to-source voltage (). However, due to the physical shortening of the effective channel length caused by an increase in , the actual drain current increases slightly with increasing . This phenomenon is called channel-length modulation.

![image](https://github.com/user-attachments/assets/0957afc5-3814-4cc6-baf4-36da9cb86419)

#### **Impact of PVT (Process, Voltage, and Temperature) Variations**:
In real circuits, performance is affected by variations in manufacturing, operating voltage, and temperature. These are known as PVT variations:
#### **Process Variations:** Differences in transistor dimensions, doping concentrations, and oxide thickness during fabrication affect parameters like threshold voltage (Vth), mobility (μ), and transconductance. This results in variations in the mirrored current and gain.

#### **Voltage Variations:** Changes in supply voltage affect the gate overdrive voltage and operating point of the transistors. This leads to variations in mirrored current and can shift the output operating range of the amplifier.

#### **Temperature Variations:** Temperature changes affect carrier mobility and threshold voltage. Higher temperatures reduce mobility, leading to a decrease in transconductance and gain. Threshold voltage also decreases with increasing temperature, which can shift the operating point of the transistors.

To minimize the effect of PVT variations, symmetric transistor layout, cascode current mirrors, and feedback techniques are used. Cascode mirrors provide higher output resistance and better matching, making the circuit more stable under varying conditions.

![WhatsApp Image 2025-03-23 at 18 47 21_69759897](https://github.com/user-attachments/assets/0c6a449e-62e2-4493-889c-32e506ff133d)

#### Impact on Current Mirror

1. Reference Transistor Behavior
In a current mirror, the reference current is defined by the gate-to-source voltage () of the reference transistor (). Since  is diode-connected (with ), channel-length modulation slightly increases the reference current with increasing .

3. Mirrored Current Deviation
The mirrored current in the output transistor () is affected because the output transistor sees a different drain-to-source voltage (). Due to channel-length modulation, the mirrored current becomes\
**Iout= Iref(1+ lamda*Vds)**

5. Output Resistance Degradation
The output resistance of the current mirror is reduced due to channel-length modulation. The small-signal output resistance is:
**r_{out} = 1/(lamba*Id)}**
A higher channel-length modulation effect (higher ) reduces , leading to lower output impedance and higher current variation with load.
Low output resistance reduces the effectiveness of the current mirror as an ideal current source.

![image](https://github.com/user-attachments/assets/9b5ba9d1-771a-445e-b0a0-37f7b0e314fb)

#### **Differential Amplifier with Current Mirror Load**

A differential amplifier amplifies the difference between two input signals while rejecting common-mode signals. When a current mirror is used as the load, it provides higher output impedance and better gain. 

In a typical configuration, the sources of two MOSFETs are connected to a current source, and their drains are connected to a current mirror load.
The voltage gain of a differential amplifier with a current mirror load is:
**A<sub>v</sub> = g<sub>m</sub>*R<sub>d</sub>**
For a matched pair of transistors, the differential gain becomes:
A<sub>v</sub> = un*Cox*(w/l)*(Vov)/(lambda*I<sub>d</sub>) 

The current mirror ensures that the output current reflects the differential signal accurately while rejecting common-mode signals. This improves the signal-to-noise ratio and makes the amplifier more stable.

#### **Impact of PVT Variations on Differential Amplifier:**
**Process Variations:** Differences in transistor sizes and threshold voltages cause imbalance in the differential pair, reducing the common-mode rejection ratio (CMRR). Careful transistor matching and symmetric layout minimize these effects.

#### **Voltage Variations**: Changes in supply voltage affect the biasing of the differential pair and the current mirror, altering the operating point and reducing gain. A regulated bias circuit helps stabilize the operating point.

#### **Temperature Variations:** Higher temperatures reduce mobility and increase leakage currents, lowering gain and causing offset drift. Designing for low temperature sensitivity and using temperature compensation techniques help reduce these effects.

To improve performance under PVT variations, careful layout, matching of transistor dimensions, and the use of regulated bias circuits are essential. Cascode mirrors and active feedback further enhance gain and reduce sensitivity to variations.

![image](https://github.com/user-attachments/assets/adb54238-c8d1-4558-9ee5-98a4af3fe74b)

## Procedure:
1. Create a new experiment file.
2. Build the respective circuit diagram as per the design question and set the length and wisth of the corresponding n and p channel mosfets as per the current mirror ratio fopr Part A and only to the current mirror circuit to set the DC operating point for Circuit Part 2 with the previous simulation file .
3. Vary the length and width by maintaing the constant current mirror ratio as peer the requirement and note the corresponding changes in the current flowing through the circuit . Compare and plota comparision table .
4. Perform the transient analysis and observe the gain , variations in input and output waveform.
5. Perform the AC analysis and analyze the frequency response of the circuiit and calculate the 3dB Bandwidth


   ## calculation:

we can see Itotal = P/VDD = 1 mW /1.8 V = 0.555 mA

Next, we know that Itotal = Iref + IX, where IX = ID. Since the (W/L) ratio specified to us is 1:1, IX + Iref = (Itotal/2) = 0.2777 mA. In the next question, where (W/L) ratio is 1:2, the value of IX = (Itotal/3).

Next, we need to calculate how much input voltage we will need to give the N-channel MOSFET, for it to work as an amplifier (with gain ≥ 10 V/V).

We know that AV = -gmRout = -gm(ro1||ro2), where ro1, ro2 are the dynamic output resistances of the NMOS, PMOS respectively, due to channel length modulation.

Since we know that ro1 = 1/λ1ID1, ro2 = 1/λ2ID2, where ID1 = ID2 = ID.

ro1 || ro2 = 1/ID (λ1 + λ2) = 1/ (0.277 x 10-3 x (1.382 + 1.329)) = 1331.65 Ω = 1.331 kΩ

Note that values for λ1, λ2 have been obtained from the TSMC 180 nm process technology .lib file, where the parameter for these values is PCLM (Channel Length Modulation Parameter).

We can also write gm as 2ID/VOV. Finally, substituting all of this back into our original equation, we get,

AV = (2ID/VOV). Rout, from which we can calculate VOV as 0.0737V.

VGS = VOV + Vt = 0.0737 + 0.496 = 0.569V

Therefore, our input voltage for the NMOS is 0.569 V.

## Circuit Diagram


![Image](https://github.com/user-attachments/assets/ec2151bc-207c-4274-8590-bd2b55cb9e2c)

For the P-channel MOSFETs, M1, M2: - W = 10 µm, L = 180 nm

For the N-channel MOSFETs, M3: - W = 31.23 µm, L = 180 nm

## Results:
   
  **1. DC Analysis:**



**Simulation:**


 

![Image](https://github.com/user-attachments/assets/0e95cf48-10cf-4d69-81bd-b9b93d86a8dd)


From here, we can see that the simulation is closely matching with our calculated values, since the current flowing through the NMOS (M3), PMOS (M1, M2) are nearly identical. From this, we can verify whether the circuit is following our power requirements, which is a key part in the design of any IC or chip.

P = Itotal * VDD = 0.55401 mA * 1.8 V = 0.9972 mW, which is within our power budget.


##



**2. TRANSIENT ANALYSIS :**

Next, we move on to transient analysis, where we can verify whether our V/V gain requirement is satisfied or not. To do this, we will configure our input voltage, Vin and convert it into a sinusoidal input with DC offset of 0.569V.

   
SIMULATION ;

**CIRCUIT DIAGRAM**

![Image](https://github.com/user-attachments/assets/cfb4e771-c3f1-4b11-a726-49a39abb3b6d)
  
![Image](https://github.com/user-attachments/assets/25d519bb-6c35-4d1c-8b95-1d2a646a9b95)

From here, we can see that the peak output voltage is 1.2381 V, for an input peak voltage of 10 mV. Now, we can calculate our gain, and verify our whether our gain requirement is satisfied or not.

AV = Vout/Vin = (0.96 – 1.2381)/(10 mV) = -27.81 V/V = 28.884 dB

This definitely satisfies our gain requirement, since we needed a V/V gain of ≥ 10 V/V.
   


**3. AC Analysis:**



SIMULATION;

![Image](https://github.com/user-attachments/assets/a2dc6a56-4ee7-447c-953b-8bd073272c14)


From here, we can see our 3 dB BW = 629.997 MHz – 0 = 629.997 MHz

The midband gain we are obtaining from our frequency response, i.e., 29.298 dB is also similar to the value we calculated, 28.884 dB.


##

**Circuit 2**: Ratio of 1:2 using L = 180 nm

For ratio of 1:2, then Iref = Itotal/3 = 0.183 mA


## Results:
   
  **1. DC Analysis:**


 








**CIRCUIT DIAGRAM**
![Image](https://github.com/user-attachments/assets/36341e18-89e7-49bc-8dcf-a9ee00b479c5)

Simulation:
![Image](https://github.com/user-attachments/assets/7780c762-cb9c-4b52-8625-4b9752fd4f16)
##

**2. TRANSIENT ANALYSIS :**
![Image](https://github.com/user-attachments/assets/b88b0cd1-9409-433e-afa9-9e1a827e2815)

Gain (V/V) = (1.26006-0.96)/ (-10 mV) = 30.006 V/V = 29.544 dB for an input voltage of 10 mV peak voltage, frequency of 1 kHz, sine wave. Let us perform the frequency response to verify this.






      


**3. AC Analysis:**

![Image](https://github.com/user-attachments/assets/3acb08f2-d3f2-45df-b60a-43277c4844ad)

From here, we can see that our midband gain is around 29.325 dB, which is a close match with our calculated value of 29.544 dB, which gives a V/V gain of around 29.25 V/V, not that far off from our calculated gain of 30.006 V/V.

ii. Analysis using L = 500 nm

1:1 using L = 500 nm

![Image](https://github.com/user-attachments/assets/d02fcd10-2213-457d-aeb4-51c4b3f64438)

For CMOSN (M3), W = 65.19 µm, L = 500 nm

For CMOSP (M1, M2), W = 10 µm, L = 500 nm





 



   
  **1. DC Analysis:**






**Simulation:**

 ![Image](https://github.com/user-attachments/assets/ec924264-7fe7-4a79-8d8f-93df2dadeb4d)



**2. TRANSIENT ANALYSIS :**

   
SIMULATION ;

![Image](https://github.com/user-attachments/assets/c08a1671-5737-4771-a763-3009ccb09607)






**3. AC Analysis:**
![Image](https://github.com/user-attachments/assets/a933724e-1040-44be-9ecb-351167d71c3f)

Gain = 37.87023 dB, 3 dB BW = 122.329 MHz

ii. Circuit 2: Ratio of 1:2 using L = 500 nm

For CMOSN (M3), W = 85.243 µm, L = 500 nm

For CMOSP (M1), W = 10 µm, L = 500 nm

For CMOSP (M2), W = 20 µm, L = 500 nm




**DC Analysis** 


![Image](https://github.com/user-attachments/assets/c3110c68-bd15-4621-98c9-18445818b579)

**Transient Analysis**

![Image](https://github.com/user-attachments/assets/f8e723d8-2f42-4a3b-a358-e383ae096daf)

Gain (V/V) = -62.063 V/V = 35.855 dB

**AC Analysis **
![Image](https://github.com/user-attachments/assets/a55767d5-dfc6-4795-9906-c596e12ad5cd)

3 dB BW = 93.0732 MHz, Gain (dB) = 38.015 dB


**ii.** Analysis using L = 1 µm

Ratio of 1:1
For CMOSN (M3), W = 93.35 µm, L = 1 µm

For CMOSP (M1), W = 10 µm, L = 1 µm

For CMOSP (M2), W = 10 µm, L = 1 µm


![Image](https://github.com/user-attachments/assets/72c7e36d-a015-4acf-b172-b068f0ccbcdc)

**DC Analysis** 

![Image](https://github.com/user-attachments/assets/cea7a8f6-dc3b-40d3-82a4-38128c72ef35)

**Transient Analysis**
![Image](https://github.com/user-attachments/assets/6250ac05-3b87-4078-a973-31b4de6c5352)
Gain (V/V) = -60 V/V = 35.563 dB

**AC Analysis **

![Image](https://github.com/user-attachments/assets/ec83b222-5f20-4637-ba1e-2e7d6e61fa7d)

3 dB BW = 98.90171 MHz, Gain (dB) = 35.481 dB


ii. Analysis using L = 1 µm

Ratio of 1:2
For CMOSN (M3), W = 121.51 µm, L = 1 µm

For CMOSP (M1), W = 20 µm, L = 1 µm

For CMOSP (M2), W = 10 µm, L = 1 µm

![Image](https://github.com/user-attachments/assets/d47a98b0-c9f5-459e-abfd-b04bb3b21d17)


**DC Analysis** 

![Image](https://github.com/user-attachments/assets/6520927e-11a6-4cff-a272-0795f1a09515)

**Transient Analysis**

![Image](https://github.com/user-attachments/assets/5e2e6585-a357-4b1d-a43b-4f0fdb3b7f32)


**AC Analysis **
![Image](https://github.com/user-attachments/assets/9bed2220-2883-4cce-bc5b-37911eb5958b)
3 dB BW = 57.2524 MHz, Gain (dB) = 38.69341 dB



Table of Comparisons


![Image](https://github.com/user-attachments/assets/40f752c8-01a6-4543-86d3-f44ab0a44b3d)




Part 2: Differential Amplifier

Now that we have understood the basics of the current mirror, we will move onto using it to design our differential amplifier, using the same parameters that we designed for the differential amplifier simulation.


![Image](https://github.com/user-attachments/assets/051f41e4-4993-4cf7-ad5d-6920f64d0cad)



For the N-channel MOSFETs (CMOSN), the W/L ratios are as follows: -

M1, W = 108.5 µm, L = 180 nm

M2, W = 108.5 µm, L = 180 nm

M3, W = 22.42 µm, L = 180 nm

M6, W = 10 µm, L = 180 nm

The reason for the (W/L) ratio of M3 being more than double that of M6 is because the current flowing through M3 should be double than the current of M6, i.e., IM3 = 1.222 mA, while IM6 = 0.611 mA.

This is also the same reason why M4, M5 have the same (W/L) ratios, so that equal amounts of current flows through both transistors.

For the P-channel MOSFETs (CMOSP), the W/L ratios are as follows: -

M4, W = 52 µm, L = 180 nm

M5, W = 52 µm, L = 180 nm

M6, W = 10 µm, L = 180 nm


**DC Analysis** 
![Image](https://github.com/user-attachments/assets/6561386e-a36f-4bef-b889-a45e8e6db07d)

As we can see, for our (W/L) ratios, the values we obtain from the DC analysis closely match the ones we require.


Transient Analysis

![Image](https://github.com/user-attachments/assets/29a2b47d-d538-4e72-bd24-46d0e78416f8)











We have supplied a differential input of 10 mV peak voltage, 1 kHz frequency, sine wave. The input is differential, i.e., only to the gate of M1, since the output of a differential amplifier is the difference in drain voltages of M1, M2. Since the output is a difference, if we supply common input, the amplifier will reject the signal and provides very little to no gain (ideally).

Av = (1.092 – 0.95)/ (-10 mV) = -14.2 V/V = 23.045 dB

**Results and Inferences**

The experiment demonstrates several important characteristics of current mirror circuits with varying channel lengths and W/L ratios:

1.Gain-Bandwidth Trade-off

There is a clear inverse relationship between gain and bandwidth across the different channel lengths. The 180 nm designs show modest gain (~29 dB) but exceptional bandwidth (>600 MHz), while the 1 μm designs provide much higher gain (~35-39 dB) at the expense of reduced bandwidth (<100 MHz).

2.Channel Length Effects

Increasing the channel length from 180 nm to 500 nm and then to 1 μm results in:

1.Increased gain: Due to reduced channel length modulation effects (λ) in longer channel devices, resulting in higher output resistance.

2.Decreased bandwidth: Due to increased parasitic capacitances associated with larger transistor dimensions.

3.Larger transistor widths required: NMOS widths had to be significantly increased (31 μm → 121 μm) to maintain the same current levels.

3.W/L Ratio Impact

The 1:2 ratio consistently outperforms the 1:1 ratio in terms of gain across all channel lengths:

1.For 180 nm: Modest improvement (29.298 dB → 29.325 dB)

2.For 500 nm: Slight improvement (37.87 dB → 38.015 dB)

3.For 1 μm: More significant improvement (35.481 dB → 38.693 dB)

The current mirror circuit's performance can thus be tailored to specific application needs by selecting appropriate channel lengths and W/L ratios, with clear trade-offs between gain, bandwidth, and silicon area (as evidenced by the increasing transistor widths required for longer channel designs).
