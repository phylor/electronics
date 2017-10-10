# Potentiometer

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
