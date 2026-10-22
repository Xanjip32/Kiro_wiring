# Safety and design verification

**Do not use the draft drawings as live wiring instructions.**

- **AC mains:** only a qualified person should install or modify mains connections, fuses, switches, protective earthing and enclosure.
- **Low voltage:** disconnect power before wiring, check polarity and continuity, use current-limited test supplies where feasible.
- **Buck converters:** confirm permissible input range, output voltage, current, thermal performance and fault behavior **before** connecting computers or servos.
- **Power budget:** obtain actual device specs; measure transient current and assess concurrent motion/stall cases.
- **Fuses:** choose based on conductors, connectors and fault conditions — not merely the load's typical current.
- **Emergency stop:** a software stop is not equivalent to safely removing hazardous motion power. Validate physical behavior, reset and restart prevention. Choose suitable rated devices.
- **USB power:** verify whether CH343 adapters or hub ports can backfeed power. Do not assume named USB signals specify a safe cable pinout.
- **Review:** identify a responsible hardware reviewer and record results before students use the assembled system.

## Unresolved items in Rev D drawing

1. USB hub DC jack polarity/voltage/current.
2. Jetson carrier-board supply limit and input connector current rating.
3. Wheel and arm motor power-path/connector loading.
4. Converter continuous current and cooling.
5. DC switching device ratings and E-stop behavior.
6. Wire sizes, protection coordination and KiCad electrical rule check.
