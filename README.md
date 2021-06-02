MotorControl
============
This Repository has the Kicad source files for an H-Bridge that I want to use in my model RC Boats.
It is based around the DRV8701P H-Bridge driver Chip.

It's used in conjunction with Infineon IDP060N03L-G Mosfets with an Rd-on of 6 mOhm, so they should be good up to around 40-50 Amps.

Features
--------
It's main Features are: 
1. Current measurement via a Shunt resistor.

2. Reverse polarity protection. 

3. A settable maximum current (courtesy of current chopping of the DRV8701)

4. The input current is smoothed via an inductor/capacitor combination of 2.2uH/440uF respectively.

5. A maxixum operating PWM frequency of 50 kHz.

Notes
-----
1. According to my calculations and the voltage that is likely to power the Boats (2S Li-Ion battery packs) the maxixum PWM frequency that the charge pump
of the DRV8701P supports is 86kHz so far outside the problematic resonance frequency of 5.1 kHz of the Inductor/Capacitor current smoothing

2. The total gate charge of one MOSFET is < 14.4 nC which is roughly the number that the reference design in the Data sheet mentions.
In this case The current source for the high-side FETs is set to 100mA via a resistor on the board. This gives the FETs a worst case rise time of 144
ns.

3. The Resonance of the Inductor-Capacitor circuit is at roughly 5.1 kHz, so A PWM frequency a fair bit higher is recommended.)

4. The data sheet mentions a maxixum current chopping frequency of 38 kHz so well inside the maximum supported frequency.
