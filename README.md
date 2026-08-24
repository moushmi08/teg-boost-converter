# Thermoelectric Waste Heat Harvester with Boost Converter

A TEG-based waste heat energy harvesting circuit paired with a boost
converter to step up its low output voltage into something usable.

## About the Project

Most power generation wastes a huge chunk of energy as heat — think of
the heat pouring out of a power plant's cooling towers. A thermoelectric
generator (TEG) can turn some of that wasted heat directly into
electricity with no moving parts, by exploiting the Seebeck effect: when
one side of a semiconductor pair is hotter than the other, the resulting
temperature gradient pushes charge carriers around and generates a
voltage.

The catch is that a TEG's raw output voltage is usually too low and
unstable to be directly useful, so this project also covers the DC-DC
conversion side — specifically a **boost converter** built around a
MOSFET, a Schottky diode, an inductor, and a capacitor. The design
process works through:

- Why a single-stage DC chopper is more efficient than an AC-link chopper
  for this kind of conversion
- How switching the MOSFET on and off builds up energy in the inductor
  and steps up the voltage at the output
- Deriving the key relationships — output voltage vs. duty cycle, inductor
  and capacitor sizing, current ripple, and diode/MOSFET power dissipation
  — from first principles
- How converter efficiency factors into the duty cycle calculation, and a
  quick note on using paralleled switches to spread thermal/conduction
  losses and push efficiency higher

The final design was simulated in LTspice, targeting an output around
28V, and the resulting voltage and inductor ripple-current waveforms
were compared against the theoretical derivation.

The full theory, hand-derived equations, and simulation results are in
the report PDF included in this repo.

## Tools Used

- LTspice (boost converter simulation and waveform analysis)
