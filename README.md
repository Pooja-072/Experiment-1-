# Experiment-1-
## DC,Transient and AC Analysis of Common Source Amplifier Using LTspice<br>
### AIM :<br>
To Analyse the DC, Transient and AC analysis of a Common Source Amplifier using LTspice.<br>
<br>
### COMPONENTS :<br>
Resistor, n-mosfet, Voltage source(Power Supply), AC ground, Wires.<br>
### CIRCUIT DIAGRAM : <br>
![Image](https://github.com/user-attachments/assets/af8c885c-20f9-44a9-8276-688cd0fecadf)
<br>
### THEORY:<br>
The Common source (CS) Amplifier is one of the most widely used configurations in anaglog electronics, known for its high voltage gain and effectivenesss in signal amplications.<br>
It's functionality is assessed through three major evaluations:<br>
### ~ DC Analysis:
Focuses on establishing the biasing condition for determining the Q point to ensure that the MOSFET is in active region.<br>
### ~ Transient Analysis:
It evaluates time domain response, observing how the amplifier processes input signal over time <br>
### ~ AC Analysis:
It helps to understand how the amplifier handles small signals and different frequencies. It shows how much the signal is amplifoed (gain),the range of frequencies it can work with(bandwidth)), and how the signal shifts in timing (phase).
<br>
### Procedure:<br>
1.Built the above circuit in the LT Spice <br>
2.Set the supply voltage (Vdd) to 1.8V, the gate voltage (VG) to 0.9V, and a 1kohm resistor in the circuit.<br>
3.Download and save the library file and LT splice file to a folder<br>
4.Import the library file to LTspice file using spice directive .op<br>
5.Change the nmos4 mosfet model name as CMOSN as in the library file with length 180nm and width 1um.<br>
6.The given power rating is 100 micro watt. So find the current for this power rating.<br>
7.Firstly conduct the DC Analysis of the circuit. For this vary the width of CMOSN to get the calculated value as the result of the simulation as drain current is directly proportional to width of the transistor.<br>
8.For Transient Analysis set the dc offset as 0.9V, amplitude 50mV, and frequency as 1kHz and keep the stop time for 3ms and run.<br>
9.For AC Analysis set the sweep as decade , number of points per decade as 20, start frequency as 0.1Hz and stop frequency as 1T(Tera)Hz.<br>
<br>
### CALCULATION:<br>
Given the power as 100uW ,we know that Vdd is 1.8V<br>
from the formula P=VI<br>
Id=P/V = 100u/1.8 = 55.5uA<br>
Now,<br>
from the loop equation : Vdd=IdRd + Vout<br>
(where Id=55.5uA,Rd=1kohm,Vdd=1.8V)<br>
Therefore,<br>
Vout=1.745V<br>
Hence the Q point = (Vout,Id) = (1.745V,55.5uA)<br>
<br>
### TABULAR COLUMN:<br>
For the DC Analysis, to get the calculated value of Id , you need to vary the width and check for the corresponding Vout.<br>
| Width  | Current | Vout  |
|--------|---------|-------|
| 1um    | 152.7uA | 1.64V |
| 0.8um  | 127.8uA | 1.67V |
| 0.4um  | 78.37uA | 1.72V |
| 0.2um  | 55.2uA  | 1.74V |
| 0.203um| 55.5uA  | 1.745V|

<br>

