# Clap Switch Using LM358 and 555 Timer

## Project Overview
This project implements a sound-activated switch using analog electronics.
A microphone detects sound, an LM358 comparator processes the signal, and a 555 timer activates an LED for a fixed duration.

---

## System Block Diagram
Sound → Microphone → LM358 Comparator → 555 Timer → LED

![Block Diagram]
<br>
<br>
<img width="563" height="412" alt="image" src="https://github.com/user-attachments/assets/ff4a6b6b-ae98-4fa5-a11b-02b28ecd3666" />
<br>

The microphone (or pushbutton in simulation) generates a pulse that is fed 
into the LM358 comparator. When the input exceeds the threshold set by 
the potentiometer, the comparator output triggers the 555 timer in 
monostable mode. The 555 generates a single output pulse of approximately 
3.3 seconds, which drives the LED.


---

## Components Used
- 1x Electret Microphone
- 1x LM358 Operational Amplifier
- 1x NE555 Timer
- 3 × 100kΩ resistors (connected in series)
- 1x 10kΩ Potentiometer
- 1x 10µF Capacitor
- 1x 1µF Capacitor
- 1x Green LED
- 1x 330Ω Resistor
- 1x Breadboard
- 1x DC Power Supply 9V
<br>
<br>

<img width="1131" height="801" alt="image" src="https://github.com/user-attachments/assets/449be659-abc6-44eb-b149-10023cebb024" />


---

## Circuit Schematic
The complete schematic of the clap switch circuit is shown below.

![Circuit Schematic](schematic.png)

---

## Breadboard Implementation
The circuit was implemented on a breadboard as shown.

![Breadboard]
<br>
<br>

(<img width="535" height="807" alt="image" src="https://github.com/user-attachments/assets/66eb1436-9f4c-4cf7-9d95-ec2e76bc0b4f" />
)

---

## 555 Timer Configuration
The 555 timer is configured in monostable mode.

Three 100kΩ resistors are connected in series to replace the unavailable 270kΩ resistor.

Timing calculation=1.1*R*C
So,
Time=1.1*(100kΩ+100kΩ+100kΩ)*10µF=3.3 Seconds


---
## Steps
✅ Step 1: Preparing the Breadboard
<br> <p align="center"> <img width="260" src="https://github.com/user-attachments/assets/f1512b57-bd9e-4e11-b346-1d76a60978fa" /> </p>
The first step is to prepare the full breadboard.
We begin by ensuring that the power rails on both sides of the breadboard are connected together.
This means connecting all positive rails to each other and all negative rails to each other so that the entire board shares a unified power distribution before building the circuit.

<br>
✅ Step 2: Placing the Microphone and the LM358
<br> <p align="center"> <img width="260" src="https://github.com/user-attachments/assets/c013c859-ff74-41ae-bcc9-449c4081d7ba" /> </p>
Next, we place the microphone and the LM358 IC onto the breadboard.
The LM358 is positioned so that its pins sit across the center gap of the breadboard to prevent accidental short circuits between the two sides.

The microphone is placed near the LM358’s input so the signal path stays short and clean.
At this stage, we are only placing components, without wiring them yet.

<br>
---

## Results
- The LED turns ON when a loud clap is detected.
- The LED remains ON for approximately 3 seconds.
- The potentiometer allows sensitivity adjustment.

---

## Conclusion
This project demonstrates a practical application of analog signal processing and timing circuits using LM358 and 555 timer ICs.

---

## Author
Esraa Osama
