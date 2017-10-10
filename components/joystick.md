# Joystick

- simple ones consist of two potentiometers and a push button
- usually found PINs:
  - VRx: x axis (0-1023)
  - VRy: y axis (0-1023)
  - SW: push button
  - GND
  - +5V

## Arduino Example

```arduino
const int joystickXPin = A0;
const int joystickYPin = A1;
int joystickX;
int joystickY;

void loop() {
  joystickX = analogRead(joystickXPin);
  joystickY = analogRead(joystickYPin);
}
```
