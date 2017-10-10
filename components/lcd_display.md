# LCD Display

- usually compatible with Hitachi HD44780
- usually have 16 pins
- usually 16x2 characters (columns x rows)

## Arduino Example

```arduino
#include <LiquidCrystal.h>

LiquidCrstyal lcd(7, 8, 9, 10, 11, 12); // pins of LCD

void setup() {
  lcd.begin(16, 2); // columns and rows
  lcd.print("Hello world!");
  delay(1000);
}

void loop() {
  lcd.clear();

  lcd.setCursor(0, 0);
  lcd.print("hello");

  lcd.setCursor(0, 1);
  lcd.print("world");

  for(int i = 0; i < 30; ++i) {
    lcd.scrollDisplayLeft();
    delay(150);
  }
}
```
