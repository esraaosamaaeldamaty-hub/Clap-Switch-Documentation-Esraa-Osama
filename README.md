# Clap Switch Using LM358 and 555 Timer
Have you ever wished you could turn on a light without touching a switch?
This project demonstrates a sound‑activated clap switch, which detects a loud clap using a microphone (or a pushbutton in simulation) and triggers a 3‑second timer output using a 555 IC.

This guide is perfect for:

Beginners learning analog electronics

Students building sensor‑based circuits

Anyone who wants to understand how comparators and timers work together

## Project Overview
This project implements a sound-activated switch using analog electronics.
A microphone detects sound, an LM358 comparator processes the signal, and a 555 timer activates an LED for a fixed duration.

---

## System Block Diagram
Sound → Microphone → LM358 Comparator → 555 Timer → LED

![Block Diagram]
<br>
<br>
<img width="471" height="114" alt="image" src="https://github.com/user-attachments/assets/75da8202-4d92-4d4d-8e9b-7ddb085e458f" />

<img width="563" height="412" alt="image" src="https://github.com/user-attachments/assets/ff4a6b6b-ae98-4fa5-a11b-02b28ecd3666" />
<br>

The microphone (or pushbutton in simulation) generates a pulse that is fed 
into the LM358 comparator. When the input exceeds the threshold set by 
the potentiometer, the comparator output triggers the 555 timer in 
monostable mode. The 555 generates a single output pulse of approximately 
3.3 seconds, which drives the LED.


---

## Components Used
| Component               | Quantity | Description                                          |
| ----------------------- | -------- | ---------------------------------------------------- |
| LM358 Op‑Amp            | 1        | Used as a sound comparator                           |
| NE555 Timer             | 1        | Generates the monostable pulse                       |
| Electret Microphone     | 1        | Detects the clap sound (or pushbutton in simulation) |
| 10 kΩ Resistor          | 2        | Mic bias + comparator connections                    |
| 330 Ω Resistor          | 1        | LED current limiting                                 |
| 100 kΩ Resistors        | 3        | Timing resistor (total 300 kΩ)                       |
| Potentiometer 10 kΩ     | 1        | Adjusts comparator threshold                         |
| 1 µF Capacitor          | 1        | AC coupling for the microphone                       |
| 10 µF Capacitor         | 1        | Timing capacitor for the 555                         |
| LED                     | 1        | Output indicator                                     |
| Breadboard              | 1        | For prototyping                                      |
| Jumper Wires            | Several  | For connections                                      |
| Power Supply (9V) | 1        | Circuit power                                        |

<br>
<br>

<img width="1131" height="801" alt="image" src="https://github.com/user-attachments/assets/449be659-abc6-44eb-b149-10023cebb024" />


---

## Circuit Schematic
The complete schematic of the clap switch circuit is shown below.

![Circuit Schematic]
<br>
<img width="1358" height="687" alt="image" src="https://github.com/user-attachments/assets/d57d3df7-0e17-4cf4-b025-11a170836f27" />
<br>


---

## Breadboard Implementation
The circuit was implemented on a breadboard as shown.

![Breadboard]
<br>
<br>

(<img width="535" height="807" alt="image" src="https://github.com/user-attachments/assets/66eb1436-9f4c-4cf7-9d95-ec2e76bc0b4f" />
)

---
## How It Works (Theory)
This circuit consists of two main stages:

A) The Sensor Stage — LM358 Comparator
The microphone generates a very small audio signal.
This signal passes through a 1 µF capacitor for AC coupling (so only sound pulses reach the comparator).

Inside the LM358:

IN+ (Pin 3) receives the microphone's amplified pulse.

IN− (Pin 2) receives a reference voltage set by a 10 kΩ potentiometer.

If the sound level is higher than the threshold:

👉 The LM358 output goes LOW, which triggers the 555 Timer.

This is the key function of a comparator:
Compare a signal to a reference — output reacts only when the signal exceeds the threshold.
<br>
B)555 Timer Configuration
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
🔎 Note: Microphone Polarity Issue (Important Discovery)
During testing, we initially assumed that the electret microphone was non‑polarized, but later discovered that it is actually polarized.
Because of this, the microphone terminals were connected backwards, which caused the circuit to behave incorrectly.

To identify the correct polarity:

We used a multimeter (continuity mode) to check which terminal is internally connected to the microphone’s metallic casing.

The terminal that showed continuity with the metal body is the negative (−) terminal.

The remaining terminal is the positive (+) input.

After correcting the polarity on the breadboard, the microphone stage started working as expected.

<br>

✅ Step 3: Microphone Connections
<br> <p align="center"> <img width="300" src="https://github.com/user-attachments/assets/62c126e8-871f-409c-b56b-19682014dbf7" /> </p>
First, we connect the microphone terminals:

The positive terminal (+) of the microphone is connected to VCC through a 10 kΩ resistor.

The negative terminal (−) of the microphone is connected directly to GND.

<br> <p align="center"> <img width="300" src="https://github.com/user-attachments/assets/b7b95f36-2e36-4504-b01f-519fdf48e90e" /> </p>
Next, we send the microphone signal into the LM358:

The positive terminal (+) of the microphone is connected to a 1 µF capacitor.

