# Day 08: [RGB LEDs]

**Date:** August 25, 2026  

---
## 📃 Description
Learned how RGB LEDs can create new colors by mixing the values of each color; red green and blue, from 0 to 255 giving off more than 16 million colors.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 08 Demonstration](https://img.youtube.com/vi/oo5FhME0vLg/hqdefault.jpg)](https://www.youtube.com/watch?v=oo5FhME0vLg)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* 330Ω Resistor
* RGB LEDs
* Breadboard
* Jumper Wires

---

## 💻 Code

```cpp
int redPin = 8;
int greenPin = 9;
int bluePin = 10;
int dt = 500;
String myColor;
String msg = "What Colour Do You Want?";
void setup() {
  Serial.begin(9600);
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);
}

void loop() {
  Serial.println(msg);
  while(Serial.available()==0){

  }
  myColor = Serial.readString();

  if(myColor == "red"){
    digitalWrite(redPin, HIGH);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, LOW);
  }
  if(myColor == "green"){
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, HIGH);
    digitalWrite(bluePin, LOW);
  }
  if(myColor == "blue"){
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, HIGH);
  }
  if(myColor == "off"){
    digitalWrite(redPin, LOW);
    digitalWrite(greenPin, LOW);
    digitalWrite(bluePin, LOW);
  }
  if(myColor == "yellow"){
    analogWrite(redPin, 255);
    analogWrite(greenPin, 50);
    analogWrite(bluePin, 0);
  }
  if(myColor == "cyan"){
    analogWrite(redPin, 0);
    analogWrite(greenPin, 255);
    analogWrite(bluePin, 80);
  }
  if(myColor == "magenta"){
    analogWrite(redPin, 255);
    analogWrite(greenPin, 0);
    analogWrite(bluePin, 100);
  }
}
