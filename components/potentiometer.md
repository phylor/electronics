# Potentiometer

## Digital Potentiometer

Example model no.: MCP4162

Can be used just like analog potentiometers, but is controlled using SPI. Usually digital potentiometers are used when volume/brightness is controlled via keys (up/down) instead of a knob. Digital potentiometers are not as accurate as anlog though!

## Arduino Example

PINs:
- 5V
- A0
- GND

```arduino
const int potiPin = A0;
int potValue = 0;

void setup() {}

void loop() {
  potValue = analogRead(potiPin);
}
```
