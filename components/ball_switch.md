# Ball Switch

- German: `Kugelschalter`
- consists of the metal housing and a metal ball on the inside
- only has an open circuit when the ball switch is standing
- when switch is tilted, the circuit is closed

Input pin -> 1kOhm -> Ball Switch -> Ground

## Arduino Example

```arduino
const int switchPin = 6;
int switchValue = 0;

void setup() {
  pinMode(switchPin, INPUT);
}

void loop() {
  switchValue = digitalRead(switchPin);
}
```
