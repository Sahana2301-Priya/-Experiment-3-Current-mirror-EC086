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
## Part A :
## Design Calculation:
As we know It=Iref+Ix\
Therefore, for 1:1 ratio Iref=Ix\
So,Iref=It/2\
It=P/Vdd\
It=1mW/1.8V\
It=0.555mA.\
Therefore,Iref=0.2778mA.\
## Circuit Diagram:
![{781234F8-A55B-4024-B645-163C13B1F41E}](https://github.com/user-attachments/assets/c8108b74-7382-43ea-ac34-64b304012d59)

### DC Analysis:
![{D1277AED-516A-4264-A31B-71A8158764AA}](https://github.com/user-attachments/assets/eb9bc24a-67f5-4c07-a9ca-957f3284ef44)

when L= 180n , W= 3u in all the mosfets , current Iref = Id1=Id2=Id3 = 0.2778mA(approx)
(w/l)=16.66
Analysis when length is varied by maintaining the (w/l) ratio as 16.66\
<table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>180nm</td>
    <td>180nm</td>
    <td>180nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>3µm</td>
    <td>3µm</td>
    <td>3um</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> =  0.002778A </td>
      <td> I<sub>d</sub> = 0.000277527A </td>
      <td> I<sub>d</sub> =0.000277527A </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td> --- </td>
      <td> 0.836V</td>
    </tr>
</table>
a) Length = 500n that implies width = 500*16.66 = 8.33u

![{EDCCA100-448D-4697-8C96-387653B85749}](https://github.com/user-attachments/assets/10af0b9c-8199-4392-815c-f324bacd2652)

<table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>50n</td>
    <td>500nm</td>
    <td>500nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>8.33µm</td>
    <td>8.33µm</td>
    <td>8.33um</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> =0.0002778| </td>
      <td> I<sub>d</sub> = 0.000281239 </td>
      <td> I<sub>d</sub> =0.000281239 </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td> --- </td>
      <td> 0.836V</td>
    </tr>
</table>

b) length = 1u that implies width w =16.66*1u=16.66u

![{93D4442A-DEF2-413E-BB6C-9C7BA851F607}](https://github.com/user-attachments/assets/ab808d08-1da4-4f60-82a8-c8112a3dc5d4)
<table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>`  1u</td>
    <td>1u</td>
    <td>1u</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>16.66µm</td>
    <td>16.66µm</td>
    <td>16.66µm</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> = 0.000277778A </td>
      <td> I<sub>d</sub> = 0.000280552A </td>
      <td> I<sub>d</sub> = |0.0002800552A </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td> --- </td>
      <td> 0.836V</td>
    </tr>
</table>

## Overall Comparision:
|Length|Width|Id(M1)|Id(M2)|Id(M3)|W/L RATIO|
|------|-----|---------|------|------|------|
|180n|3u|0.0002778|0.000277527|0.000277527|16.66|
|500n|8.33u|0.0002778|0.000281239|0.000281239|16.66|
|1u|16.66u|0.000277778|0.000280552|0.0002800552|16.66|


### Transient Anaslysis:
![image](https://github.com/user-attachments/assets/444950a2-a9c5-43ad-9d3c-ea9fff500dec)

There is 180 degree phase shift between input and o/p and the gain is (Vout/Vin)= 12.8( slightly greater than 10)  due to mismatching in transistors. 
### AC Analysis:
![image](https://github.com/user-attachments/assets/d69ee6e1-24a1-436c-a2d1-91a8bfe9aadb)
20 log (Av)= 20 dB but practical gain = 24 dB which is higher and **3dB Bandwidth = 1.02GHz**
## 1:2 Ratio 
### Circuit Diagram:
![image](https://github.com/user-attachments/assets/0571bce9-c77f-46ba-b960-00af0c865b9c)
### DC Analysis:
As we know It=Iref+Ix
Therefore, for 1:2 ratio 2*Iref=Ix\
So,Iref=It/3\
It=P/Vdd\
It=1mW/1.8V\
It=0.555mA.\
Therefore,Iref=0.185mA.

a) Length = 180n implies Width = 6u and w/l=33.33
<table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>180nm</td>
    <td>180nm</td>
    <td>180nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>3u</td>
    <td>6u</td>
    <td>6u</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> = 0.000185A </td>
      <td> I<sub>d</sub> = 0.000369916A </td>
      <td> I<sub>d</sub> =0.000369916A </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td>0.763V </td>
      <td>----</td>
    </tr>
</table>
<br>


b) Length = 500n that implies width = 500*33.33 = 16.66u

![{08F0597B-6EA9-4CC9-A08F-03077074FA7E}](https://github.com/user-attachments/assets/ebcd2331-6a54-420b-8c28-51a5c4c6e369)
<table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>500nm</td>
    <td>500nm</td>
    <td>500nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>8.33u</td>
    <td>16.66u</td>
    <td>16.66u</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> =0.000185A </td>
      <td> I<sub>d</sub> = 0.000379667A </td>
      <td> I<sub>d</sub> = 0.000379667A </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td>0.763V </td>
      <td>----</td>
    </tr>
</table>
<br>


c) Length = 1u that implies width =33.33*1u=33.33u\
![{EBE47F27-73F7-423E-AF86-1FFDCAD7F3A7}](https://github.com/user-attachments/assets/578da17c-2a30-4893-92e5-6859ff4598ea)
<table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>1u</td>
    <td>1u</td>
    <td>1u</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>13.33u</td>
    <td>16.66u</td>
    <td>16.66u</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> = 0.000185A </td>
      <td> I<sub>d</sub> = 0.000376678A </td>
      <td> I<sub>d</sub>= 0.000376678A </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td>0.763V </td>
      <td>----</td>
    </tr>
</table>
<br>


|Length|Width|Id(M1)|Id(M2)|Id(M3)|W/L RATIO|
|------|-----|---------|------|------|------|
|180n|6u|0.000185|0.000369916|0.000369916|33.33|
|500n|16.66u|0.000185|0.000379667|0.000379667|33.33|
|1u|33.33u|0.000185|0.000376678|0.000376678|33.33|
### Transient Analysis:
![image](https://github.com/user-attachments/assets/9e65a30e-c2a7-46f1-8b86-01e025ae248a)


The theoritical gain = 10V/V but practical is 11.54 with 180 degree phase shift between input and output.
### AC Analysis:
![image](https://github.com/user-attachments/assets/b85b5c5a-b4cf-4d1b-be55-8ec9e196df16)
3 dB Bandwisth = 2.04GHz and gain = 26dB
## Inference :
1. Impact of Width-to-Length Ratio (W/L) on Current Mirroring:
When the ratio is maintained at 1:1, both transistors in the mirror circuit have identical W/L ratios. This results in an almost perfect mirroring of the reference current ( mA) in the output branch, assuming ideal matching conditions and negligible channel-length modulation effects.\
For the 1:2 ratio (where one transistor has twice the W/L of the other), the expected mirrored current theoretically doubles. However, practical non-idealities such as mobility degradation, threshold voltage variations,  slightly impact the accuracy of current replication.\
The observed mirrored current for  mA is slightly different from the ideal value due to these second-order effects.
3. Effect of PMOS and NMOS Current Mirrors:
PMOS Current Mirror: Exhibits lower output conductance and better mirroring accuracy at higher output resistance due to the lower mobility of holes. The matching is affected by variations in threshold voltage () and body effect, which slightly alter the mirrored current.\
NMOS Current Mirror: Demonstrates higher transconductance due to higher electron mobility, making it more sensitive to process variations. However, the output impedance is lower, which may result in slight deviations in the expected mirrored current.

4. Biasing Considerations and Stability:
The applied gate bias  determines the operating point and ensures that the transistors remain in saturation for effective current mirroring.\
Any mismatch in threshold voltage (Vth) or mobility variations between the transistors affects the mirroring accuracy, leading to minor deviations from theoretical predictions.\
At smaller reference currents (e.g.,  mA for 1:2 ratio), the impact of channel-length modulation becomes more significant, leading to slight variations in the mirrored current.

6. Overall Performance Comparison:
1:1 Ratio: Provides better accuracy in current replication due to identical transistor dimensions.\
1:2 Ratio: Offers increased output current, but slight deviations occur due to non-ideal effects such as mobility degradation and process variations.

## Conclusion:
By maintaining a constant aspect ratio while varying transistor dimensions, the current mirror effectively scales the output current as expected. However, practical non-idealities such as threshold voltage mismatch, channel-length modulation, and process variations introduce minor deviations. PMOS mirrors provide higher output impedance and better matching at higher output resistances, whereas NMOS mirrors offer higher transconductance but are more sensitive to variations. Proper biasing and transistor sizing play crucial roles in optimizing mirroring accuracy and circuit stability.
## Part B:
### Design and analyze the differential amplifier using the same design specifications as in experiment three- differential amplifier. Perform dc transient and ac analysis.
![WhatsApp Image 2025-03-23 at 22 05 43_0bf4910c](https://github.com/user-attachments/assets/9a6bbad9-1198-42e9-b9cf-5e12e9507b94)
## Circuit Diagram:
![{3D9E37BA-6B67-47EE-885C-E686FACE6AAB}](https://github.com/user-attachments/assets/d290ce3a-8d5d-4397-94c8-4ca5fdc958f6)
## DC Analysis:
By keeping all the parameters constant as in the previous question of circuit 4 diagram with all the length as 180 nanometer and the corresponding width in the earlier question we vary only the width of the current mirror circuit to match the 1:2 as per the Design question provided above . To fix DC operating point to the fixed value of 1.4 Volt as mentioned in the previous question we vary the reference current to match the DC operating point and acquire the same.
![{7AC3A992-E7C4-4A00-ADE0-16E8F7F0363F}](https://github.com/user-attachments/assets/69b847fc-6c69-4deb-8819-8359894d40e5)

The current across the Mosfet M2 is twice that of the M6 Mosfet that is oh 0.1162mA and 0.6mA respectively.
## Transient analysis:
![image](https://github.com/user-attachments/assets/03dec1ac-12c1-497b-bbf9-978311843fa6)
Vout/Vin=(2.2/1.34)=1.64 and there is 180 degree phase shift beetween input and output.
## AC Analysis:
![image](https://github.com/user-attachments/assets/3b5ecb9f-2206-4974-b75a-5a5ee0fedc30)
There is a significant increase in the gain to around 33 dB. And the 3DB bandwidth is rise to 325.86 MHz.

## Conclusion:
Replacing the tail current source with a current mirror enhances the stability and performance of the differential amplifier. It improves CMRR, gain, and bias accuracy while maintaining robustness against variations. However, design considerations such as device matching and voltage headroom must be carefully managed.

## Inference:
By replacing the bias voltage of the MOSFET acting as a tail current source with a current mirror circuit, we achieve the following:
1. Improved Current Stability
The current mirror ensures a stable and well-defined tail current (Iss), reducing variations due to process and temperature changes.\
The reference current of 0.637 mA is accurately mirrored, ensuring consistent biasing for the differential pair.
3. Better Common-Mode Rejection Ratio (CMRR)
A current mirror provides a high impedance at the tail node, which improves the CMRR of the differential amplifier.\
This leads to better rejection of common-mode noise and enhances the circuit's differential gain performance.

4. Increased Gain
The high output impedance of the current mirror acts as an active load, increasing the differential gain of the amplifier.\
The gain is determined by the transconductance () of the differential pair and the impedance at the drain terminals.

6. Design Considerations
The choice of MOSFET dimensions (W/L) affects the current mirroring accuracy and output impedance.\
Care must be taken to ensure proper biasing and matching to minimize mismatch errors.
8. Trade-offs
While a current mirror provides better bias stability, it may introduce systematic offset due to transistor mismatches.\
The headroom requirement increases, potentially limiting the voltage swing of the circuit.







