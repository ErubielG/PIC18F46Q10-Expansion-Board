# PIC18F46Q10 Expansion Board

**Educational expansion/trainer board for the Microchip PIC18F46Q10 — schematic revision v1.1 (work in progress).**

[Español](README.es.md) · [Architecture](docs/architecture.md) · [Roadmap](docs/roadmap.md) · [Engineering review](docs/hardware-review-checklist.md)

> **Status:** The v1.1 schematic has been drafted and discussed in an academic review. The PCB has **not** been routed, fabricated, or electrically tested. Do not treat the design as manufacturing-ready.

## Project objective

Design, prototype, and validate a PIC18F46Q10 expansion board suitable for learning embedded systems and digital electronics. The first hardware iteration will use through-hole (THT) parts for accessible assembly and debugging. A later revision will use SMD components and professional PCB fabrication.

Engineering decisions, review feedback, test results, and failures will be documented over time.

## Planned hardware

- **MCU:** Microchip PIC18F46Q10 in a PDIP-40 package.
- **Main rail:** nominal 5 V.
- **DC power:** regulated 7–12 V barrel-jack input, LM2596-based buck conversion, and a reverse-polarity MOSFET circuit.
- **USB-C power:** alternative 5 V sink input with independent CC pull-down resistors, input fuse, filtering, and transient suppression.
- **Source selection:** DC / OFF / USB; the schematic placeholder must be replaced by a verified physical selector before PCB layout.
- **Programming:** six-position ICSP header for a compatible Microchip programmer (MPLAB SNAP planned).
- **Expansion:** access to GPIO ports with 2.54 mm headers, user pushbutton, RESET and indicator LEDs.

## Electrical architecture

| Sheet | Function |
| --- | --- |
| `POWER_DC` | Barrel-jack input, MOSFET, LM2596 buck converter and 5 V output. |
| `POWER_USB` | USB-C 5 V input, CC resistors, fuse and protection. |
| `POWER_SELECT` | Manual supply selection and power indicator. |
| `PIC_CORE` | PIC18F46Q10, ports, RESET/MCLR, ICSP and user I/O. |

## Development status

- [x] Initial architecture and four-sheet schematic in Proteus 8.17.
- [x] Revision v1.1 prepared and academically reviewed.
- [ ] Upload the original `.pdsprj` and four-page PDF files to this repository.
- [ ] Record ERC for the precise revision being published.
- [ ] Verify MCLR/VPP, PGC/PGD and reset network with the intended programmer.
- [ ] Verify physical components, packages and netlist in ARES.
- [ ] Design, build and test the first through-hole PCB.
- [ ] Prepare an SMD revision and manufacturing outputs.

## Technical cautions

The DC-side TVS and input fuse were removed from the v1.1 JACK schematic. This assumes a **regulated, protected, current-limited external source**; the MOSFET is not a substitute for overcurrent or transient protection. The USB input retains a fuse and transient protection.

In the attached v1.1 design, **C9 = 100 nF belongs to the MCLR/reset network**, not the main 5 V decoupling network. Its compatibility with MPLAB SNAP must be checked. Component package assignments, regulatory requirements, electrical performance, and hardware behavior have not been verified.

## Documentation

- [Architecture](docs/architecture.md)
- [Design decisions](docs/design-decisions.md)
- [Hardware review checklist](docs/hardware-review-checklist.md)
- [Preliminary BOM](docs/bom-draft.csv)
- [Roadmap](docs/roadmap.md)
- [Change history](CHANGELOG.md)

## Source files

**Pending upload:** the original Proteus v1.1 project and the four-page schematic PDF are preserved locally but are not yet included in this online repository. This section will link to the exact uploaded files when available.

## License

No license selected yet. No general right to reuse or redistribute the design has been granted. A hardware license will be evaluated in a future revision.
