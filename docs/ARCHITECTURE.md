# Electrical architecture — working proposal

**Status:** unverified design notes, based on the supplied *KIRO SO-101 Complete two-arm electrical schematic*, Rev D, 2026-10-22.

## Physical subsystems

| Subsystem | Draft concept | Must verify |
|---|---|---|
| AC input | Protected/earthed AC to DC power supply | Qualified AC installation, enclosure, protective earth and local rules |
| Main DC | Proposed 12 V PSU and independently protected branches | Nameplate, maximum sustained/transient current, wire ampacity |
| Computer | Jetson Orin Nano family board via appropriate power input | **Exact model and carrier-board input range/current** |
| Mobile base | Four 12 V-class wheel servos | Servo model, voltage limits, transient current and adapter pinout |
| Arms | Six leader + six follower servos | Actual motor models, 5 V compatibility, stall load and bus injection |
| Conversion | Shared 12 V → 5 V DC–DC buck proposal | Output setpoint, efficiency, continuous current, heatsinking, fuse coordination |
| USB | Powered hub, adapters and peripherals | Hub input voltage/polarity/current; power backfeed risk |
| Motion stop | E-stop concept using contactors/relays | A documented stop-safety assessment and real stop behavior |

The drawing mentions a **12 V / 29 A supply** and a **5 V converter rated at least 15 A continuous (20 A preferred)**. These are **draft assumptions**, not validated procurement recommendations. Do not treat the drawing's fuse numbers as final sizing.

## Design principle: fewer adapters, not fewer safeguards

Consolidating multiple adapters may simplify maintenance, but it also increases shared-supply fault consequences. Independent branch protection, appropriate wire/connector ratings, safe power-off and physical segregation remain necessary.

## Documents to create after hardware audit

1. Verified KiCad schematic and electrical rule check.
2. Voltage/current power budget (idle, normal operation, peak and worst-case).
3. Point-to-point connector and harness table with polarity/pin order.
4. Fuse, conductor, connector and thermal calculations.
5. Motion-stop validation report.
6. Student-safe low-voltage training diagram, separate from the mains assembly.
