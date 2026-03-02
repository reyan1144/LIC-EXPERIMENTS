# INSTRUMENTATION-AMPLIFIER  
# INTRODUCTION  
An instrumentation amplifier is a specialized differential amplifier designed for precise signal amplification in noisy environments. It features high input impedance, excellent common-mode rejection ratio (CMRR), and adjustable gain, making it ideal for sensor signal conditioning. Unlike standard op-amps, it minimizes noise and interference, ensuring accurate measurements in applications like medical devices and industrial sensors. Typically built with three op-amps and a gain-setting resistor, it provides stable performance even in challenging conditions. Its versatility and precision make it a critical component in data acquisition and control systems.  

![Image](https://github.com/user-attachments/assets/a3b6301c-7963-4cf3-ac09-4b40c27d5538)  

# ADVANATGES  
1. High Common-Mode Rejection (CMRR) – Effectively cancels noise and interference from signals.
2. High Input Impedance – Minimizes signal distortion by not loading the source.
3. Precise Adjustable Gain – Allows accurate amplification with a single external resistor.

# DISADVANATGES  
1. Higher Cost – More complex than standard op-amps due to additional circuitry.
2. Limited Bandwidth at High Gains – Gain-Bandwidth Tradeoff reduces speed at higher amplifications.
3. Power Consumption – Typically draws more current than basic amplifiers.

# APPLICATIONS  
1. Medical Devices – ECG, EEG, and patient monitoring systems.
2. Industrial Sensors – Strain gauges, pressure transducers, and bridge amplifiers.
3. Audio & Data Acquisition – Low-noise signal conditioning in test equipment.

# QUESTION  
Design an Instrumentation amplifier using 3 op-amp configuration with the following constraint  
A) R1=R2=R3=R4=R5=R6=100KΩ  
B)Difference gain Adm=20V/V - Find Acm and calculate CMRR for Adm=20V/V and 50V/V , Use LTspice Simulator.  

# CALCULATION AND ANALYSIS  

1) Adm=20V/V

Adm= (R2/R1) * (1 + 2 * (R5/RG))  
20 = (100k / 100k) × (1 + 2 × (100k / RG))  
RG = 10.52 Kilo ohm  

![Image](https://github.com/user-attachments/assets/122381c3-7ef5-4696-9f08-005eb0a73501)  

Vout = 12V approx  
Gain = Vout/Vin = (1.1 - 0.5 ) / 12 = 20  

Analysis for Acm  

![Image](https://github.com/user-attachments/assets/87b882e7-8932-4844-bb27-6bbd536b1725)  

Vout = 1 * 10^-9  
Acm = (1 * 10^-9) / 100 * 10^-3 = 1 * 10^-8  

CMRR = 20log(Adm/Acm) = 186.02dB  

2) Adm=50V/V

Adm= (R2/R1) * (1 + 2 * (R5/RG))  
50 = (100k / 100k) × (1 + 2 × (100k / RG))  
RG = 4.08 Kilo ohm  

![Image](https://github.com/user-attachments/assets/0cc912f0-5934-4d17-96d4-7107152544db)  

Vout = 12V approx  
Gain = Vout/Vin = (1 - 0.76 ) / 12 = 50  

Analysis for Acm  

![Image](https://github.com/user-attachments/assets/e889813a-9093-4a91-9aaa-332fe2d14837)  

Vout = 1 * 10^-9  
Acm = (1 * 10^-9) / 100 * 10^-3 = 1 * 10^-8  

CMRR = 20log(Adm/Acm) = 193.97dB  



















