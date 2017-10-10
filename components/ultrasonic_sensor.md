# Ultrasonic Sensor

Example model no.: `HC-SR04`

- ultrasonic sensors work like radar: they send out a ping and wait to receive the pong. Measuring the amount of time it takes for the pong to come back, you can estimate the distance.

PINs:
- VCC
- Trig: when `HIGH`, sends out a ping
- Echo: `HIGH` when pong has been received
- GND

## Arduino Example

```arduino
#include <NewPing.h>

#define trigPin 12
#define echoPin 13
#define MAX_DISTANCE 500

NewPing sonar(trigPin, echoPin, MAX_DISTANCE);

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  int duration, distanceInCm, pos = 0, i;

  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distanceInCm = (duration / 2) / 29.1;
```
