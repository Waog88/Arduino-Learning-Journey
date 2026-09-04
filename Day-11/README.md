# Day 11: [Buttons]

**Date:** September 4, 2026  

---
## 📃 Description
Learned how Buttons works and used LEDs and Buzzers to demonstrate examples.

---

## 📹 Video Demonstration

Click the thumbnail below to watch today's video log:

[![Watch Day 10 Demonstration](https://img.youtube.com/vi/4WxVXUBHACc/hqdefault.jpg)](https://www.youtube.com/watch?v=4WxVXUBHACc)

---

## 🛠️ Hardware Used
* Arduino Board (UNO)
* USB Cable
* LEDs
* Active Buzzer
* Breadboard
* Jumper Wires
* 330Ω Resistor
* 10KΩ Resistor
* Button

---

## 💻 Code

```cpp
//toggle switch

int redPin = 8;
int buttonPin = 12;
int buttonNew;
int LEDState = 0;
int buttonOld = 1;
int dt=100;

void setup() {
  Serial.begin(9600);
  pinMode(redPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop() {
  buttonNew=digitalRead(buttonPin);
  if(buttonOld==0 && buttonNew==1){
    if(LEDState==0){
      digitalWrite(redPin, HIGH);
      LEDState = 1;
    }
    else{
      digitalWrite(redPin, LOW);
      LEDState = 0;
    }
  }
  buttonOld=buttonNew;
  delay(dt);
}

//dimmable led

int buttonPin1 = 12;
int buttonPin2 = 11;
int buttonVal1;
int buttonVal2;
int LEDbright = 0;
int ledPin = 3;
int buzzPin = 2;
int dt=100;

void setup() {
  pinMode(buttonPin1, INPUT);
  pinMode(buttonPin2, INPUT);
  pinMode(buzzPin, OUTPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  buttonVal1 = digitalRead(buttonPin1);
  buttonVal2 = digitalRead(buttonPin2);
  Serial.print("Button 1 = ");
  Serial.print(buttonVal1);
  Serial.print(", ");
  Serial.print("Button 2 = ");
  Serial.print(buttonVal2);
  Serial.print(", ");
  Serial.print("Brightness = ");
  Serial.println(LEDbright);
  delay(dt);

  if(buttonVal1==0){
    LEDbright=LEDbright+5;
  }
  if(buttonVal2==0){
    LEDbright=LEDbright-5;
  }

  if(LEDbright>255){
    LEDbright=255;
    digitalWrite(buzzPin, HIGH);
    delay(dt);
    digitalWrite(buzzPin, LOW);
    Serial.println("Buzz High");
  }
  if(LEDbright<0){
    LEDbright=0;
    digitalWrite(buzzPin, HIGH);
    delay(dt);
    digitalWrite(buzzPin, LOW);
    Serial.println("Buzz LOW");
  }

  analogWrite(ledPin, LEDbright);
}
