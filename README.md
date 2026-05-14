# 5V to 3.3V Low-Dropout Voltage Regulator
A small PCB with a voltage step-down circuit to provide regulated output at 3.3V. The circuit is based on the IC MIC5317-3.3YM5-TR and is designed using Altium Designer. The PCB has provisions for the input and output connector, decoupling capacitors, and a power LED with a series resistor.

## How It Works

The circuit board takes in an unrated DC supply at the J1 header but outputs a stabilized voltage of 3.3 volts through J2 header. The IC used is the MIC5317-3.3YM5-TR, which is a fixed 3.3 volt, 150 mA LDO regulator in SOT-23-5 packaging. The enable pin is connected to high level to ensure the component is permanently enabled while the NC pin is open as per the manufacturer's datasheet. Capacitors placed between both power rails prevent switching noise and ensure stability when loading occurs.

## Design Details

LDO choice. The MIC5317-3.3YM5-TR was chosen due to its low dropout voltage, fixed 3.3V output voltage, small SOT-23-5 package size, and wide input voltage range. No external feedback resistors are needed for this IC, simplifying the layout and decreasing the number of components.

Decoupling capacitors. Capacitors C1 (input capacitor) and C2 (output capacitor) have the same nominal capacity, which equals 10µF, while their maximal working voltage is 25V. In addition, both capacitors are X5R ceramic multilayer capacitors (MLCC).

LED indicator. D1 is connected directly to the VOUT(3.3V) net, while resistor R1 with the resistance value of 120Ω is used to limit the forward current in D1. The use of this LED will ensure that the power supply is active.

## PCB & Schematics

The Altium Designer source files (`.SchDoc` and `.PcbDoc`) are included in the root of this repository.

### Schematic

![Schematic](PCB%20+%20Schematic%20+%20Footprint%20Pictures/Schematic_1.png)

### PCB Layout

![PCB Layout](PCB%20+%20Schematic%20+%20Footprint%20Pictures/PCB_Layout.png)

## Hardware

| Component | Details |
|-----------|---------|
| LDO Regulator | MIC5317-3.3YM5-TR, 150mA, SOT-23-5 |
| Input Capacitor (C1) | 10µF, 25V, X5R MLCC |
| Output Capacitor (C2) | 10µF, 25V, X5R MLCC |
| Current-Limiting Resistor (R1) | 120Ω |
| Power Indicator (D1) | LED |
| Input Connector (J1) | M20-9990246 2-pin header |
| Output Connector (J2) | M20-9990246 2-pin header |
| PCB | Custom board designed in Altium Designer |
