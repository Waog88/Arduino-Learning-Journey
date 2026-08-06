# Day 02: [Binary numbers]

**Date:** August 5, 2026  

---
## 📃 Description
Understood how computer works through binary numbers and built a simple binary counter up to 4 digits.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 01 Demonstration](https://img.youtube.com/vi/_Q0NcB_krisE/hqdefault.jpg)](https://www.youtube.com/watch?v=_Q0NcB_krisE)

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
int redPin = 13;

int greenPin = 12;

int yellowPin = 8;

int bluePin = 7;

int waitTime = 1000;

void setup() {

// put your setup code here, to run once:

pinMode(redPin, OUTPUT);

pinMode(greenPin, OUTPUT);

pinMode(yellowPin, OUTPUT);

pinMode(bluePin, OUTPUT);

}

void loop() {

// 0

digitalWrite(redPin, LOW);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, LOW);

delay(waitTime);

// 1

digitalWrite(redPin, LOW);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//2

digitalWrite(redPin, LOW);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, LOW);

delay(waitTime);

//3

digitalWrite(redPin, LOW);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//4

digitalWrite(redPin, LOW);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, LOW);

delay(waitTime);

//5

digitalWrite(redPin, LOW);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//6

digitalWrite(redPin, LOW);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, LOW);

delay(waitTime);

//7

digitalWrite(redPin, LOW);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//8

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, LOW);

delay(waitTime);

//9

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//10

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, LOW);

delay(waitTime);

//11

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, LOW);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//12

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, LOW);

delay(waitTime);

//13

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, LOW);

digitalWrite(bluePin, HIGH);

delay(waitTime);

//14

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, LOW);

delay(waitTime);

//15

digitalWrite(redPin, HIGH);

digitalWrite(greenPin, HIGH);

digitalWrite(yellowPin, HIGH);

digitalWrite(bluePin, HIGH);

delay(waitTime);

}
