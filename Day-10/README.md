# Day 10: [Photoresistor]

**Date:** August 30, 2026  

---
## 📃 Description
Learned how photoresistor works and used LEDs and Buzzers to demonstrate examples.
More light = less resistance
Less light = more resistance

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 10 Demonstration](https://img.youtube.com/vi/Zl5yKd1lqUA/hqdefault.jpg)](https://www.youtube.com/watch?v=Zl5yKd1lqUA)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* LEDs
* Passive Buzzer
* Photoresistor
* Breadboard
* Jumper Wires
* 330Ω Resistor
* 5KΩ Resistor

---

## 💻 Code

```cpp

//Photoresistor with LED

int lightPen=A0;
int lightVal;
int dt = 250;
int redPin = 13;
int greenPin = 12;
void setup() {
pinMode(lightPen, INPUT);
pinMode(redPin, OUTPUT);
pinMode(greenPin, OUTPUT);
Serial.begin(9600);
}

void loop() {
lightVal=analogRead(lightPen);
Serial.println(lightVal);
delay(dt);
if(lightVal > 400){
  digitalWrite(redPin, LOW);
  digitalWrite(greenPin, HIGH);
}
if(lightVal < 400){
  digitalWrite(redPin, HIGH);
  digitalWrite(greenPin, LOW);
}
}

//Photoresistor with Buzzer

int lightPen= A0;
int lightVal;
int buzzPin = 8;
int toneVal;
void setup() {
  Serial.begin(9600);
  pinMode(lightPen, INPUT);
  pinMode(buzzPin, OUTPUT);
}

void loop() {
lightVal = analogRead(lightPen);
toneVal = (9./550.)*lightVal-(9.*200./550)+1;
Serial.println(lightVal);
digitalWrite(buzzPin, HIGH);
delayMicroseconds(toneVal);
digitalWrite(buzzPin, LOW);
delayMicroseconds(toneVal);
}
