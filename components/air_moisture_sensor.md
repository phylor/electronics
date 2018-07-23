# Air Moisture Sensor

Example model no.: `DHT11` or `DHT22`

- measures moisture and temperature
- usually 3 or 4 pins

PINs:
- +5V
- OUT
- not used in example
- GND

## Arduino Example

```arduino
// DHT library available from Adafruit
#include "DHT.h"
#define DHTPIN 8
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  dht.begin();
}

void loop() {
  float h = dht.readHumidity();
  float t = dht.readTemperature();

  if(isnan(h) || isnan(t)) {
    // DHT sensor not running
  }
}
```
