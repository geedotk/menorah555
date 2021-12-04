# Menorah555

Menorah555 is an LED menorah that uses flickering LEDs to simulate the candles.
The shamash (helper candle) is removed and used to "light" the other candles.

## Circuit:
The menorah is built around LEDs that look like standard 5-mm LEDs (T-1 3/4), but
they actually have a chip inside that applies PWM to the LED to simulate a 
flickering flame. This means that no special driver circuitry is needed to create
that effect. Thus, the circuit has no microcontroller in it.

The shamash "candle" has a single flickering LED driven with a super cap. The shamash
board is a daughter board that can be unplugged, and the super cap will allow the
LED to keep lit for a while. A current limiter circuit keeps the inrush current down
so that charging the super cap does not cause the power supply to trip the current limit.

The "candle" lighting circuits are built around 555 timers. This could have been done
with fewer parts in a number of ways, but the 555 was selected to silence the
pundits that say, "it could have been done with a 555!" The 555 on each candle is used as
a set-reset flip-flop. Another 555 timer is configured to provide a power-on reset to
ensure that all LEDs (except for the shamash) are unlit when power is turned on. Triggering
of the 555 to turn on the LED is done with a reed switch. The shamash PCB has a magnet
mounted on it to trigger the reed switch and "light" the candle.

## PCB
Schematic capture and PCB layout were done in [KiCad](https://www.kicad.org/) 5.1.12.
There is no problem fitting everything on the PCB because the size is dictated more
by the aesthetics than the component size. In fact, the electrolytic capacitors selected
are MUCH larger than necessary because they are part of the suggestion of a candle shape.

## Base
The base of the menorah was designed in [FreeCAD](https://www.freecadweb.org/) 0.19 and
was designed to be made of acrylic or similar plastic and bent to the proper final
shape. It's not always easy to be consistent in heat-bending acrylic, so it may be better
to drill the mounting holes after bending. Otherwise, the base may not sit flat on a table.

## Flame Diffusors
The flame diffusors were designed in FreeCAD and were meant to be FDM printed in transparent
filament. The layer lines and in-fill will help to diffuse the light.
