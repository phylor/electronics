# Analog/Digitial Converter

Arduino has a builtin 10 bit A/D converter (therefore the resolution is up to 1024). If the reference voltage is 5V, that means it is possible to catch differences in the analog signal of 4.9mV (5V / 1024).

Read in analog signals using `valAnalog = analogRead(INPUT_PIN);`
