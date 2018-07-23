# Transistor

- NPN example model: BC548, able to handle 100mA and 30V
- Arduino: on every pin max. 40mA and in total max 200mA. Use transistors to handle more power.
- Always use a current limiting resistor on the base of the transistor

## Calculate Base Resistor

If no base resistor is used, the transistor uses as much current as it can and eventually burns out.

What you need to know about your circuit:
- **Your load**. The current (mA) applied to the collector/emitter circuit.
- **Supply voltage leading to the collector**.
- **Supply voltage leading to the base**.

Collect the required values from the datasheet:
- **DC current gain h_FE**. To be save, use the minimum value.
- **Voltage drop between base and emitter V_BE(sat)**. To be save, use the maximum value.

Calculation:
- the required current to achieve saturation: `your load / DC current gain h_FE`
- the voltage required to saturate: `base voltage - voltage drop between base and emitter V_BE(sat)`
- calculate the resistor using Ohm's law and the current and voltage calculated above
- half the calculated resistor value so that you always achieve saturation

## Load

Always put the load between the collector supply voltage and the collector. If you put the load between emitter and ground, the voltage between collector and emitter is never going to exceed the base voltage. In that scenario, it is not possible to switch a higher voltage using the transistor.
