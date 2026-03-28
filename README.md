# 🚆 Railway Platform Safety System using Arduino

## 📌 Project Overview
The Railway Platform Safety System is an Arduino-based project designed to improve passenger safety at railway stations. It detects unsafe conditions such as passengers crossing the safety line near the platform edge and provides immediate alerts to prevent accidents.

---

## 🎯 Objectives
- Improve railway platform safety  
- Detect passengers near platform edge  
- Provide real-time alerts  
- Reduce accidents and risks  

---

## 🛠️ Components Used
- Arduino Uno  
- IR Sensor  
- Ultrasonic Sensor  
- Buzzer  
- LED  
- Breadboard  
- Jumper Wires  
- Power Supply  

---

## ⚙️ Working Principle
1. Sensors are placed near the platform edge.  
2. IR sensor detects human presence.  
3. Ultrasonic sensor measures distance.  
4. If a person is too close:
   - Buzzer is activated  
   - LED starts glowing  
5. Alert helps prevent accidents.  

---

## 🔌 Circuit Diagram
_Add your circuit diagram image here_

---

## 💻 Arduino Code

```cpp
const int irSensor = 2;
const int buzzer = 3;
const int led = 4;

void setup() {
  pinMode(irSensor, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int sensorValue = digitalRead(irSensor);

  if(sensorValue == LOW) {
    digitalWrite(buzzer, HIGH);
    digitalWrite(led, HIGH);
    Serial.println("Warning! Person detected near edge.");
  } else {
    digitalWrite(buzzer, LOW);
    digitalWrite(led, LOW);
  }
}
