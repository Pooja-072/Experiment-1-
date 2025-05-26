# 1. MONOSTABLE MULTIVIBRATOR<br>
A monostable multivibrator is a type of electronic circuit that has one stable state and one temporary (unstable) state. When triggered by an external pulse, it temporarily switches to the unstable state for a specific period of time and then automatically returns to its stable state.<br>
* Also called a one-shot multivibrator.<br>
* Used to generate precise time delays or single output pulses.<br>
* Commonly implemented using logic gates, transistors, or timers like the 555 timer.<br>
In a 555 timer monostable mode, pressing a button (trigger) produces a high output pulse for a set time (determined by resistor and capacitor values), then the output goes low again.<br>

### Working Principle of Monostable Multivibrator:
A monostable multivibrator works by staying in a stable state under normal conditions. When an external trigger pulse is applied, the circuit temporarily shifts to an unstable state (for a pre-defined time) and then returns automatically to the stable state.<br>
<br>
#### Steps in the Working: <br>

1.Initial State (Stable): <br>

   * Output is in a default logic level (usually LOW or 0V).<br>
   * No changes occur until a trigger is received.<br>
<br>
2.Triggering:<br>

   * An external negative (or positive) trigger pulse is applied.<br>
   * The circuit detects this pulse and immediately switches to the unstable state.<br>
   * Output becomes HIGH for a specific time.<br>
<br>
3.Timing Interval (Unstable State):<br>

   * A timing capacitor starts charging or discharging through a resistor.<br>
   * The time period {𝑇},<br>
   T is determined by the RC time constant.<br>
#### 𝑇 = 1.1×𝑅×𝐶 (for 555 timer-based monostable)<br>

4.Return to Stable State:<br>

* After the time period, the capacitor reaches a certain voltage.<br>
* The circuit automatically resets itself and returns to its original stable state (LOW).<br>

### Key Components Involved:<br>
* Trigger Input: Starts the timing process.<br>
* RC Network (Resistor + Capacitor): Sets the pulse width (duration).<br>
*Comparator/Transistor/Timer IC: Detects voltage across the capacitor and controls switching.<br>

-------------------------------------------------------------------------------------------------
### DESIGN QUESTION:<br>

#### To use the 555 timer IC to design and build a monostable multivibrator such that, when activated, produces an output pulse with a width of 0.5 milliseconds.<br>

Calculation:<br>
Given:<br>
Pulse width T = 0.5 ms = 0.0005 s<br>
Capacitance C = 1 µF = 1×10⁻⁶ F<br>
Using the formula:<br>
T = (1.1 * R * C)<br>
R = (T/(1.1 * C)) = (0.0005/(1.1* 1 *10^(-6))) = 454.54 Ω<br>

### 555 Timer Monostable Configuration – Shortform:<br>
Pin 1 → GND<br>
Pin 2 → Trigger (LOW to activate)<br>
Pin 3 → Output<br>
Pin 4 → Reset → tied to Vcc<br>
Pin 5 → Control → 0.01 µF to GND<br>
Pin 6 → Threshold<br>
Pin 7 → Discharge<br>
Pin 8 → Vcc (+5V)<br>
Connect resistor (R) between Vcc and pin 7<br>
Connect capacitor (C) between pin 6 and GND<br>
Join pins 6 & 7 together<br>
Apply trigger pulse to pin 2 (e.g., push-button)<br>
Observe output at pin 3 (LED or oscilloscope)<br>
<br>