The negative terminal of the capacitor (−) is connected to Pin 3 (IN+) of the LM358.

This capacitor provides AC‑coupling, meaning it blocks DC and allows only the audio signal to pass into the comparator.

<br>
✅ Step 4: LM358 Comparator Wiring
<br> <p align="center"> <img width="260" src="https://github.com/user-attachments/assets/acfcb82d-9814-48b6-a1fc-e8fb439853dd" /> </p>
Now we wire the LM358 so it functions as a voltage comparator:

Pin 8 → VCC

Pin 4 → GND

<br>
Setting the Threshold (Pin 2 – IN−)
We use a 10 kΩ potentiometer to create an adjustable reference voltage for the inverting input.

<br> <p align="center"> <img width="400" src="https://github.com/user-attachments/assets/a29661a4-de7a-4bb8-a0d3-1714535a019d" /> </p>
Potentiometer wiring:

One terminal → VCC

The opposite terminal → GND

The middle wiper (center pin) → Pin 2 (IN−) of the LM358

This adjustable reference voltage allows us to control the sensitivity of the sound detection process.
When the microphone signal exceeds the threshold set by the potentiometer, the comparator output switches HIGH and triggers the next stage.

<br>
✅ Step 5: 555 Timer (Monostable) Wiring
<br> <p align="center"> <img width="500" src="https://github.com/user-attachments/assets/2011a5e9-636e-489f-bae8-591dd2f83429" /> </p>
The 555 timer is configured in monostable mode, which generates a single output pulse when triggered by the LM358 comparator.

🔌 Power Connections
Pin 1 → GND
Pin 8 → VCC
Pin 4 (RESET) → VCC
RESET must always be tied HIGH to keep the timer enabled.

🎯 Trigger Connection
Pin 2 (TRIG) is connected to Pin 1 (Output) of the LM358 comparator.
When the LM358 output goes LOW → the 555 is triggered.

<br>
⏱️ Timing Network (R & C)
1) Connect Pin 6 and Pin 7 Together
<p align="center"> <img width="350" src="https://github.com/user-attachments/assets/f43a8032-5021-42a5-b04e-ccc31a445892" /> </p>
Pins 6 (THRESH) and 7 (DISCHARGE) must be connected to form the timing node of the monostable circuit.

2) Add the Timing Resistor (300 kΩ)
We use three 100 kΩ resistors in series to obtain a total of 300 kΩ.
These resistors go between VCC and the Pin 6 & Pin 7 node.

<p align="center"> <img width="500" src="https://github.com/user-attachments/assets/7cb06f2d-28ac-4d99-8e98-c3f66e18c665" /> </p>
This resistor controls how fast the capacitor charges, which sets the pulse duration.

3) Add the Timing Capacitor (10 µF)
<p align="center"> <img width="350" src="https://github.com/user-attachments/assets/3384050c-ded4-4542-8b97-3ebb6a857dd6" /> </p>
Capacitor (+) → connected to Pin 6 & Pin 7

Capacitor (−) → connected to GND

This capacitor determines how long the 555 output stays HIGH.

⏲️ Output Pulse Duration
The monostable pulse width is given by:

T=1.1×R×C
T=1.1×R×C
Using R = 300 kΩ and C = 10 µF, we obtain:

T≈3.3 seconds
The LED connected to Pin 3 will stay ON for about 3 seconds after each trigger.

<br>
✅ Step 6: Output LED
<br> <p align="center"> <img width="260" src="https://github.com/user-attachments/assets/eba0ef32-0ef7-47fe-ae43-0d935f93959b" /> </p>
The final step is connecting the output of the 555 timer to the LED.
Pin 3 (OUT) of the 555 goes HIGH during the monostable pulse, which turns the LED ON for the calculated duration.

LED Wiring:

Pin 3 (OUT) connect with LED Anode (+)

LED Cathode (−) connect with 330 Ω resistor then GND

The 330 Ω resistor is used to limit the current flowing through the LED and protect it from damage.

<br>

---
## Result
- The LED turns ON when a loud clap is detected.
- The LED remains ON for approximately 3.3 seconds.
- The potentiometer allows sensitivity adjustment.
---
## Testing & Troubleshooting
If something goes wrong during testing, here are common issues and fixes:

1- Problem: LED stays ON all the time
Cause: Pin 2 (Trigger) is stuck LOW
Fix:
Ensure LM358 output is not constantly LOW
Check that pins 6 & 7 are not shorted to GND
Check timing capacitor orientation

2- Problem: LED never turns ON
Cause: Comparator threshold is too high
Fix:
Rotate the potentiometer until LM358 output changes
Verify microphone or button signal
Check power to LM358 (Pin 8 = VCC, Pin 4 = GND)
3- Problem: LED pulse is too short
Cause: Timing capacitor too small
Fix:
Use 10 µF instead of 1 µF
Increase timing resistor value
4-Problem: Circuit triggers randomly (noise)
Cause: Floating trigger or weak grounding
Fix:
Ensure pull‑down resistors are in place
Keep wires short
Ensure microphone GND is solid

---
## Conclusion
This project demonstrates a practical application of analog signal processing and timing circuits using LM358 and 555 timer ICs.

---

## Author
Esraa Osama