### SIMULATION RESULT:<br>
1.DC Analysis :<br>
![Image](https://github.com/user-attachments/assets/790c17a8-1d4a-403c-9d04-5dbb265bfa63)
<br>
<br>
From the simulation ,
We got Id=55.5uA for width=0.203um and Vout=1.745V.<br>
Vds=Vout=1.745V<br>
Vov = Vgs-Vth = Vin-Vth = 0.54V<br>
where Vds>Vov. Mosfet lies in saturation region.<br>
Therefore the dc operting point is(1.745V,55.5uA)<br>
<br>
2.Transient Analysis:<br>
![Image](https://github.com/user-attachments/assets/f49f7252-c005-4211-bf09-b73caa773b0f)<br>
<br>
we got vout = 1.745V for width = 0.203um and a phase shift of 180 degree.<br>
Gain,Av = Vout/Vin = 1.745/0.9 = 1.938<br>
<br>
3.AC Analysis:<br>
![Image](https://github.com/user-attachments/assets/739c5487-95f4-4c60-87ff-0efd50545589)<br>
<br>
We got frequency = 210,45GHz<br>
Gain(db)=-9.104db<br>
<br>
### INFERENCE:<br>
1.There was a 180 degree phase shift between input and output in dc analysis <br>
2.Width is directly proportional to drain current.<br>
3.From AC analysis we get gain and frequency.<br>
## CIRCUIT DIAGRAM 2 :<br>
![Image](https://github.com/user-attachments/assets/58a0291e-6700-47cd-8954-3add6af540a8)<br>
<br>
### COMPONENTS: <br>
PMOSFET(180nm tachnology) , NMOSFET(180nm technology) , voltage supply,AC ground .<br>
<br>
### THEORY:<br>
The Common source (CS) Amplifier is one of the most widely used configurations in anaglog electronics, known for its high voltage gain and effectivenesss in signal amplications.<br>
It's functionality is assessed through three major evaluations:<br>
### ~ DC Analysis:
Focuses on establishing the biasing condition for determining the Q point to ensure that the MOSFET is in active region.<br>
### ~ Transient Analysis:
It evaluates time domain response, observing how the amplifier processes input signal over time <br>
### ~ AC Analysis:
It helps to understand how the amplifier handles small signals and different frequencies. It shows how much the signal is amplifoed (gain),the range of frequencies it can work with(bandwidth)), and how the signal shifts in timing (phase).
<br>
### PROCEDURE :<br>
1. Build the above circuit using LTSPICE.<br>
2. Download and save the library file and LT splice file to a folder<br>
3. Import the library file to LTspice file using spice directive .op<br>
4. Design a diode connected PMOSFET such that it always operates in saturation region.<br>
5. Set the gate voltage of NMOSFET to 0.7V and maintain the supply voltage as 1.8V only.<br>
6. Set the length and width of both the transistor as 180nm and 1um.<br>
7. The given power rating is 100 micro watt. So find the current for this power rating.<br>
8. Firstly conduct the DC Analysis of the circuit. For this vary the width of CMOSN to get the calculated value as the result of the simulation as drain current is directly proportional to width of the transistor.<br>
9. For Transient Analysis set the dc offset as 0.9V, amplitude 50mV, and frequency as 1kHz and keep the stop time for 3ms and run.<br>
10. For AC Analysis set the sweep as decade , number of points per decade as 20, start frequency as 0.1Hz and stop frequency as 1T(Tera)Hz.<br>
<br>
### TABULAR COLUMN:<br>
For the DC Analysis, to get the calculated value of Id , you need to vary the width and check for the corresponding Vout.<br>
| Width  | Current | Vout  |
|--------|---------|-------|
| 1um    | 27uA    | 1.1V  |
| 1.2um  | 32.6uA  | 1.1V  |
| 1.4um  | 38.1uA  | 1.1 V |
| 1.6um  | 43.5uA  | 1.1V  | 
| 2um    | 54.5uA  | 1.1V  |
|2.02um  | 55.5um  | 1.1V  |
<br>
### SIMULATION RESULT :<br>
1. DC Analysis:<br>
Given the power as 100uW ,we know that Vdd is 1.8V<br>
from the formula P=VI<br>
Id=P/V = 100u/1.8 = 55.5uA<br>
![Image](https://github.com/user-attachments/assets/d94001ce-d099-4093-b6d3-6e34777315c1)<br>
We got Id=55.5uA for width=2.02um and Vout=1.1V.<br>
Vds=Vout=1.1V<br>
Vov = Vgs-Vth = Vin-Vth = 0.7-0.36= 0.36V<br>
where Vds>Vov. Mosfet lies in saturation region.<br>
Therefore the dc operting point is(1.1V,55.5uA)<br>
<br>
2.Transient Analysis:<br>
![Image](https://github.com/user-attachments/assets/c257f3bd-a802-42b8-9038-6c1a748738a8)
