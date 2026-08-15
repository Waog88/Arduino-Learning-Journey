# Day 04: [Reading Analog Voltage]

**Date:** August 15, 2026  

---
## 📃 Description
Learned how to read voltage of a circuit with use of ohms law.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 03 Demonstration](https://img.youtube.com/vi/z41suus4xRE/hqdefault.jpg)](https://www.youtube.com/watch?v=z41suus4xRE)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* 330Ω Resistor
* 100Ω Resistor
* Breadboard
* Jumper Wires

---

## 💻 Code

```cpp
int readPin = A4;
float V2 = 0;
int waitTime = 500;
int readVal;

void setup() {
  // put your setup code here, to run once:
pinMode(readPin, INPUT);
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
readVal = analogRead(readPin);
V2 = (5./1023.)*readVal;
Serial.println(V2);
delay(waitTime);
}
