# Day 09: [Buzzers]

**Date:** August 29, 2026  

---
## 📃 Description
Learned how buzzers work and the different purposes between an active and passive buzzer.
Active: built in oscillator, fixed tone, used for beeps and alarms/sirens
Passive: No oscillator, different tones and frequencies, used to play melodies

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 03 Demonstration](https://img.youtube.com/vi/-wN7i9ABzaU/hqdefault.jpg)](https://www.youtube.com/watch?v=-wN7i9ABzaU)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* Active Buzzer
* Passive Buzzer
* Potentiometer
* Breadboard
* Jumper Wires

---

## 💻 Code

```cpp
//Active Buzzer with potentiometer

int potVal;
int buzzPin = 8;
int potPin = A3;
int dt = 100;
void setup() {
Serial.begin(9600);
pinMode(buzzPin, OUTPUT);
pinMode(potPin, INPUT);
}

void loop() {
potVal = analogRead(potPin);
Serial.println(potVal);
while(potVal>1000){
  digitalWrite(buzzPin, HIGH);
  potVal=analogRead(potPin);
  Serial.println(potVal);
}
digitalWrite(buzzPin, LOW);
}

//Active Buzzer alarm/siren

int buzzPin = 8;
int dt1 = 1;
int dt2 = 2;
int j;
void setup() {
pinMode(buzzPin, OUTPUT);
}

void loop() {
for (j = 1; j <= 100; j=j+1 ){
  digitalWrite(buzzPin, HIGH);
  delay(dt1);
  digitalWrite(buzzPin, LOW);
  delay(dt1);
}
for(j = 1; j <= 100; j=j+1){
  digitalWrite(buzzPin, HIGH);
  delay(dt2);
  digitalWrite(buzzPin, LOW);
  delay(dt2);
}
}

//Passive Buzzer with Potentiometer

int potPin = A3;
int potVal;
int toneVal;
int buzzPin = 8;

void setup() {
  pinMode(potPin, INPUT);
  pinMode(buzzPin, OUTPUT);
}

void loop() {
potVal = analogRead(potPin);
toneVal = (9940./1023.)*potVal+60;
digitalWrite(buzzPin, HIGH);
delayMicroseconds(toneVal);
digitalWrite(buzzPin, LOW);
delayMicroseconds(toneVal);
}
