# Shift Register

Example model no.: `74HC595`

Used for: Allows another component to have more connections (by controlling 3 pins, you can control up to 8 other pins)

How does it work: The 8 output pins of the shift register are controlled by sending one byte to the shift register (1 byte is capable of identifying on/off on all 8 output pins). The input of the shift register consists of 3 pins (latch, clock and data). When output pins need to be changed, `LOW` is applied to the latch pin to let the shift register know that we want to set the output pins. After that, each pin's on/off status is sent via the data pin to the shift register. After all bits have been enumerated, the latch pin is set to `HIGH`. The shift register stores all states of the output pins (that is why they can be enumerated in serial instead of in parllel).

Multiple shift registers can be concatenated with each other (so that the shift registers have direct connections between each other). Only one data pin is hence required for the controlling unit (e.g. the Arduino). `CLOCK` and `LATCH` pins can be set in parallel (i.e. the same pins on the Arduino can be connected with all shift registers).

## Set Shift Register's Pins on Arduino

```
byte a = B11001101;
digitalWrite(LATCH_PIN, LOW);
shiftOut(DATA_PIN, CLOCK_PIN, MSBFIRST, a);
digitalWrite(LATCH_PIN, HIGH);
```
