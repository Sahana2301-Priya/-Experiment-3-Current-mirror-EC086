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
