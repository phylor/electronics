# Infrared Sensor

PINs:
- OUT
- GND
- VCC

## Arduino Example

```arduino
#include <IRremote.h>
const int sensorPin = 11;

IRrecv irrecv(sensorPin);
decode_results results;

void setup() {
  irrecv.enableIRIn();
}

void loop() {
  if(irrecv.decode(&results)) {
    // results.value contains pressed key (if you press a button on a remote)
    irrecv.resume();
  }

  if(results.value == 0x00..00) {
    // do something
  }
}
```

## PIR (passive infrared) Sensor

Example model no.: `HC-SR501`
