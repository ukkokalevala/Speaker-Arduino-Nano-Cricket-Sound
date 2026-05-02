Project: Night Cricket Sound Generator (Arduino Nano)
 Overview
This project simulates realistic cricket sounds using an Arduino Nano, a speaker with transistor driver, and an LDR light sensor.
•	 Only active in darkness 
•	 Generates natural, non-repetitive cricket chirps 
•	 Uses pulse-based sound synthesis for realism 
________________________________________
 Components
•	Arduino Nano 
•	50Ω 0.25W speaker 
•	2N2222 (or BC183) transistor 
•	1kΩ resistor (base resistor) 
•	LDR (light-dependent resistor) 
•	10kΩ resistor (for voltage divider) 
•	Breadboard + jumper wires 
________________________________________
 Connections
 Speaker + Transistor (driver stage)
Arduino D9 ── 1kΩ ──> Base (2N2222)

Emitter ────────────> GND

Collector ──────────> Speaker (-)

Speaker (+) ────────> 5V
 Transistor amplifies current → louder sound
________________________________________
 LDR Light Sensor
5V ── LDR ──┬── A0 (Arduino)
            │
           10kΩ
            │
           GND
 Forms a voltage divider:
•	Bright light → HIGH reading 
•	Darkness → LOW reading 
________________________________________
 How It Works
 Light Detection
•	Arduino reads analog value from A0 
•	If below threshold → it’s dark → sound enabled 
 Sound Generation
•	Uses tone() to generate frequency (~4kHz) 
•	Rapid ON/OFF pulses create cricket texture 
•	Random timing removes robotic repetition 
 Natural Behavior
•	Chirps grouped in bursts 
•	Slight variations in: 
o	pitch 
o	timing 
o	spacing 
________________________________________
 Key Features
•	Realistic cricket chirps (not just beeps) 
•	Automatic day/night operation 
•	Simple hardware, no audio files needed 
•	Efficient and low-cost 
________________________________________
 Calibration
Light threshold:
int lightThreshold = 500;
Adjust based on your environment:
•	Too sensitive → lower value 
•	Not triggering → increase value 
Use Serial Monitor to see readings.
Code:
https://github.com/ukkokalevala/Speaker-Arduino-Nano-Cricket-Sound.git
