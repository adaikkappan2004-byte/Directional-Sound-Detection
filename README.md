# Directional-Sound-Detection
## Real-Time Sound Direction Detection System

This repository contains the design, simulation, and hardware implementation of a hybrid analog and digital system developed to detect the direction of an incoming sound source in real time. Built using basic electronic components, this project offers a cost-effective, low-power, and hardware-efficient solution suitable for applications in environmental monitoring, security systems, and assistive technology.

### Project Overview

The system relies on a **four-microphone array** arranged in a precise square geometry. When a sudden sound impulse (such as a clap) occurs, it hits each microphone at slightly different times. By capturing and analyzing this **Time Difference of Arrival (TDOA)**, the underlying hardware determines the exact direction of the sound source.

### System Architecture

The system architecture bridges analog signal conditioning with digital combinatorial logic:


**Analog Signal Conditioning:** Signals from the microphone array are amplified using operational amplifiers. A peak detector smooths out raw sound impulses, which are then converted into a negative trigger via a BJT switching circuit.



**Pulse Generation:** A series of NE555 timers configured in monostable mode ingest the trigger to output uniform $50\text{ ms}$ pulses corresponding to each microphone channel.


 
**Time Difference Measurement & Digital Processing:** The pulses feed into a network of six SR flip-flops to latch and establish the precise chronological arrival order (which pulse arrives first vs. last).



**Output Decoding:** A combinational logic decoder circuit interprets the flip-flop states according to a defined truth table to map the acoustic sector and illuminate the corresponding destination LEDs.



### Repository Contents


**Circuit Diagrams & Schematics:** Complete layout mapping the Sound-to-Pulse converters, SR flip-flops, and the output decoder.



**Simulation Results:** Waveform analysis confirming successful transient responses and time-latching capabilities.



**Hardware Design:** Custom PCB layout designs along with photos of the operational breadboard prototype.



---

Developed as part of the Design and Innovation Lab course at Amrita School of Engineering, Coimbatore.
