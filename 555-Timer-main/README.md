# 555-Timer
## MONOSTABLE MULTIVIBRATOR USING 555 TIMER IC
# 1.AIM
Generate a waveform with pulse width of 0.5 ms under different trigger conditions using 555 timer IC.
# 2.Theory  
A monostable multivibrator, also known as a one-shot pulse generator, is a circuit that generates a single output pulse in response to an external trigger input. When built using a 555 timer IC, the circuit operates in monostable mode, where the timer produces a high output pulse of predetermined width (also called time period) upon receiving a trigger signal. The duration of this output pulse is determined by an external resistor (R) and capacitor (C) connected to the timer. When the trigger input (applied to pin 2) goes momentarily low, it initiates a timing cycle, causing the output (pin 3) to go high. This high state persists for a time period 𝑇=1.1RC after which the output returns to its stable low state. The 555 timer’s internal flip-flop and discharge transistor control the charging and discharging of the capacitor, defining the duration of the pulse. The circuit is commonly used for pulse generation, timing applications, and creating precise time delays.  
# 3.Features  
1.Single stable state: It has one stable (low) state and one quasi-stable (high) state that persists for a specific duration upon triggering.  
2.Trigger input sensitivity: The circuit is triggered by a negative pulse (a momentary low signal) applied to the trigger pin (pin 2).  
3.Automatic reset: After the set time duration, the output automatically returns to the stable low state without the need for an additional reset signal.  
4.Edge-triggered operation: The monostable mode responds to the falling edge (negative-going transition) of the trigger pulse.  
5.High output drive capability: The 555 timer can source or sink up to 200 mA of current, sufficient to drive LEDs, relays, or other loads. 

# 4.Circuit Diagram  
![Image](https://github.com/user-attachments/assets/0750370d-0d58-4146-8e35-5b9c5a835ab7)  

# 5.Calculation  
We need T=0.5ms  
WKT:T = 1.1 x R x C  
Lets assume C=1u  
We will get R as 454.54ohms  

# 6.Transient Analysis  

![Image](https://github.com/user-attachments/assets/58a5f433-07d0-4a9d-b0c1-c1154687c58c)  
This is generating trigger pulse at every 2ms...lets change is to 1ms and see what happens  
![Image](https://github.com/user-attachments/assets/7eb4bfd2-c616-4075-b89d-a02ef5a50ff7)  
This is generating trigger pulse at every 1ms...now lets change it to 0.1ms and see what happens  
![Image](https://github.com/user-attachments/assets/7a6794e1-4ace-4a04-9914-cd32a041048b)  

I have run the simulation for tran10m and as you can see the trigerring is happening very fast but the output voltage goes high on every 0.5ms only  

V(n001) is voltage across capacitor  
V(n002) is the output voltage  


# 7.Inference  
In  monostable multivibrator using the 555 timer IC, it is observed that the circuit generates a single output pulse in response to each trigger pulse applied to the input. The duration of the output pulse remains constant for a given resistor (R) and capacitor (C) combination, irrespective of the width or duration of the trigger pulse. This confirms the edge-triggered nature of the circuit, where the output is initiated by the falling edge of the trigger pulse. The simulation demonstrates that for multiple trigger pulses spaced sufficiently apart, the circuit generates corresponding distinct output pulses, while closely spaced trigger pulses during the quasi-stable state are ignored due to the one-shot behavior. This behavior highlights the circuit's reliability and suitability for pulse generation and timing applications.  

# 8.Conclusion  
 In monostable multivibrator using a 555 timer IC, it is concluded that the circuit effectively generates a single output pulse of fixed duration upon receiving a trigger input. The output pulse width is determined by the external resistor and capacitor, following the formula 
T=1.1RC, and is independent of the trigger pulse width. The circuit responds only to the falling edge of the trigger signal and ignores subsequent triggers during the timing period, confirming its monostable or one-shot operation. This behavior makes the circuit ideal for applications requiring precise timing intervals, pulse generation, and switch debouncing.  


## ASTABLE MULTIVIBRATOR USING 555 TIMER IC  

# 1.AIM  
Generate a waveform with pulse width of 0.5 ms under different trigger conditions using 555 timer IC.  

# 2.Theory  
An astable multivibrator is a free-running oscillator circuit that continuously generates a square wave without requiring any external trigger. When configured using a 555 timer IC, the astable mode is achieved by connecting external resistors RA and RB with a capacitor C which determine the timing characteristics. In this mode, the circuit has no stable state; it alternates between high and low output states, producing a continuous train of rectangular pulses at the output (pin 3). The timing capacitor C charges through both resistors RA and RB and discharges through RB only,creating an asymmetry in the charge and discharge times. The output waveform has a period (T) and a duty cycle determined by the values of RA,RB and C.  
The astable multivibrator is commonly used in applications such as clock pulse generation, flashing LEDs, tone generation, and square wave generation.  
# 3.Features  
1.Free-running oscillator: Continuously generates a square wave without requiring an external trigger signal.  
2.No stable state: The circuit has two quasi-stable states (high and low), and the output toggles between them indefinitely.  
3.Output square wave: Produces a rectangular waveform with adjustable mark-space ratio (duty cycle).  
4.Simple and reliable: Uses minimal external components and is easy to implement in both hardware and simulation.  
5.Edge-independent operation: Unlike the monostable mode, the astable multivibrator doesn’t require any external input signal to trigger operation.  

# 4.Circuit Diagram  
![Image](https://github.com/user-attachments/assets/6814230c-3e13-49ff-8198-1608edf0b5cb)  

  
# 5.Calculations  
Lets choose ton=0.3ms and toff=0.2ms  
ton = 0.69 (R1 + R2)C2, toff = 0.69 x R1 x C2
by substituting in above formula we get  
R2=28.9kohm,R1=14.5kohm  
# 6.Transient Analysis  
![Image](https://github.com/user-attachments/assets/d1a08cfb-f3e1-4912-af23-345acb13c935)  
v(vou): This is the output of an inverted astable multivibrator.  
V(n006): This comes from a differentiator circuit, where the capacitor used is 0.1 μF.  
V(n007): This is the output of a positive clipper circuit.  
V(vout): This is the output of a monostable multivibrator, and the pulse width is set to 0.5 ms.  

# 7.Inference  
In astable multivibrator using a 555 timer IC, the circuit produced a continuous square wave output without any external trigger. The simulation confirmed that the pulse width (period) of the output waveform was determined by the resistor and capacitor values chosen. By selecting appropriate resistor values R1 and R2  and capacitor C the total period of 0.5 ms was achieved, with the output alternating between high and low states. It was observed that the time the output stayed high (ton) and low (toff) could be independently controlled, validating the theoretical calculations. This simulation verified the 555 timer’s operation in astable mode and demonstrated its use as a square wave generator.  

# 8.Conclusion    
The simulation of the astable multivibrator circuit using a 555 timer IC demonstrated that the circuit operates as a free-running oscillator, continuously generating a square wave without requiring an external trigger. The output waveform’s period and duty cycle were determined by the values of resistors 
R1,R2 and Capaciror C as predicted by theoretical formulas. The achieved output period of 0.5 ms validated the accuracy of the component selection and design calculations. The simulation further confirmed the reliability of the 555 timer IC for generating stable clock pulses and square waves, highlighting its suitability for use in timing, pulse generation, and oscillator applications.  




















