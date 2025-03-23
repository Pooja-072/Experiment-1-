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











