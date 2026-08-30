# Day 07: [Reading Ints and Strings from Serial Ports]

**Date:** August 24, 2026  

---
## 📃 Description
Learned how to read integers and strings from serial ports via user input and used to manipulate variables. Used variables to manipulate the amount of LED blinks and which LED to turn on.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 07 Demonstration](https://img.youtube.com/vi/FKSfGD6m1Uk/hqdefault.jpg)](https://www.youtube.com/watch?v=FKSfGD6m1Uk)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* 330Ω Resistor
* LEDs
* Breadboard
* Jumper Wires

---

## 💻 Code

```cpp
//LED blinks

int redPin = 13;
int dt = 500;
int numBlinks;
String msg="How Many Blinks do you Want: ";
int j;
void setup() {
  Serial.begin(9600);
  pinMode(redPin, OUTPUT);
}

void loop() {
  Serial.println(msg);
  while (Serial.available()==0){

  }
  numBlinks=Serial.parseInt();
  for(j=1; j<=numBlinks; j=j+1){
    digitalWrite(redPin, HIGH);
    delay(dt);
    digitalWrite(redPin, LOW);
    delay(dt);
  }

}

//controlling which LED to turn on

int redPin = 13;
int greenPin = 12;
int bluePin = 8;
String myColor;
String msg = "Hello! ";
String msg2 = "Which LED do you want to light up: ";
void setup() {
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);
  Serial.begin(9600);
}
void loop() {
  Serial.println(msg2);
  while(Serial.available()==0){

  }
  myColor=Serial.readString();
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
}
