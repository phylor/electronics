# I2C

- inter-integrated circuit
- Aka `two wire interface`
- uses SDA and SCL (pin A4 and A5 on Arduino)
- the Arduino functions as master, every connected device is a slave and has one or more hexadecimal addresses which are used by the Arduino to read or write data to those devices (see the devices' datasheet for the addresses)