![image](https://github.com/user-attachments/assets/91dd2b68-710c-4f28-940e-d8328fd206e2)

### Simulation Result:<br>

![image](https://github.com/user-attachments/assets/52b83cba-ef5e-45b0-bc13-a8cdd3982ab5)

In the above circuit, when the trigger voltage drops below 1/3 of Vcc, the output switches to HIGH.<br>

### Result <br>
The 555 timer in monostable mode successfully generates a single output pulse when the trigger voltage drops below 1/3 Vcc.<br>

### Inference<br>

* When the trigger voltage < 1/3 Vcc, the 555 timer recognizes it as a valid trigger.
* This causes the output (pin 3) to go HIGH for a specific time period.
* The capacitor charges during this time, determining the pulse width.
* After the time elapses, the output returns to LOW, completing the monostable operation.

------------------------------------------------------------------------------------------------

# ASTABLE MULTIVIBRATOR <BR>
An astable multivibrator is an electronic circuit that continuously switches between two unstable states without any external trigger, generating a free-running square wave (oscillating output).<br>
* No stable state (unlike monostable).<br>
* Continuously produces ON-OFF (HIGH-LOW) pulses.<br>
* Acts as a clock, flasher, or tone generator.<br>
* Commonly built using 555 timer IC, transistors, or logic gates.<br>
In a 555 timer astable mode, the output at pin 3 continuously toggles between HIGH and LOW, creating a square wave whose frequency and duty cycle are set by two resistors (R1, R2) and a capacitor (C).<br>

### Working Principle of Astable Multivibrator (Using 555 Timer):<br>
An astable multivibrator has no stable state. It keeps toggling between HIGH and LOW automatically, creating a continuous square wave without any external trigger.<br>
<br>
#### Step-by-Step Working:<br>
1.Initial Condition:<br>

* When powered on, the capacitor (C) starts charging through R1 and R2.<br>
* As it charges, the voltage across the capacitor increases.<br>

2.Threshold Detection (2/3 Vcc):<br>

* When capacitor voltage reaches 2/3 Vcc, the internal comparator in the 555 timer resets the flip-flop, and the output goes LOW.<br>
* At this point, the discharge pin (7) is connected to GND.<br>

3.Discharging Phase:<br>
  
* The capacitor now discharges through R2 and pin 7.<br>
* When voltage drops below 1/3 Vcc, the flip-flop is set again and the output goes HIGH.<br>

4.Recharging:<br>

* The capacitor starts charging again through R1 and R2.<br>
* This cycle repeats continuously, generating a square wave output.<br>

### Frequency & Time Period:<br>

![image](https://github.com/user-attachments/assets/4ce1dd7a-c3a5-45eb-ac71-d3075aa912f4)

------------------------------------------------------------------------------------------------

### DESIGN QUESTION<br>

#### Generate pulse of width 0.5ms using 555 timer IC.<br>

![WhatsApp Image 2025-05-26 at 19 54 18_92099e41](https://github.com/user-attachments/assets/48ea3088-8cdf-4ffc-90c5-15536aa90ad1)

##### Calculation:<br>
From the formula wkt T = 1.1*R*C <br>
assuming c=0.1uF , R becomes<br>
R = 4.5kohm<br>

#### CASE 1:<br>
Given<br>
ton = 0.3ms & toff = 0.2ms<br>
formulas<br>
ton = 0.69*(R1+R2)*C<br>
toff = 0.69*R2*C<br>
from calculations , <br>
R2 = 29.98kohm<br>
R1= 14.5kohm<br>
c= 0.01uF<br>

#### CASE 2:<br>
Given<br>
ton = 0.2ms & toff = 0.05ms<br>
assume ,<br>
R1 = 72kohm<br> & R2 = 72kohm<br>
by formula <br>
C = 1nF<br>

#### CASE 3:<br>
Given<br>
ton = 0.1ms & toff = 0.4ms<br>
Check if possible:<br>
* Since in a 555 timer astable, 𝑡on > 𝑡off always.<br>
Here ton < toff, not possible<br>
so swap values<br>
new ton= 0.4ms and toff= 0.1ms
therefore<br>
R2 = 4.3kΩ<br>
R1 = 53.4kΩ<br>
C=0.01μF<br>
from differentiator ,assuming c= 0.1uF<br>
fa= 1kHz, fb= 10kHz<br>
R1=159ohm<br>

### Simulation result:<br>
#### CASE 1 :<BR>

![WhatsApp Image 2025-05-26 at 19 54 17_8fd66052](https://github.com/user-attachments/assets/48608ee5-1eaa-4556-b5f9-1e93f83d4547)

* First waveform: Output of Astable Multivibrator (continuous square wave).<br>
* Second waveform: Output of Differentiator Circuit (sharp spikes at edges).<br>
* Third waveform: Output of Positive Clipper Circuit (positive peaks clipped).<br>
* Fourth waveform: Output of Monostable Multivibrator (single pulse of 0.5 ms width).<br>

#### CASE 2 :<BR>

![WhatsApp Image 2025-05-26 at 19 54 19_a377e608](https://github.com/user-attachments/assets/9653502e-cffb-4f57-96ce-82f3db5a5b94)

* First waveform: Output of Astable Multivibrator – continuous square wave.
* Second waveform: Output of Differentiator Circuit – sharp voltage spikes at transitions (with C = 0.1 µF).
* Third waveform: Output of Positive Clipper – positive portions of input waveform are clipped.
* Fourth waveform: Output of Monostable Multivibrator – single pulse of 0.5 ms width.

#### CASE 3 :<BR>

![WhatsApp Image 2025-05-26 at 19 54 18_c653ad8b](https://github.com/user-attachments/assets/9fea2779-9422-4e27-8693-ecebfc3b7f33)

* First waveform: Output of Inverted Astable Multivibrator – continuous inverted square wave.
* Second waveform: Output of Differentiator Circuit – sharp positive and negative spikes at transitions.


* Third waveform: Output of Positive Clipper Circuit – positive peaks are clipped, negative parts remain.
* Fourth waveform: Output of Monostable Multivibrator – single pulse with 0.5 ms duration.

### Results:<br>

1.Inverted Astable Multivibrator Output: A continuous square wave, but inverted (starts from LOW to HIGH).<br>
2.Differentiator Circuit Output (using C = 0.1 µF): Produces narrow spikes at each transition of the square wave — positive spike at falling edge, negative spike at rising edge of the input.<br>
3.Positive Clipper Output: The waveform after clipping removes or limits positive voltage spikes, allowing only negative parts of the signal to pass.<br>
4.Monostable Multivibrator Output (Pulse width = 0.5 ms):For each triggering input (like a negative spike), it produces a single fixed-width HIGH pulse of 0.5 ms.<br>

### Inference:<br>
* The signal flow demonstrates how complex waveforms can be generated and shaped using basic analog building blocks.
* The differentiator emphasizes high-frequency components (edges), showing its role in transient detection.
* The clipper introduces non-linearity, proving useful in waveform limiting and protection circuits.
* The monostable multivibrator acts as a timing element, converting brief triggers into uniform timed pulses.

