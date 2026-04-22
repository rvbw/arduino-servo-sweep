# Arduino Servo Sweep

## Overview
This project demonstrates how to control a **Servo Motor** using an **Arduino Uno**.  
The servo automatically moves back and forth between two angles in a continuous sweep motion.

This is a basic and essential project for testing servo motors before integrating them into more advanced systems like robotic arms.

![Project Image](Image/image.jpeg)

---

## Components
- Arduino Uno
- Servo Motor
- Jumper Wires
- USB Cable

---

## Wiring

### Servo Connections:
- **Red wire (VCC)** → Arduino **5V**
- **Black/Brown wire (GND)** → Arduino **GND**
- **Yellow/Orange/Green wire (Signal)** → Digital Pin **9**

> Note: Wire colors may vary depending on the servo model.

---

## Code
```cpp
#include <Servo.h>

Servo myServo;

void setup() {
  myServo.attach(9);
}

void loop() {
  for (int angle = 0; angle <= 180; angle++) {
    myServo.write(angle);
    delay(30);
  }

  delay(500);

  for (int angle = 180; angle >= 0; angle--) {
    myServo.write(angle);
    delay(30);
  }

  delay(500);
}
