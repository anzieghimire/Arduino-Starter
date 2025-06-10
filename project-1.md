# 🧠 Learning Circuits and Ohm’s Law (For 5th Graders!)

Hi! I’m a 10-year-old who’s learning Arduino and electronics. Today, I learned about:

- 🔗 Series Circuits  
- 🪢 Parallel Circuits  
- ⚡ Ohm’s Law  

Here’s what they mean in simple words — and how they work!
# Ohm’s Law Explained ⚡

Ohm’s Law is a basic rule that helps us understand how electricity flows in a circuit.
V = IR

Where:

- **V** = Voltage (measured in volts, V)  
  *Voltage is like the “push” that makes electricity move.*

- **I** = Current (measured in amps, A)  
  *Current is how much electricity is flowing.*

- **R** = Resistance (measured in ohms, Ω)  
  *Resistance is anything that slows down the electricity.*

---

## How It Works

- If the voltage (V) gets bigger, more current (I) flows.
- If the resistance (R) gets bigger, less current (I) flows.

---

## Example

Imagine you have:

- A battery with **9 volts** (V)
- A resistor with **3 ohms** (Ω)

Using Ohm’s Law, you can find the current:
V / Ω = I, or 9 / 3 = 3.

So, **3 amps** of current flow through the circuit.

---

## Why It’s Useful

Ohm’s Law helps you:

- Calculate how much electricity flows in your circuit  
- Choose the right parts (like resistors) to keep your circuit safe  
- Understand why some parts get hot or don’t work properly

---

> Ohm’s Law is like the secret recipe for making your circuits work perfectly! 🔧✨

---

## 🔗 What is a Series Circuit?

A **series circuit** is when all the parts (like lights or buzzers) are connected one after another in a single line.

### 🚶 Example:
Imagine a line of kids passing a ball down the line. If one kid leaves, the ball can't move anymore!

### ⚡ In a circuit:
- The electricity flows in ONE path only
- If one part breaks, everything stops working ❌
- The lights share the power

```text
+ ------💡------💡------💡------ -
# 🔌 Arduino Starter Kit – Project 1: Blinking LED 💡

## 📘 Project Overview

This was my **first project** using the Arduino Starter Basic Kit! In this project, I learned how to connect an LED to the Arduino and make it **blink** on and off using code.

---

## 🛠️ Components Used

- 1 x Arduino Uno board
- 1 x LED (Light Emitting Diode)
- 1 x 220Ω resistor
- Breadboard
- Jumper wires
- USB cable (to connect to the computer)

---

## ⚙️ Circuit Diagram

- The **long leg** of the LED (positive) connects to **digital pin 13** on the Arduino (through a resistor).
- The **short leg** (negative) goes to **GND**.
- The resistor helps protect the LED so it doesn't get too much power.

---

## 🧠 What I Learned

- How to build a simple circuit on a breadboard
- How to upload a sketch (program) to the Arduino
- How to control an LED using code
- What `setup()` and `loop()` functions do in Arduino code

---

## 💻 Arduino Code

```cpp
void setup() {
  pinMode(13, OUTPUT);  // Set pin 13 as an output
}

void loop() {
  digitalWrite(13, HIGH); // Turn the LED on
  delay(1000);            // Wait for 1 second
  digitalWrite(13, LOW);  // Turn the LED off
  delay(1000);            // Wait for 1 second
}

