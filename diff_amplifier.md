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
-----------------------------------------------------------------------------------------------


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
from this , the transistor to operate in saturation region ,<br>
Vgs>Vth, <br>
Vds> Vov <br>
From observation our Vgs= 0.801V , Vth= 0.495V and Vds = 0.904V . <br>
as,
##### 0.801 > 0.495 our Vgs > Vth <br>
as,
##### 0.904 > (0.801-0.495) i.e Vds > Vov <br>
The transistors lie in saturation region .<br>
##### Theoretical values and observed values of parameters :<br>

| Parameter    | Theoretical value  | Practical value |
|--------------|--------------------|-----------------|
|Voutcm        | 1.40V              | 1.403V          |
|Vp            | 0.5V               | 0.49V           |
|Id1,Id2       | 0.6mA              | 0.59mA          |
|Id(R3)        | 1.2mA              | 1.19mA          |
|Rd            | 1.8kohm            | 1.83kohm        |
|Rss           | 416.2ohm           | 416ohm          |
|Vgs           | 0.8V               | 0.801V          |

<br>
therefore Q point = (Vds,Id) = (0.904V,0.6mA).<br>
Now lets caluculate vincm(min), Vincm(max), Vout(min), Vout(max) .<br>

##### Vincm(min)= Vth + Vp = 0.36 + 0.5 = 0.86V <br>
##### Vincm(max) = Vdd - (Id*Rd) + Vth = 1.762V <br>
##### Vout(min) = Vov1 + Vov3 = (0.8-0.36)+0.5 = 0.94V <br>
##### Vout(max) = Vdd-(Id*Rd) = 1.402V <br>
<br>

## Transient Analysis :
* Replace DC input with an AC signal.<br>
* Use SINE(dc_offset, Amplitude, Frequency).
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".<br>
* Set Stop Time: 5ms.<br>
* Run the simulation.<br>
##### I will apply 2 different amplitudes and vary Vcm to see the input and output swing and to check whether circuit act as a linear amplifier within the range .<br>
### For Amplitude = 50mV :
#### * When Vincm = 0.5V:

![0 5 vout](https://github.com/user-attachments/assets/f4415b87-6a06-4239-a734-30c681e5167d)

check the SPICE ERROR log,<br>
Vgs = 0.480V , Vth = 0.485V . <br>
as 
###### Vgs<=Vth 
The transitor is in off state , therefore you are observing distortion or the clipping off of the output circuit . <br>

#### * When Vincm = 0.55V :

![0 55Vout 50m](https://github.com/user-attachments/assets/5f4e4803-220d-48a6-93dd-3d50e3541e43)

check the SPICE ERROR log,<br>
Vgs = 0.513 V , Vth = 0.485V and Vds = 2.38V. <br>
as Vgs>Vth and Vds> Vov , the transitor is in saturation region <br>
Vincmp-p = 600mV + 500mV = 1.1V<br>
Voutp-p = 2.3+2.4 = 4.8V Which is too high . This happens because Id and Iss and fully varying <br>

#### * When Vincm = 1.31V :

![1 31 vout](https://github.com/user-attachments/assets/1fa65df0-bfff-4cb9-a735-b5fdbbf2f181)

Vinp-p = 1.36V+ 1.26V = 2.62V<br>
Voutp-p = 1.16V + 1.60V = 2.76V <br>
From theoretical value wkt Vout(max)p-p = 2.80V <br>
So in this input volatge we are getting the maximum output swing.<br>

#### * When Vout >=1.7V<br>

![1 76vout](https://github.com/user-attachments/assets/521bbc5b-0f00-43cc-800d-14553b9b610a)

The transistor enters the triode region as Vds<Vov <br>
therefore the waveform is distorted .<br> 

### For Amplitude = 100mV :
#### * When Vincm < 0.5V <br>
in this case if Vincm < 0.5V the transitor enters cutoff region as there will no sufficient Vgs .<br>
#### * When Vincm = 1.31V <br>

![1 31Vout 100mv](https://github.com/user-attachments/assets/390387c4-6f4d-4388-9671-bc3ddb72ea44)

In this case Vincmp-p = 2.62V and Voutp-p = 0.95V + 1.82V <br>
From theoretical value wkt Vout(max)p-p = 2.80V <br>
So in this input volatge we are getting the maximum output swing.<br>

#### * When Vincm < 1.55V <br>

![1 76vout 100mv](https://github.com/user-attachments/assets/28137843-0ab2-4915-96db-8beab1901e6b)

The transistor enters the triode region as Vds<Vov <br>
therefore the waveform is distorted .<br> 
#### FOR 50mV AMPLITUDE :
|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Vincm(min)     | 0.86V        | 0.55V           |
|Vincm(max)     | 1.76V        | 1.66V           |

#### FOR 100mV AMPLITUDE :
|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Vincm(min)     | 0.86V        | 0.5V            |
|Vincm(max)     | 1.76V        | 1.55V           |

##### So I conclude that, Larger Amplitude Causes Early Distortion i.e at higher ampltitude transistor reaches saturation or cutoff earlier , limiting the range of valid Vincm.<br>

## AC Analysis : <br>

For this we priorly need to calculate gain with theoretical values . <br>
gain = Av= -gm*Rd 
where gm= (2Id)/Vov = 2.72mS <br>
Av= -2.72m * 1.83k = -4.97 V/V <br>
as we know Av= 20Log(vout/Vin)<br>
in dB scale theoretical gain is 13.92dB <br>

![ac ckt 1](https://github.com/user-attachments/assets/ef893833-9bdc-45a6-9ab3-146f714227b4)

from this , practically we are getting 13.01dB gain <br>
which is equal to , Av= 10^(13.01/20) = 4.47V <br>
Bandwidth = 2.5GHz <br>
3db Bandwidth = 13GHz <br>
|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 13.92dB      | 13.01dB         |
|Av(in V/V)     | 4.97         | 4.47            |













