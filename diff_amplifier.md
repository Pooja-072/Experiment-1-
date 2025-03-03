# THE MOS DIFFERENTIAL PAIR AMPLIFIER <br>
<br>
* A differntial pair amplifier is a circuit that amplifies the difference between two input signal while rejecting the common mode noise .<br>
* It is widely used in analog ciruits, operational amplifiers, and communivation system .<br>
<br>

## WORKING PRINCIPLE OF DIFFERENTIAL PAIR AMPLIFIER :<br>

### Basic Structure:<br>
<br>

![mospair](https://github.com/user-attachments/assets/518b2b0d-fc94-4921-8b5f-caafb7b475b9)<br>

Now assuming both the transistors are identical (m1,m2)<br>
drain resistors, Rd1 = Rd2 = Rd <br>
also Vin1= Vin2= Vincm <br>
    Vincm= Vgs + Vp <br>
The transistor to work in saturation region,<br>
    Vds >= Vov <br>
    Vds >= Vgs-Vtn <br>
    Vd-Vs >= Vg-Vs-Vtn <br>
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


