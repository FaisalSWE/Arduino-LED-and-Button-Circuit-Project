# Arduino-LED-and-Button-Circuit-Project
simple Arduino circuit with three LEDs and three push buttons

# Arduino-LED-and-Button-Circuit-Project

# Overview
This project demonstrates a simple Arduino Uno circuit with three LEDs and three push buttons. The LEDs are controlled based on the state of the corresponding buttons.

# Hardware
Arduino Uno
3x LEDs
3x Push Buttons
6x Resistors
Breadboard
wires

# The circuit connects:
LEDs to digital pins 9, 10, and 11 with resistors to ground.
Buttons to digital pins 2, 3, and 4 with pull-down resistors.
Power and ground connections from the Arduino to the breadboard.

# Installation
Upload the provided sketch to your Arduino Uno.

# Usage
Press each button to turn on the corresponding LED.
Release the button to turn off the LED.
The Serial Monitor will display the state of each button.

# Code
```
const int ledPins[] = {13, 12, 11};  // LED pins
const int buttonPins[] = {4, 3, 2};  // Button pins
const int numPins = 3;
int ledStates[] = {LOW, LOW, LOW};   // Initial state of LEDs (all off)

void setup() {
  for (int i = 0; i < numPins; i++) {
    pinMode(ledPins[i], OUTPUT);      // Set LED pins as output
    pinMode(buttonPins[i], INPUT_PULLUP); // Set button pins as input with pull-up
    digitalWrite(ledPins[i], ledStates[i]); // Initialize LEDs to off
  }
}

void loop() {
  for (int i = 0; i < numPins; i++) {
    int buttonState = digitalRead(buttonPins[i]); // Read each button state
    if (buttonState == LOW) {    // Turn OFF the corresponding LED when button is pressed
      ledStates[i] = LOW;
    } else {
      ledStates[i] = HIGH;        // Turn ON the LED when button is not pressed
    }
    digitalWrite(ledPins[i], ledStates[i]); // Update LED state
  }
}
```
