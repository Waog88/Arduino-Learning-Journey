# Day 12: [Servos]

**Date:** September 8, 2026  

---
## 📃 Description
Learned how to operate a servo using commands by including the new library; #include <servo.h> to easily control the servo without the need of manually generating PWM

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 10 Demonstration](https://img.youtube.com/vi/1mZuN0CA5L0/hqdefault.jpg)](https://www.youtube.com/watch?v=1mZuN0CA5L0)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* Photoresistor
* Breadboard
* Jumper Wires
* 5KΩ Resistor
* Servo

---

## 💻 Code

```cpp

//Servo test

#include <Servo.h>
int servoPin=9;
int servoPos=0;
Servo myServo;
void setup() {
Serial.begin(9600);
myServo.attach(servoPin);
}

void loop() {
Serial.println("What angle for the servo? ");
while(Serial.available()==0){

}
servoPos=Serial.parseInt();
myServo.write(servoPos);
}

//Daylight Detector

#include <Servo.h>
int servoPin=9;
int lightPin=A0;
int lightVal;
int angle;
int dt = 250;
Servo myServo;
void setup() {
Serial.begin(9600);
myServo.attach(servoPin);
pinMode(lightPin, INPUT);
pinMode(servoPin, OUTPUT);

}

void loop() {
lightVal=analogRead(lightPin);
Serial.println(lightVal);
delay(dt);
angle=(-16./63.)*lightVal+16.*780./63.;
myServo.write(angle);

}
