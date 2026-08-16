# Day 05: [Potentiometer]

**Date:** August 16, 2026  

---
## 📃 Description
Potentiometers are a variable resistor that takes a input voltage and outputs a fraction of it through a circuit. Showcased it with LEDS and displayed voltages with serial ports.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 03 Demonstration](https://img.youtube.com/vi/hI9oL1ftdxg/hqdefault.jpg)](https://www.youtube.com/watch?v=hI9oL1ftdxg)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* 330Ω Resistor
* LEDs
* Breadboard
* Jumper Wires
* Potentiometer

---

## 💻 Code

```cpp

//Potentiometer with 3 LEDs

int voltPin = A3;
int readVal;
float V2;
int delayTime = 250;
int redPin = 9;
int yellowPin = 6;
int greenPin = 5;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(voltPin, INPUT);
  pinMode(redPin, OUTPUT);
  pinMode(yellowPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  readVal = analogRead(voltPin);
  V2 = (5./1023.)*readVal;
  Serial.print("Potentiometer Voltage is ");
  Serial.println(V2);
  if(V2 < 1){
    digitalWrite(redPin, LOW);
    digitalWrite(yellowPin, LOW);
    digitalWrite(greenPin, LOW);
  }
  if(V2 > 1 && V2 < 2){
    digitalWrite(redPin, LOW);
    digitalWrite(yellowPin, LOW);
    digitalWrite(greenPin, HIGH);
  }
  if(V2 > 2 && V2 < 4){
    digitalWrite(redPin, LOW);
    digitalWrite(yellowPin, HIGH);
    digitalWrite(greenPin, LOW);
  }
  if(V2 > 4 && V2 < 5){
    digitalWrite(redPin, HIGH);
    digitalWrite(yellowPin, LOW);
    digitalWrite(greenPin, LOW);
  }
  delay(delayTime);
}

//Dimmable Light

int potPin = A3;
int potVal;
float LEDVal;
int greenPin = 9;

void setup() {
  // put your setup code here, to run once:
  pinMode(potPin, INPUT);
  pinMode(greenPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  potVal = analogRead(potPin);
  LEDVal = (255./1023.)*potVal;
  analogWrite(greenPin, LEDVal);
  Serial.println(LEDVal);
}
