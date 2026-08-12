# Day 02: [AnalogWrite]

**Date:** August 12, 2026  

---
## 📃 Description
Explored the use of the analogWrite function to dim leds through Pulse Width Modulation (PWM) signals

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 03 Demonstration](https://img.youtube.com/vi/AAZmq8Flkkw/hqdefault.jpg)](https://www.youtube.com/watch?v=AAZmq8Flkkw)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* LED
* 330Ω Resistor
* Breadboard
* Jumper Wires

---

## 💻 Code

```cpp
int redPin = 9;
int off = 0;
int dim = 15;
int medium = 100;
int bright = 255;
int waitTime = 1000;

void setup() {
  // put your setup code here, to run once:
  pinMode(redPin, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  analogWrite(redPin, off);
  delay(waitTime);
  analogWrite(redPin, dim);
  delay(waitTime);
  analogWrite(redPin, medium);
  delay(waitTime);
  analogWrite(redPin, bright);
  delay(waitTime);
}
