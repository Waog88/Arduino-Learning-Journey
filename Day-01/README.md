# Day 01: [Blinking LED, Traffic Light System + Arduino Variables]

**Date:** August 1, 2026  

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 01 Demonstration](https://youtube.com/shorts/_Ji0BdF9HPA?si=UnMv6gbGOzfO1wDz)

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
// Day 01: [Pulsing Light]

void setup() {
  // put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(500);
digitalWrite(13, LOW);
delay(500);
}
```cpp
// Day 01: [Traffic Light]
void setup() {
  // put your setup code here, to run once:
pinMode(12, OUTPUT);
pinMode(8, OUTPUT);
pinMode(7, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(12, HIGH);
delay(500);
digitalWrite(12, LOW);

digitalWrite(8, HIGH);
delay(500);
digitalWrite(8, LOW);

digitalWrite(7, HIGH);
delay(500);
digitalWrite(7, LOW);
}

// Day 01: [Traffic Light + Arduino Variables]
int DELAY_TIME = 5000;
int GREEN_PIN = 12;
int YELLOW_PIN = 8;
int RED_PIN = 7;

void setup() {
  // put your setup code here, to run once:
pinMode(12, OUTPUT);
pinMode(8, OUTPUT);
pinMode(7, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(GREEN_PIN, HIGH);
delay(500);
digitalWrite(GREEN_PIN, LOW);

digitalWrite(YELLOW_PIN, HIGH);
delay(500);
digitalWrite(YELLOW_PIN, LOW);

digitalWrite(RED_PIN, HIGH);
delay(DELAY_TIME);
digitalWrite(RED_PIN, LOW);
}



