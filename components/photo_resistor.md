# Photo Resistor

- more light -> less resistance, i.e. smaller values when reading the sensor

+5V -> Photo Resistor -> 10kOhm -> (A0, GND)

## Arduino Example

```arduino
int photoValue = 0;

void loop() {
  photoValue = analogRead(A0);
}
```
