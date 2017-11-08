# Infrared Sensor

PINs:
- OUT
- GND
- VCC

To guard the component, a 100 Ohm resistor and a 4.7 mikroF can be used. Connect the resistor between 5V of the arduino and VCC of the sensor. Connect the capacitor between GND and VCC of the sensor.

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
