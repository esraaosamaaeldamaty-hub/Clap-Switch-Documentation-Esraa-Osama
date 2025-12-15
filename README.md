# Clap Switch Using LM358 and 555 Timer

## Project Overview
This project implements a sound-activated switch using analog electronics.
A microphone detects sound, an LM358 comparator processes the signal, and a 555 timer activates an LED for a fixed duration.

---

## System Block Diagram
Sound → Microphone → LM358 Comparator → 555 Timer → LED

![Block Diagram](schematic.png)

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

---

## Circuit Schematic
The complete schematic of the clap switch circuit is shown below.

![Circuit Schematic](schematic.png)

---

## Breadboard Implementation
The circuit was implemented on a breadboard as shown.

![Breadboard](breadboard.jpg)

---

## 555 Timer Configuration
The 555 timer is configured in monostable mode.

Three 100kΩ resistors are connected in series to replace the unavailable 270kΩ resistor.

Timing calculation:

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
