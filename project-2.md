# 🚀 Arduino Starter Kit – Project 2: Spaceship Interface

## 1. 🌟 Introduction of the Project

In this project, I created a **spaceship control interface** using the Arduino Starter Kit.  
It has:

- A **green LED** that stays ON when the spaceship is on **standby**
- Two **red LEDs** that blink like crazy when the spaceship is **launching** and leaving **Earth’s atmosphere**

This helped me learn how to use **buttons**, control **multiple LEDs**, and understand how **electricity flows** in a circuit!

---

## 2. 🔌 Positioning of the Resistors, Switches, Wires, and LEDs

Here’s how I set everything up on the breadboard:

- **Green LED (Standby Mode)**
  - Long leg (positive) → Pin 3 (with resistor)
  - Short leg (negative) → GND

- **Red LED 1 (Launch Mode)**
  - Long leg → Pin 4 (with resistor)
  - Short leg → GND

- **Red LED 2 (Launch Mode)**
  - Long leg → Pin 5 (with resistor)
  - Short leg → GND

- **Button (Launch Trigger)**
  - One side to Pin 2
  - Other side to 5V
  - Connected to GND using a **pull-down resistor** (10kΩ)

Jumper wires connect everything to the Arduino Uno.

---

## 3. 💻 The Arduino Code (with Comments)

```cpp
// Spaceship Launch Controller
// Green LED = standby
// Red LEDs = rocket launch!

int greenLED = 3;
int redLED1 = 4;
int redLED2 = 5;
int buttonPin = 2;

void setup() {
  pinMode(greenLED, OUTPUT);
  pinMode(redLED1, OUTPUT);
  pinMode(redLED2, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop() {
  int buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {
    // Button is pressed - Launch mode!
    digitalWrite(greenLED, LOW);         // Turn OFF standby
    digitalWrite(redLED1, HIGH);         // Red LED 1 ON
    digitalWrite(redLED2, LOW);          // Red LED 2 OFF
    delay(250);                          // Short delay
    digitalWrite(redLED1, LOW);          // Red LED 1 OFF
    digitalWrite(redLED2, HIGH);         // Red LED 2 ON
    delay(250);
  } else {
    // Button not pressed - Standby mode
    digitalWrite(greenLED, HIGH);        // Green LED ON
    digitalWrite(redLED1, LOW);          // Red LEDs OFF
    digitalWrite(redLED2, LOW);
  }
}
