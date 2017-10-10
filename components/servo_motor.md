# Servo Motor

## Arduino Example

```arduino
#include <Servo.h>
Servo servo;

const int servoPin = 9;

void setup() {
  servo.attach(servoPin);
  servo.write(0);
}

void loop() {
  servo.write(90);
  delay(20);
}
```
