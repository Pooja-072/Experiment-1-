# CURRENT MIRROR <br>
A current mirror is an essential circuit used in analog electronics to copy a reference current from one active device to another while maintaining a stable and accurate current flow (Iref = Iout). It is widely employed in biasing circuits, active loads, and differential amplifiers<br>
![what is current mirror](https://github.com/user-attachments/assets/1768da11-0189-48ea-9dc7-6f677b3c4609)
<br>
## WORKING PRINCIPLE OF CURRENT MIRROR :<br>

#### 1. Reference Current Generation:<br>
* The first transistor (M1) is configured in a diode-connected manner (drain and gate shorted).<br>
* A reference current Iref is forced through M1 using a current source or resistor.<br>
* This sets the transistor’s gate-source voltage (Vgs1) which defines the operating point.<br>
<br>

#### 2. Mirroring the Current<br>

* The second transistor (M2) has its gate connected to M1’s gate.<br>
* Since both transistors share the same (Vgs) , they ideally conduct the same drain current, provided they have the same W/L ratio and are in saturation.<br>
* The mirrored current (Iout) is approximately equal to Iref.<br>
<br>

#### 3. Output Current Scaling <br>

* If the W/L ratio of M2 is different from M1, the output current is scaled<br>
* I<sub>out</sub>/I<sub>ref</sub> = (W/L)<sub>2</sub>/(W/L)<sub>1</sub> <br>
therefore,<br>
I<sub>out</sub> = (W/L)<sub>2</sub>/(W/L)<sub>1</sub> * I<sub>ref</sub> <br>
<br>

## Key Conditions for Proper Operation : <br>

#### Both transistors should be in saturation<br>

This ensures that the drain current depends only on V<sub>gs</sub> and not on V<sub>ds</sub> <br>

#### Matching of Transistors <br>

Fabrication variations can cause mismatch in threshold voltage (V<sub>th</sub>), affecting accuracy.<br>

#### Channel Length Modulation<br> 

Practical mirrors suffer from a small variation in I<sub>out</sub>due to V<sub>ds</sub> changes.<br>
Using a cascode current mirror reduces this effect by increasing output resistance.<br>

## PMOS Current Mirror<br>

![image](https://github.com/user-attachments/assets/1a870006-1e99-448a-b5e7-c4ddd99f8417)
<br>
This shows the implementation of current mirror using the PMOS transistors. In PMOS current mirror, the source terminals for both transistors are connected to Supply voltage Vdd.<br>
The relation between the Iout and Iref can be given by the same expression.<br>
I<sub>out</sub> = (W/L)<sub>2</sub>/(W/L)<sub>1</sub> * I<sub>ref</sub> <br>
The only thing which needs to be ensured is that M1 should operate in the saturation region. Or in other words, VSD1 ≥ VSG – |VTP |, Where VTP is the threshold voltage of the PMOS transistor.<br>

-------------------------------------------------------------------------------------------------
## SIMULATION : NMOS current mirror circuit with a resistive load<br>
#### Circuit Components & Functionality:<br>
* V1 (1.8V Supply): Provides the operating voltage for the circuit.<br>
* Iref (100µA): Sets the reference current through M2.<br>
* M2 (Diode-Connected NMOS): Operates in saturation and sets the gate voltage Vx.<br>
*M1 (Mirroring NMOS): Copies the current from M2 to R1.<br>
*R1 (820Ω Load Resistor): Converts the output current into a voltage.<br>

![ckt dia](https://github.com/user-attachments/assets/f1a42946-8c17-4549-82df-3ef7a192b852)

#### OBSERVATION TABLE :<br>
For Iref = 100u<br>

|Iout (Expted)(A) |Iout(appeared)(A) |(W/L)<sub>2</sub> |(W/L)<sub>1</sub> | Vx (V) |Vout(V) |
|-----------------|------------------|------------------|------------------|--------|--------|
|100u             |103.5u            |180n/180n         |180n/180n         |1.27    | 1.71   |
|100u             |10.715u           |500n/500n         |500n/500n         |1.43    | 1.717  |
|100u             |100.648u          |1u/1u             |1u/1u             |1.39    | 1.7174 |
|200u             |197.6u            |1u/2u             |1u/2u             |1.397   |  1.63  | 
|100u             |101.5u            |1u/2u             |1u/2u             |1.087   | 1.716  | 
|100u             |102.131u          |1u/3u             |1u/3u             |0.95    |1.7172  |

* ##### Iout is slightly higher than the expected value in most cases.<br>
For W/L = 180n/180n , expected Iout=100uA, but appeared Iout = 103.5uA. This happens because as Vds increases, the effective channel length decreases, causing higher drain current.<br>
* ##### Higher W/L ratios (shorter channel lengths) show more deviation.<br>
For W/L = 500n/500n , Iout=100uA drops significantly (10.715μA), indicating increased channel length modulation effects.Shorter channel lengths mean higher λ, leading to larger variations in current.<br>
* ##### For longer transistors (L increased),Vx is lower, stabilizing Iout): <br>
Vx decreases as L increases .<br>

------------------------------------------------------------------------------------------------
## SIMULATION : PMOS Current Mirror with NMOS Amplifier <br>

### Design a current mirror circuit which has a gain of AV = -10V/V, power supply of Vdd = 1.8V, and power of P <= 1mW. Find reference current (Iref), output current (Id), and total current (Itotal). Perform DC and AC analysis for mirror ratio 1:1, 1:2. Vary length from 180nm -> 500nm -> 1µm and do the analysis.<br>

### FOR 1:1 RATIO 

![main ckt diagram part1](https://github.com/user-attachments/assets/0975d4af-b847-4b85-8189-c35c5cf32b6d)

This circuit consists of a PMOS current mirror (M1 & M2) and an NMOS amplifier stage (M3). The purpose of this circuit is to generate a stable bias current and amplify an input signal.<br>

##### Calculation:<br>
Given , Vdd = 1.8V and P<=1mV <br>
for P= 1mV, <br>
Itot = P/Vdd = 1m / 1.8 = 0.55mA 
###### Iout = 0.55mA
Itot = Iref + Iout <br>
for 1:1 ratio Iref = Iout <br>
Therefore ,<br>
###### Iref = Iout = Itot/2 = 0.277mA <br>
for Vin,<br>
as Vin = Vgs3 , Vin>=Vth<br>
###### Vin>= 0.48V<br>
also,<br>
###### Vout = Vdd/2 = 0.90V <br>
###### Vout = Vx = 0.90V<br>

### DC ANALYSIS :<br>

#### For L = 180n <br>
![180n 1isto1 ](https://github.com/user-attachments/assets/2ae367a1-67bd-4a50-9f41-e3619660f385)

#### For L = 500n <br>
![500n 1isto 1 ratio](https://github.com/user-attachments/assets/99844176-eb9c-4a57-91bf-40834ee129d3)

#### For L = 1u <br>
![1u 1isto 1 ratio](https://github.com/user-attachments/assets/9b81d8a3-2b08-46f4-97c9-ffa150476baa)

#### COMPARISION TABLE :<br>

|Iref (A)    |Iout (A)   |(W/L)<sub>1</sub> |(W/L)<sub>2</sub> |(W/L)<sub>3</sub> |  Vx (V) |Vout(V) |
|------------|-----------|------------------|------------------|------------------|---------|--------|
|0.277m      |0.277m     |7.3u/180n         |7.3u/180n         |117.94u/180n      | 0.90    |0.90    |
|0.277m      |0.277m     |22u/500n          |22u/500n          |119.6u/500n       | 0.90    |0.90    |
|0.277m      |0.277m     |44.24u/1u         |44.24u/1u         |234.254u/1u       | 0.90    |0.90    |

















