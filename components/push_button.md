# Push Button

## Pull-up and Pull-down Resistors

Pull-up: pulls voltage to `HIGH` when circuit is open (button is not pressed)
Pull-down: pulls voltage to `LOW` when circuit is open (button is not pressed)

For arduino, a 10kOhm resistor is usually used (same for pull-up and pull-down). It is important that there is a potential if the circuit is open (i.e. button is not pressed). The 10kOhm resistor does not influence the circuit when the button is pressed (free flow between Arduino input pin and `+5V` via the button). When the the button is not pressed, there is no connection between the arduino pin and thus no potential. That is why the pull-down/-up resistor is required, so that in this situation there is a flow between the arduino input pin and GND or `+5V` (depending whether a pull-down or pull-up resistor is used).

Note that when using pull-down resistors, the arduino input pin needs to provide a current (so that there is a circuit between the arduino pin and GND via the resistor, because the pull-down resistor is connected to GND).

The Arduino already includes internal pull-up resistors. To activate them, e.g. on pin 2:

```
void setup() {
  pinMode(2, INPUT);
  digitalWrite(2, HIGH);
}
```

## Bouncing

in German: `Prellen`

Happens when multiple `HIGH`/`LOW` signals are quickly sent after each other shortly after the press of a button.

### Solutions

Hardware: using a resistor and a capacitor a low-pass filter can be implemented (use a resistor of 10kOhm and a capacitor of 22-100nF).

Software: Use library [Bounce](http://www.arduino.cc/playground/Code/Bounce).

```
#include <Bounce.h>

// Second parameter defines how many milliseconds the input is blocked
Bounce bouncer = Bounce(INPUT_PIN, 20);

void setup() {
  pinMode(INPUT_PIN, INPUT);
}

void loop() {
  bouncer.update();

  // Returns HIGH when input has changed
  int inputValue = bouncer.read();

  if (inputValue == HIGH) {
    
  } else {

  }
}
```

## Arduino Example: Wait for press

In this example, a pull-down resistor is used.

5V -> Push Button -> [10kOhm to GND, Arduino input pin]


```arduino
const int button = 2;
int buttonState = 0;

void setup() {
  pinMode(button, INPUT);
}

void loop() {
  buttonState = digitalRead(button);

  if(buttonState == HIGH) {
    // button pressed
  }
  else {
    // button released
  }
```
