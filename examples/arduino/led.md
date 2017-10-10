# LED

![LED on the Arduino](../../assets/arduino_led.jpg)

## Blinking

```arduino
int led = 13;
void setup() {
  pinMode(led, OUTPUT);
}
void loop() {
  digitalWrite(led, HIGH);
  delay(1000);
  digitalWrite(led, LOW);
  delay(1000);
}
```
