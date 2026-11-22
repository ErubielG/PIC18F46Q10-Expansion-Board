# Hardware review checklist / Lista de verificación

## Schematic / Esquemático

- [ ] Confirm v1.1 ERC; archive its output.
- [ ] Recheck cross-sheet power nets and exact switch behavior.
- [ ] Check PIC18F46Q10 physical pin mapping for PDIP-40.
- [ ] Verify MCLR/VPP, PGC/PGD, reset network and compatibility with MPLAB SNAP.
- [ ] Review whether an additional PIC supply decoupling capacitor is necessary.
- [ ] Confirm USB-C CC1 and CC2 resistors, VBUS routing and USB current capabilities.
- [ ] Specify exact USB TVS part (schematic currently labels it SMBJ6).
- [ ] Validate LM2596 inductor, diode, capacitor electrical and thermal ratings.
- [ ] Confirm the DC input source is protected/current-limited.

## PCB in ARES

- [ ] Identify actual footprint for each component, particularly USB-C and DC selector.
- [ ] Confirm pad numbers against datasheets.
- [ ] Position regulator parts to keep high-current switching loops short.
- [ ] Determine power track widths, clearance rules and ground returns.
- [ ] Verify connector access, mounting holes, labeling and component clearance.
- [ ] Run DRC and confirm no unconnected nets.

## Bring-up / Puesta en marcha

- [ ] Check unpowered continuity and shorts.
- [ ] Apply DC supply with current limit and verify the 5 V rail.
- [ ] Test USB-C input independently.
- [ ] Test source selector, RESET, ICSP and GPIO.
- [ ] Record test conditions, measurements, problems and corrective actions.

**None of the hardware tests are yet claimed as completed.**
