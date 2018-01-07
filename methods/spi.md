# SPI

- serial peripheral interface
- uses 4 pins
  - MOSI: master out slave in (D11)
  - MISO: master in slave out (D12)
  - SCK: clock (D13)
  - SS or CS: slave select or chip select (could be any pin, often D10 is used)
- every device requires its own SS pin (that is how a device knows whether master would like to communicate or not). The rest of the pins (MOSI, MISO, SCK) can be shared across all devices.
