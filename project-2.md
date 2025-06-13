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
```

## 4. ⚡ How Electricity Flows

Here’s what happens with the flow of electricity in each mode:

### 🟢 Standby Mode (Button NOT Pressed)
- Electricity flows from the Arduino to **Pin 3**.
- It goes through the **green LED** and the **resistor**.
- Then it flows to **GND** (ground), which completes the circuit.
- This keeps the green LED **ON**.

### 🔴 Launch Mode (Button Pressed)
- When the button is pressed, it sends a signal from **Pin 2** to the Arduino.
- The Arduino turns **OFF** the green LED.
- It turns the **red LEDs** ON and OFF quickly, making them **flash**.
- Electricity flows from **Pins 4 and 5**, through the **resistors** and **red LEDs**, then to **GND**.

---

## 5. 🎮 How to Use the Spaceship Interface

Here’s how to play with your awesome spaceship controller:

1. 🔌 **Connect** your Arduino to your computer using the USB cable.
2. 💾 **Upload the code** from the Arduino app to your board.
3. ✅ Once it's uploaded, the **green LED** will turn ON — your spaceship is in **standby mode**.
4. 🛫 **Press the button** to begin the launch!
   - The green light turns OFF.
   - The **two red LEDs** will blink like your rocket is **launching** into space.
5. ✋ Release the button — it returns to **standby mode** and the green LED turns back on.

It’s like you're the **mission control** for a rocket! 🚀🛰️

