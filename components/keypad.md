# Keypad

- usually matrix controlled: there is one pin for every column and one for every row

## Arduino Example

```arduino
// Requires Keypad library
#include <Keypad.h>

const byte ROWS = 4;
const byte COLS = 4;
char keys[ROWS][COLS] = {
  {'1','2','3','A'},
  {'4','5','6','B'},
  {'7','8','9','C'},
  {'*','0','#','D'}
};
// Pins on the Arduino
byte rowPins[ROWS] = {2,3,4,5};
byte colPins[COLS] = {6,7,8,9};

Keypad keypad = Keypad(makeKeymap(keys), rowPins, colPins, ROWS, COLS);

void setup() {}

void loop() {
  char key = keypad.getKey();

  if(key != NO_KEY) {
    // ...
  }
}
```
