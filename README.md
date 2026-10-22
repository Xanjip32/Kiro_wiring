# KIRO Wiring — SO-101 Educational Robot

An open, **student-friendly wiring and electrical engineering project** for a robot inspired by the [LeRobot SO-101](https://github.com/huggingface/lerobot) arm.

> **Status: DESIGN DRAFT — not validated for physical assembly.** Schematics and proposed component values must be checked against the installed hardware before any wiring or energization.

## Why this project exists

Our goal is to simplify the wiring of the KIRO robot while preserving safety, serviceability and educational value. Students should be able to identify where power comes from, how each subsystem is protected, and how to troubleshoot it — without needing to understand the entire robot on day one.

**Current priorities**
- Reduce unnecessary wires, duplicate adapters and messy cable routing.
- Investigate a central power supply, fused distribution and properly rated DC–DC buck converter(s).
- Document professionally in KiCad: electrical schematic, power tree, harness/connector map and bill of materials.
- Turn each verified engineering step into a simple hands-on curriculum for students.
- Keep the learning path modular, approachable and repeatable.

## Proposed system (subject to verification)

The current draft covers **two SO-101-style arms (leader + follower)**, four wheel servos, an onboard Jetson, cameras, lidar, a USB hub and gamepad. The dated Rev D engineering drawing proposes this high-level arrangement:

```text
              AC mains
                 |
        Qualified AC installation
    (protection, isolation, earthing)
                 |
            12 V DC PSU
                 |
       Protected 12 V distribution
          /                \
   12 V subsystems      DC–DC buck
   (base, computer)         |
                      Protected 5 V bus
                       /          \
                   Leader       Follower
```

**This is conceptual, not an assembly-ready schematic.** Different servo and computer revisions can require different voltage/current ratings. Check datasheets, startup/stall loads, DC fuse and connector ratings, grounding, cable size and thermal performance. The USB hub's separate DC input remains **unverified**.

## People

- **Sam:** wiring lead; coordinates physical wiring and harness layout.
- **Engineering/documentation:** wiring simplification, power-load analysis, schematics and design records (specific ownership to be confirmed).
- **Curriculum:** translate each validated task into accessible learning material.

## Start here

1. Read [Safety and verification](docs/SAFETY.md) before connecting anything.
2. Review the [draft architecture](docs/ARCHITECTURE.md).
3. Record actual hardware in the [inventory checklist](docs/HARDWARE_INVENTORY.md).
4. Follow the [student curriculum outline](curriculum/README.md).
5. Submit design evidence and test measurements before calling a schematic *verified*.

## Repository structure

| Location | Purpose |
|---|---|
| `docs/` | Architecture, component audit and safety requirements |
| `curriculum/` | Beginner-first lesson plan |
| `schematics/` | Future native KiCad projects and reviewed drawing exports |
| `wiring/` | Future harness photos, connector tables and routing |
| `tests/` | Future measurements, validation and sign-off |

The original computer-local `Downloads/Kiro_wiring` directory **has not yet been imported**. Project source drawings will be added when they are accessible. Do not confuse this documentation scaffold with a complete or tested hardware repository.

## Engineering workflow

**Inventory → read datasheets → calculate loads → draw schematic → review safety → bench-test low voltage → document results → teach.**

Changes to power distribution, emergency stop, connectors or wire sizes must be reviewed before hardware implementation.

## Attribution

This is a KIRO team educational wiring project inspired by the LeRobot ecosystem. It is not an official Hugging Face or LeRobot hardware release. Reference upstream designs under their respective licenses.
