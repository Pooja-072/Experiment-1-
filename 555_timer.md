## 1.Monostable Multivibrator<br>
A monostable multivibrator is a type of electronic circuit that has one stable state and one temporary (unstable) state. When triggered by an external pulse, it temporarily switches to the unstable state for a specific period of time and then automatically returns to its stable state.<br>
* Also called a one-shot multivibrator.<br>
* Used to generate precise time delays or single output pulses.<br>
* Commonly implemented using logic gates, transistors, or timers like the 555 timer.<br>
In a 555 timer monostable mode, pressing a button (trigger) produces a high output pulse for a set time (determined by resistor and capacitor values), then the output goes low again.<br>

### Working Principle of Monostable Multivibrator:
A monostable multivibrator works by staying in a stable state under normal conditions. When an external trigger pulse is applied, the circuit temporarily shifts to an unstable state (for a pre-defined time) and then returns automatically to the stable state.<br>
<br>
#### Steps in the Working: <br>
1,Initial State (Stable): <br>
* Output is in a default logic level (usually LOW or 0V).<br>
* No changes occur until a trigger is received.<br>
2.Triggering:<br>
* An external negative (or positive) trigger pulse is applied.<br>
* The circuit detects this pulse and immediately switches to the unstable state.<br>
* Output becomes HIGH for a specific time.<br>
3.Timing Interval (Unstable State):<br>
* A timing capacitor starts charging or discharging through a resistor.<br>
* The time period {𝑇},<br>
T is determined by the RC time constant.<br>
#### 𝑇 = 1.1×𝑅×𝐶 (for 555 timer-based monostable)<br>
4.Return to Stable State:<br>
* After the time period, the capacitor reaches a certain voltage.
* The circuit automatically resets itself and returns to its original stable state (LOW).

### Key Components Involved:
* Trigger Input: Starts the timing process.
* RC Network (Resistor + Capacitor): Sets the pulse width (duration).
*Comparator/Transistor/Timer IC: Detects voltage across the capacitor and controls switching.











