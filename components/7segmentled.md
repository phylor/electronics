# 7 segment LED

- exist with controllers offering a serial interface (only 3 PINs: RX, GND and VCC)

## Arduino Example

```arduino
#include <SoftwareSerial.h>

// 3 is the Arduino pin
#define TXdata 3
#define RXdata 2 // not used, provide any value

SoftwareSerial serialPort(RXdata, TXdata);

void setup() {
  pinMode(TXdata, OUTPUT);
  pinMode(RXdata, INPUT);

  serialPort.begin(9600);
  delay(10); // wait for display to be initialized

  serialPort.print("v"); // clear display
  serialPort.print("z"); // Brightness
  serialPort.write(0x40); // 3/4 intensity
  serialPort.print("w"); // decimal point
  serialPort.write(0x10); // turns on colon
}

void loop() {
  serialPort.print("0291"); // display 0291

  // you can also split it
  serialPort.print("02");
  serialPort.print("91");

  // if you don't want to display certain digits, print a space
  serialPort.print("0  1");
}
```
