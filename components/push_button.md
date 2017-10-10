# Push Button

## Arduino Example: Wait for press

5V -> Push Button -> [10kOhm, Arduino input pin]


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
