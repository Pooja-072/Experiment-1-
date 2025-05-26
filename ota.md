# FOLDED CASCODE OPERATIONAL AMPLIFIER WITH CASCODE PMOS LOADS
<br>

### What is a Folded Cascode Transconductance Amplifier?<br>
A Folded Cascode Transconductance Amplifier (OTA) is a type of operational amplifier where the input differential pair is connected to a folded cascode structure to achieve high gain, wide input range, and better output swing, especially in low-voltage CMOS processes.<br>
* “Folded” refers to rerouting the current from the input NMOS pair (or PMOS) into a cascode stage made of the opposite type (PMOS or NMOS), creating a "fold" in the signal path.<br>
* It converts differential input voltage into output current, hence the name transconductance amplifier.<br>
<br>

### Working Principle of Folded Cascode Transconductance Amplifier<br>
The Folded Cascode OTA amplifies a differential input voltage by converting it into a current through an NMOS input pair, and then "folds" this current into a PMOS cascode load to produce a high-gain output.<br>
<br>

![image](https://github.com/user-attachments/assets/7886520a-91cf-4c97-9acb-63a6ce94241b)

####  Step-by-Step Operation::<br>
###### 1.Differential Pair Operation (M1 & M2):<br>
* A small difference in Vin⁺ – Vin⁻ causes a differential current to flow between M1 and M2.<br>
* This current represents the input voltage converted to current (transconductance stage).<br>
###### 2.Folding Action (M3 & M4):<br>
* Instead of stacking NMOS transistors (as in telescopic OTA), the currents from M1 and M2 are “folded” down into PMOS devices (M7, M8) using NMOS folding transistors M3 and M4.<br>
* This allows PMOS cascodes to receive NMOS current, saving headroom.<br>
###### 3.Cascode Load (M7–M10):<br>
* PMOS cascode transistors (M7, M8) increase the output resistance, boosting gain.<br>
* M9 and M10 provide biasing to keep the cascode devices in saturation.<br>
###### 4.Tail Current Source (M5 & M6):<br>
* These control the total current through the differential pair and folding path, keeping the amplifier biased and balanced.<br>
###### 5.Output Node:<br>
* The amplified differential current is mirrored through the cascode branch, and the voltage appears across the high impedance output node, producing Vout.<br>
<br>
------------------------------------------------------------------------------------------------<br>
## DESIGN QUESTION:<br>
<Br>
#### Design a single-stage folded-cascode operational amplifier using 180nm CMOS technology with a ±0.9V supply (1.8V total). The amplifier should use an NMOS differential input pair for improved common-mode range and an actively biased PMOS cascode load to achieve high gain. The design must target a DC gain of at least 50 dB, consume approximately 0.35 mW power. The tail current should be around 10 µA and maximum output swing=1.6V.<br>

Given,<br>
maximum output swing ,<br>
Voutpp = Vdd - [ Vov5 + Vov3 + |Vov4| + |Vov7| ]<br>
0.8 = 1.8 - [ Vov5 + Vov3 + |Vov7| + |Vov9| ]<br>
[ Vov5 + Vov3 + |Vov7| + |Vov9| ] = 1 V<br>
<br>
PMOS Vov should be greater than NMOS Vov to ensure PMOS stays in saturation, maintaining high gain.<br>
| Vov of PMOS | > Vov of NMOS (as μpCox < μnCox)<br>
Therefore,<br>
Vov7 = Vov9 = 0.3 V<br>
Vov3 = Vov5 = 0.2 V<br>
<br>
Given the reference current , Iss = 10u A<br>
Id1 = Iss/2 = 5uA<br>
Id (1,2) = 5uA ( current divides equally when vgs are same )<br>
The current across mosfets M3,4,7,8,9,10 be,<br>
Id2 = 5uA<br>
So,<br>
The current across M5 and M6 becomes  ,<br>
Id(tot) = Id1 + Id2 = Iss = 10uA.<br>
<br>
Also ,<br>
Power ≤ 0.35 mW<br>
P = Vdd (Iss) = 1.8 (10u) = 18 u<br>
18u<=35mW<br>
<br>
The Bias Voltages<br>
Vb2 = Vgs5 = Vov5 + Vth5 = 0.2 + 0.5<br>
Vb2=0.7  V<br>
(practical case used Vb2 = 1.8V to keep m5 and m6 in saturation )<br>
Vgs3 = Vg3 - Vs3<br>
Vgs3 = Vb1 - Vov5<br>
Vb1 = Vgs3 + Vov5 = ( Vov3 + Vth3 ) + Vov5<br>
Vb1=0.9 V<br>
(practical case used Vb2 = 2.3V to keep m3 and m4 in saturation)<br>
Vsg9 = Vs9 – Vgs<br>
Vgs9 = Vdd - Vb4<br>
Vb4 = Vdd - ( Vov9 + Vth9 ) = 1.8 - ( 0.3 + 0.39 )<br>
Vb4 = 1.11 V<br>
(practical case used Vb4 = 1V to keep m3 and m4 in saturation )<br>
Vsg7 = Vs7 - Vg7<br>
Vs7 = Vdd - |Vov9| = 1.8 - 0.3 = 1.5 V<br>
Vsg7 = 1.5 - Vb3<br>
( Vov7 + Vth7 ) = 1.5 - Vb3<br>
Vb3 = 1.5 - ( 0.3 + 0.39 )<br>
Vb3 = 0.81 V<br>
( practically used diode connected mosfet to keep m7 and m8 in saturation and to increase the output voltage )<br>
<br>
μₙCₒₓ = 200 μA/V² & Vov (NMOS) = 0.2 V<br>
μₚCₒₓ = 100 μA/V² & Vov (PMOS) = 0.3 V<br>
L = 180 nm (0.18 µm)<br>
Id = 1/2•unCox(W/L)Vov^2<br>
1. For NMOS : W/L = 2*5*10^-6/200*10^-6*(0.2)^2 =1.25<br>
2. For PMOS : W/L = =2*5*10^-6/100*10^-6*(0.3)^2=2.22<br>
<br>


























