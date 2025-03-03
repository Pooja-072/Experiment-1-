# THE MOS DIFFERENTIAL PAIR AMPLIFIER <br>
<br>
* A differential pair amplifier is a circuit that amplifies the difference between two input signal while rejecting the common mode noise .<br>
* It is widely used in analog ciruits, operational amplifiers, and communication system .<br>
<br>

## WORKING PRINCIPLE OF DIFFERENTIAL PAIR AMPLIFIER :<br>

### Basic Structure:<br>
<br>

![mospair](https://github.com/user-attachments/assets/518b2b0d-fc94-4921-8b5f-caafb7b475b9)<br>

Now assuming both the transistors are identical (m1,m2)<br>
drain resistors, Rd1 = Rd2 = Rd <br>
also,<br>
##### Vin1= Vin2= Vincm <br>
##### Vincm= Vgs + Vp <br>
The transistor to work in saturation region,<br>
    Vds >= Vov <br>
    Vds >= Vgs-Vtn <br>
##### Vd-Vs >= Vg-Vs-Vtn <br>
where,
##### Vd >= Vg-Vtn<br>
from the picture you may observe ,<br>
Vg=Vincm and Vd=Vocm <br>
Therefore,
#### Vocm >= Vincm - Vtn
from this we can conclude that Vincm = Vocm -Vtn
Now,
The total current flowing through the circuit is Iss , current flowing through the transistors are Id1 and Id2 <br>

Also, from observation <br>
Id2=Id2 = Iss/2 (both Id1 and Id2 together constitute for the total current )<br>
Vincm = Vgs + Vp<br>

#### Vp = Vincm - Vgs<br>
now, for saturation region the current equation is <br>
Id1=Id2= (1/2)UnCox(w/L)Vov)^2 <br>
where Vov = [ (I)/(Kn'W/L) ]^1/2 <br>
therefore,<br>
#### Vgs= [(2)^1/2 * Vov ] + Vtn <br>
Now Coming to the output equations ,<br>
#### Vo1=Vo2 = Vdd - Id*Rd = Vd1 = Vd2<br>
when,<br>
Vd1- Vd2 = 0 it implies Vin1=Vin2 , which is ultimately known as common mode.<br>
Now lets find in what range the amplifier works as linear amplifier <br>
for that,<br>
#### Vincm(min) = Vth +Vov3 <br>
where Vov3=Vp<br>
#### Vincm(max) = Vdd- (Id*Rd) + Vth <br>
also output max and min are<br>
#### Vout(min)= Vov1+Vov3 <br>
where Vov3 = Vp <br>
#### Vout(max)= Vdd-(Id*Rd)<br>
to get the maximum input and output swing get the average of maximum and minumum inputs and outputs .<br>
where , 
##### Vp = Voltage at the source node of input transistors (set by tail current)<br>
##### Vth =Threshold voltage of MOSFETs<br>
##### Vdd=Supply voltage<br>
and also ,<br>
Gain of the ciruit , Av = gm*Rd <br>

## ROLE OF THE COMPONENTS : <br>
##### Rss (Source Resistance):<br>
* Stabilizes biasing .<br>
* Provides negative feedback <br>
* As Rss introduces negative feedback , it affects the transconductance (gm), and overall gain (Av) of amplifier .<br>

##### Rd (Drain Resistance):<br>
* Converts current variation into an output voltage.<br>
* Higher Rd the gain increases but limits the output swing <br>

##### Id (Drain Current of each Transistor):<br>
* Defines the transistor's operating region and determines transconductance (gm).<br>
* Higher Id increases the gm , which increases the gain . <br>
* Id must be chosen carefully to keep transistors in saturation for proper amplification.<br>

##### Iss (Tail current ):<br>
* Provides a stable constant current to the differential pair.<br>
* Increasing Iss can increase the gm which increases gain.<br>
* Too much Iss can reduce the available voltage swing also.<br>
<br>

## FOUR TYPES OF DIFFERENTIAL PAIR AMPLIFIER: <br>
#### Resistor-Loaded Differential Pair: <br>
*Uses resistors as the drain load.<br>
*Simple design but has low gain due to large  requirements.<br>
*Limited common-mode rejection and output swing.<br>

#### Current Source-Loaded Differential Pair:<br>
* Replaces Rss with Ideal current source.<br>
* Improves gain.<br>

#### Simple Current Source Differential Pair:<br>
* Uses a single MOSFET as a current source.<br>
* Gain increases still.<br>

#### Active Load Differential Pair (MOSFET as Load):<br>
* Both Iss and Rd are replaced with a mosfet .<br>
* Gain is too high.<br>
-----------------------------------------------------------------------------------------------

## DESIGN QUESTION :<br>

### Design differential amplifie for following specifications Vdd=2.5V, P≤3mW, Vicm = 1.3V, Vocm = 1.4V, Vp = 0.5V. Perform DC analysis, transient analysis & frequency response and extract the required parameters.

![design exp2](https://github.com/user-attachments/assets/24082c73-ece2-44a0-8eff-612c9c939a55)
<br>
##### Now lets perform all the 4 types of ciruit's analysis step by step ;<br>

## CIRCUIT 1 : Resistor-Loaded Differential Pair:<br>

![main ckt dia](https://github.com/user-attachments/assets/f0b9e016-f72c-4d49-8da6-2fba5da1458a)
<br>
### DC Analysis :
* Make the necessary connections as per the circuit daigram .<br>
* Set the Rd and Rss values such that the transistors will operate in saturation region .<br>
* Vary W/L to get the required Voutcm.<br>
* Vary Rd to set exact Voutcm.<br>
* Go to "Simulate" > "Edit Simulation Cmd" > "DC op pnt".<br>

![ckt1 dc](https://github.com/user-attachments/assets/5e41a430-1671-4fd4-9c8f-fd0f14bce4d6)
<br>
* After this in "view " command goto " SPICE errorlog " option to check Vgs, Vth ,Vds etc.<br>

![main error log](https://github.com/user-attachments/assets/2ed58d43-a436-4634-b202-0945d58ab601)
<br>




