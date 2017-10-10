# Piezo Speaker

- using PWM it's possible to play different notes (frequencies): `timeHigh = 1 / (2 * frequency)` whereas e.g. `frequency = 440` to play an `A`
- it's possible to use the Piezo speaker as an input device: it registers touches

## Arduino Example: output

```arduino
const int buzzPin = 11;

void setup() {
  pinMode(buzzPin, OUTPUT);
}

void loop() {
  digitalWrite(buzzPin, HIGH);
  delay(1000);
  digitalWrite(buzzPin, LOW);

  tone(buzzPin, 1600, 350);
  delay(750);
  noTone(buzzPin);
}
```

## Arduino Example: detect touches

```arduino
const int buzzPin = A0;
int piezoValue = 0;

void loop() {
  piezoValue = analogRead(buzzPin);
}
```
