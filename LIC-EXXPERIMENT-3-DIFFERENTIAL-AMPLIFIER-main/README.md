# LIC-EXXPERIMENT-3-DIFFERENTIAL-AMPLIFIER  
## DIFFERENTIAL AMPLIFIER  
A differential amplifier is a type of electronic amplifier that amplifies the difference between two input voltages while rejecting any signals that are common to both inputs. It is a fundamental building block in analog circuits and is widely used in operational amplifiers (op-amps), instrumentation amplifiers, and other signal-processing applications.
# KEY FEATURES  
1.  The output can be either a single voltage (referenced to ground) or a differential voltage (difference between two outputs).
2.  The amplifier rejects signals that are common to both inputs (common-mode signals), such as noise or interference.
3.  It provides high voltage gain for the difference between the two input signals.
# APPLICATIONS  
1. Operational Amplifiers (Op-Amps): The input stage of an op-amp is typically a differential amplifier.
2. Instrumentation Amplifiers: Used in precision measurement systems to amplify small differential signals.
3. Noise Cancellation: Rejects common-mode noise in communication systems.
4. Analog Comparators: Compares two input voltages and produces an output based on their difference.

# ADVANTAGES  
1. High common-mode rejection ratio (CMRR).
2. Improved noise immunity.  
3. Suitable for amplifying small differential signals in the presence of large common-mode noise.

# LIMITATIONS  
1. Requires matched components (e.g., resistors, transistors) for optimal performance.
2. Limited by the common-mode input voltage range.

A basic differential amplifier can be implemented using transistors (BJT or MOSFET) or op-amps. 
# QUESTION  
Design and analyze the differential amplifier for the following specs:  
vdd=3.3v p<=3mW  vicm=1.65V vocm=1.7V vp=0.5V .Perfrom DC analysis,transient analysis,AC analysis in LT spice  
# PROCEDURE  
1.Open the LTspice software, merge the library file for getting accurate values of NMOS.  
2.Select the components which are needed  from the components list.  
3.Place them all components , connect all the components as in given circuit .  
4.Lets do the DC Analysis first by selecting configure analysis in that selet .op and do the simulation.  
5.After that lets take Transient analysis of 3m.  
6.For AC analysis, we should do some changes like converting DC SOURCE to sinosoidal waveform (1.2,50m,1T),after that select the AC simulation from the given options of simulation after giving values of (Decade,20,01,1T). So we will get a output after placing node to output waveform .  
# CIRCUIT 1 with resistor  
![Image](https://github.com/user-attachments/assets/ff007a24-989b-4774-87ca-3b7feff1b002) 

#CALCULATION  
![Image](https://github.com/user-attachments/assets/c0acb823-4f24-4958-b92e-48109d3d6e6d)  
1.1 DC ANALYSIS  
![Image](https://github.com/user-attachments/assets/f173714c-256f-4be5-9017-14eaa2ebecc8)  

1.2 TRANSIENT ANALYSIS  
![Image](https://github.com/user-attachments/assets/a919dad9-6dae-4633-a26f-e51a1a1bd020)  

Gain(AV)=Vout/Vin=1.77 - 1.63 / 1.69 - 1.60 = 1.5

1.3 AC ANALYSIS  
![Image](https://github.com/user-attachments/assets/b4f198a4-7beb-448f-9621-948385b08630)  

Gain = 20log(AV) = 20log(1.5) = 3.5dB

# CIRCUIT 2 WITH CURRENT SOURCE  

REPLACE THE RESISTOR WITH CURRENT SOURCE  

![Image](https://github.com/user-attachments/assets/a6ea24d5-38c0-4409-95b3-c34f43474616)  

2.1 DC ANALYSIS  
![Image](https://github.com/user-attachments/assets/b40cda86-704c-4d71-8d52-5b547d2f1d5f)  
2.2 TRANSIENT ANALYSIS  
![Image](https://github.com/user-attachments/assets/7e9ed2df-1775-4f61-8e55-dd6fd7580397)  

GAIN(AV) = Vout/Vin = 1.83 - 1.57 / 1.69 - 1.60 = 2.88  

2.3 AC ANALYSIS  

![Image](https://github.com/user-attachments/assets/6560bcb1-602b-46df-ac4d-6c227576fc5f)  

Gain in dB = 20log(2.88) = 9.18  

# CIRCUIT 3 WITH NMOS  
NOW REPLACE CURRENT SOURCE WITH NMOS  
![Image](https://github.com/user-attachments/assets/d108d1d2-adf3-4a0a-a42d-99be97b1a0ba)  
3.1 DC ANALYSIS  
![Image](https://github.com/user-attachments/assets/f5d48a32-77ad-420e-8eeb-3e0e2945e367)  
3.2 TRANSIENT ANALYSIS  
![Image](https://github.com/user-attachments/assets/abddc493-9399-4d84-9410-7f60855066bc)  

GAIN(AV) = Vout/Vin = 1.65 - 1.6 / 1.61 - 1.56 = 1

3.3 AC ANALYSIS  
![Image](https://github.com/user-attachments/assets/49f6f9c2-795b-432c-bb84-01e5d10836ff)  

Gain in dB = 2log(Av) = 0dB  

#  CIRCUIT 4  
NOW REPLACE TWO RD RESISTORS WITH PMOS  
![Image](https://github.com/user-attachments/assets/f83457e9-74f6-4022-8b6b-14050cf8a782)

4.1 DC ANALYSIS  
![Image](https://github.com/user-attachments/assets/babee48e-b3c4-40ef-a2af-bfc5fd6de059)  

4.2 TRANSIENT ANALYSIS   
![Image](https://github.com/user-attachments/assets/67cbd8f8-ebab-4da8-8743-c38368269b90)  

GAIN(AV) = Vout/Vin = 0.1  

4.3 AC ANALYSIS  

![Image](https://github.com/user-attachments/assets/216ba2ba-78c1-4e80-b5b3-08b81b431670)

GAIN in dB is -20  

# COMPARISON TABLE  

![Image](https://github.com/user-attachments/assets/d93e9772-6285-41c5-8802-d9e409ca7495)

# RESULTS AND INFERENCE  
1. Ensures MOSFETs are in the saturation region. Defines the Q-point (operating region) of the amplifier.  
2. Determines differential gain and input and output swing.
3. if we incrrease vicm id of mosfet 1 will decrease.

Iss=0,45mA  
Id1=Id2=Iss/2=0.225mA  
Rd=7.11kohm  
Rss=1.11kohm  










