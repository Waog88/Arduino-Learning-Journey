# Day 06: [For Loops and While Loops]

**Date:** August 22, 2026  

---
## 📃 Description
Used both for and while loops in circuits to avoid repeating the same lines of code and understood the differences between them.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 03 Demonstration](https://img.youtube.com/vi/z2ay6iUXEwM/hqdefault.jpg)](https://www.youtube.com/watch?v=z2ay6iUXEwM)

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

//For Loop Example

int redPin = 6;
int yellowPin = 9;
int redTime= 500;
int yellowTime = 500;
int redBlink = 5;
int yellowBlink = 3;
int j;
void setup() {
  pinMode(redPin, OUTPUT);
  pinMode(yellowPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  for(j=1; j <= yellowBlink; j = j + 1){
  digitalWrite(yellowPin, HIGH);
  delay(yellowTime);
  digitalWrite(yellowPin, LOW);
  delay(yellowTime);
  }
  for(j=1; j <= redBlink; j = j + 1){
  digitalWrite(redPin, HIGH);
  delay(redTime);
  digitalWrite(redPin, LOW);
  delay(redTime);
  }
}

//While Loop Example

int potVal;
int dt = 100;
int potPin = A0;
int redPin = 7;
void setup() {
Serial.begin(9600);
pinMode(potPin, INPUT);
pinMode(redPin , OUTPUT);
}

void loop() {
  potVal = analogRead(potPin);
  Serial.println(potVal);
  delay(dt);

while(potVal>1000){
  digitalWrite(redPin, HIGH);
  potVal = analogRead(potPin);
  Serial.println(potVal);
  delay(dt);
}
digitalWrite(redPin, LOW);
}

