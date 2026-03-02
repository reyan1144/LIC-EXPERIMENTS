# LIC-EXPERIMENT-1
## AIM
Using LTspice to examine a CS amplifier characterization like frequency response,bandwidth,phase difference,gain.Utilizing DC,transient,AC analysis using 180nm technology lib.
## COMPONENTS REQUIRED
NMOS and PMOS(180nm technology node),Resistor,voltage source,AC ground,Wires
## THEORY AND SIMULATION
A)DC ANALYSIS:When we talk about DC analysis for a MOSFET, the main goal is to figure out the stable operating point of the transistor. This is important because we want the MOSFET to work in its saturation region, which is where it can properly amplify signals.  
For the MOSFET to be in saturation, the voltage between the drain and source (VDS) needs to be greater than something called the overdrive voltage (VOV). The overdrive voltage is just the difference between the gate-source voltage (VGS) and the threshold voltage (VTH) of the MOSFET.  VOV = VGS - VTH.  
For simulating open LTspice click on configure analysis and in that select DC op pnt and then click ok.  
B)AC ANALYSIS:When we analyze a MOSFET for AC signals (small alternating signals), we treat it as a linear small-signal amplifier. This means we’re looking at how tiny changes in the input voltage (at the gate) affect the output current (at the drain). In this case, the drain current (iD) is directly proportional to the small changes in the gate voltage (vgs). ID=gm*vgs.The voltage gain (Av) of the amplifier is calculated using this formula:Av = -gm (RD || RL).  
For simulating open LTspice click on configure analysis then put the value which is shown in the fig below  
![Image](https://github.com/user-attachments/assets/d095650b-5e16-4138-a121-2f1b8b738aa2)  
and then right click on Vin and put the waves what you need and put amplitude value as 1.  
C)TRANSIENT ANALYSIS:Transient analysis is all about understanding how the amplifier responds to time-varying signals, like sudden voltage changes or pulse inputs. Imagine you’re sending a quick "blip" of voltage into the amplifier—transient analysis helps us see how the circuit reacts to that blip over time.When the input signal changes suddenly (like a step or a pulse), the amplifier doesn’t respond instantly. Instead, its behavior is influenced by the charging and discharging of capacitors in the circuit.  
For simulating open LTspice click on configure analysis then click on transient then just put the value of stop time as your wish.
## 1.1 CIRCUIT DIAGRAM
![Image](https://github.com/user-attachments/assets/780c8916-68cd-424c-aab2-06a45db15e21)-
## 1.2 PROCEDURE
1.Open LTspice and create a new schematic.  
2.Build the common source amplifier circuit as per the circuit diagram.  
3.Set component values  
4.Download the library file named tsmc018.txt from the provided source.  
5.Create a new folder on your computer.Save the downloaded library file (tsmc018.txt) into this folder.  
6.ADD a SPICE directive to import the library file.  
7.Set the MOSFET model name to CMOSN (as specified in the library file).  
8.Set the transistor parameters such that it should lie in saturation region.  
9.Run the simulation using the .op (operating point) analysis.  
10.After the simulation, check the current flowing through the resistor or the MOSFET  
11.Do it for Transient and AC analysis too  
## 1.3 CALCULATION
Given Power=100uW  
we have to find I  
WKT P=VI where V=1.8v  
hence,I=55.5uA  
Now,VDD=IDRD+VOUT,where VDD=1.8V,ID=55.5uA,RD=1kohm  
so,VOUT=1.745V  
Hence Qpoint=(1.745v,55.5uA)  
## 1.4 RESULTS
A)DC ANALYSIS:  
By adjusting the dimensions of mosfet that is W=203n and L=180n we can get the calculated Id=55.55uA and Vout=1.745V.while we have to ensure that MOSFET is in saturation region.    
![Image](https://github.com/user-attachments/assets/744eee30-b993-44fd-b451-ac6143f0634c)  
B)AC ANALYSIS: 
By simulating we willl get Ac frequency response and we will get  gain=-9.095dB,Bandwidth=215.650GHz and phase difference=102.37 degree  
![Image](https://github.com/user-attachments/assets/cf6407c0-895b-426a-bc37-463ea769ba15)  
C)TRANSIENT ANALYSIS: 
![Image](https://github.com/user-attachments/assets/4d795d54-a631-47af-ade5-6486b445d59a)  
## 1.5 INFERENCE  
1.In DC analysis if we increase W id will also increase and if we increase L Id will decrease.  
2.In AC Analysis if we increase W bandwidth decreases gain increases and phase difference decreases.GAIN is decreasing with time.   
3.The transient response is very smooth.    
## 2.1 CIRCUIT DIAGRAM  
![Image](https://github.com/user-attachments/assets/09740901-fe32-4d49-b71e-c6878d9d009b)  
## 2.2 PROCEDURE  
1.Open LTspice and create a new schematic.  
2.Build the common source amplifier circuit as per the circuit diagram.  
3.Set component values  
4.Download the library file named tsmc018.txt from the provided source.  
5.Create a new folder on your computer.Save the downloaded library file (tsmc018.txt) into this folder.  
6.ADD a SPICE directive to import the library file.  
7.Label both the MOSFET(as specified in the library file).  
8.Set both transistor parameters such that they lie in saturation region.  
9.Connect a diode in PMOS so that we need not worry about that MOSFET to be in saturation.
10.Do the DC,Transient analysis
11.For AC analysis first we have to do DC sweep as shown in fig below  
![Image](https://github.com/user-attachments/assets/adad853c-73fd-4cb9-aced-c5e794056153)  
12.We will get a VTC curve in that select any voltage in saturation region then put the same as DC offset voltage and then run it.
## 2.3 CALCULATION  
Given Power=100uW  
we have to find I  
WKT P=VI where V=1.8v  
hence,I=55.5uA  
Now,VDD=IDRD+VOUT,where VDD=1.8V,ID=55.5uA,RD=1kohm  
so,VOUT=1.745V  
Hence Qpoint=(1.745v,55.5uA)  
## 2.4 RESULTS  
A)DC ANALYSIS:  
By adjusting the dimensions of both the MOSFET'S we can get the operating point for PMOS W=1107n and L=180n and for NMOS also the same  
![Image](https://github.com/user-attachments/assets/8c0141c1-fc62-4646-a40a-852e9b623d8f)    
B)AC ANALYSIS:  
Gain=5.5dB   
![Image](https://github.com/user-attachments/assets/d3ddf39f-c590-47a0-863f-6f20a54fe46d)  
C)TRANSIENT ANALYSIS:  
![Image](https://github.com/user-attachments/assets/213eeebf-00fe-482a-bb0c-3390ae3a3cfc)  
## 2.5 INFERENCE  
1.PMOS dimesnions doesn't have much effect on Id and if we increase the width of NMOS Id will increase.  
2.To keep PMOS always in saturation we have just connected a diode to it.  
3.In AC Analysis response is not stable.  
4.The transient response is very smooth.  
## COMPARISON BETWEEN FIRST AND SECOND CIRCUIT  
![Image](https://github.com/user-attachments/assets/5e048e92-9b5c-4b10-b385-d2866f4f9ee9)  



















