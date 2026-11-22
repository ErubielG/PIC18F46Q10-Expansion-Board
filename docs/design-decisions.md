# Design decisions / Decisiones de diseño

| Decision | Rationale | Status |
| --- | --- | --- |
| PIC18F46Q10, PDIP-40 | Accessible educational assembly, probing and replacement | Selected, footprint to verify |
| Four-sheet schematic | Separates DC supply, USB power, selection and MCU core | Implemented in ISIS |
| 7–12 V regulated barrel-jack supply | Restricted and easier-to-test DC input range | Selected |
| LM2596T-5.0 buck regulator | Convert external DC to nominal 5 V | Schematic only; layout/power checks pending |
| FQP27P06 reverse-polarity arrangement | Avoid normal operation with reversed input polarity | Schematic only |
| Remove DC-side TVS and fuse | Simplification after academic feedback | v1.1; requires protected source |
| USB-C 5 V sink with independent CC resistors | Obtain 5 V without USB Power Delivery | Footprint and real current source to validate |
| Manual DC / OFF / USB selection | Make power input choice explicit | Schematic placeholder; physical switch TBD |
| MCLR dedicated to RESET and ICSP | Keep programming functions available | Reset network to validate with SNAP |
| First THT, later SMD | Fast debugging and accessible assembly before miniaturization | Development strategy |

## Open technical points / Asuntos pendientes

1. Validate the exact **v1.1** reset topology, including the 100 nF capacitor at the MCLR reset node.
2. Assign and check footprints against actual datasheets, especially the USB-C connector and selector.
3. Verify switching regulator loop geometry, currents, capacitor ratings and thermal margins.
4. Decide and document power-supply input protections and operator requirements.
5. Generate a new ERC report and verify ICSP signals and power nets before PCB layout.

Do not interpret design selection as test evidence.
