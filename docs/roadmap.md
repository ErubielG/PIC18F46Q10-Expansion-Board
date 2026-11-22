# Development roadmap / Plan de desarrollo

## Phase 1 — Schematic v1.1 / Esquemático

- [x] Separate circuit into POWER_DC, POWER_USB, POWER_SELECT and PIC_CORE.
- [x] Incorporate academic review into schematic v1.1.
- [ ] Commit unmodified native Proteus source and matching PDF.
- [ ] Run and document ERC for the exact version; review reset/ICSP and power rails.

## Phase 2 — THT prototype / Prototipo THT

- [ ] Verify datasheets and physical footprints.
- [ ] Create board outline, connectors and component placement in Proteus ARES.
- [ ] Route tracks with appropriate current capacity and ground return paths.
- [ ] Run DRC and inspect manufacturing outputs.
- [ ] Assemble and test the first prototype using through-hole components.

## Phase 3 — Verification / Validación

- [ ] Check supply voltages and consumption with a current-limited source.
- [ ] Test both power inputs and source switching.
- [ ] Verify ICSP programming, RESET, user LED/button and all accessible GPIOs.
- [ ] Document measured results, issues and corrective revisions.

## Phase 4 — SMD redesign / Rediseño SMD

- [ ] Select corresponding SMD parts and re-evaluate pinouts, tolerances and thermal needs.
- [ ] Update placement and route, rerun ERC/DRC.
- [ ] Generate Gerbers and drill files for an external PCB manufacturer.

No stage is complete until supporting evidence is uploaded.
