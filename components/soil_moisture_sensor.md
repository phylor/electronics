# Soil Moisture Sensor

Example model no.: `HL-69`, `VG400`

## Arduino Example

```arduino
const int moisturePin = A0;
int moistureValue;

void setup() {}

void loop() {
  moistureValue = analogRead(moisturePin);
}
```
