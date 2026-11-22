# Tarjeta de expansión PIC18F46Q10

**Tarjeta entrenadora educativa — revisión del esquemático v1.1 (en desarrollo).**

[English](README.md) · [Arquitectura](docs/architecture.md) · [Plan de desarrollo](docs/roadmap.md)

> **Estado:** Esquemático preliminar revisado académicamente. No se ha diseñado ni fabricado la PCB; tampoco se ha validado el circuito físicamente.

## Objetivo

Diseñar y construir una tarjeta de expansión del **Microchip PIC18F46Q10** para prácticas de electrónica y sistemas embebidos. Primero se fabricará un prototipo con componentes **THT**, para facilitar el montaje, la reparación y las pruebas. Después se evaluará un rediseño **SMD** y la fabricación profesional.

## Arquitectura

| Bloque | Función |
| --- | --- |
| `POWER_DC` | Entrada JACK regulada de 7–12 V, protección mediante MOSFET y regulador LM2596 a 5 V. |
| `POWER_USB` | Alternativa de alimentación USB-C a 5 V, resistencias CC, fusible y supresor de transitorios. |
| `POWER_SELECT` | Selección manual entre fuentes, estado OFF e indicador de alimentación. |
| `PIC_CORE` | PIC18F46Q10 PDIP-40, puertos GPIO, RESET, ICSP e indicadores de prueba. |

## Estado del proyecto

- [x] Esquema de cuatro hojas elaborado con Proteus 8.17.
- [x] Revisión v1.1 preparada para documentar los cambios de diseño.
- [ ] Incorporar al repositorio el archivo original `.pdsprj` y el PDF de cuatro páginas.
- [ ] Repetir y documentar ERC sobre la revisión exacta.
- [ ] Comprobar MCLR, VPP, PGC y PGD con el programador MPLAB SNAP.
- [ ] Comprobar encapsulados y asignación de pads en ARES.
- [ ] Diseñar, fabricar y probar el prototipo THT.
- [ ] Rediseñar la PCB con componentes SMD y preparar fabricación externa.

## Observaciones

La entrada JACK de v1.1 ya no incorpora el TVS ni el fusible que se consideraron inicialmente. La alimentación debe proceder de una fuente regulada y protegida, preferiblemente limitada en corriente. En el esquemático v1.1, el capacitor **C9 de 100 nF forma parte del circuito RESET/MCLR** y no debe confundirse con el desacoplamiento de alimentación.

**Los archivos fuente de Proteus y el PDF aún están pendientes de carga al repositorio en línea.** El proyecto no está validado para fabricación.

## Documentación

[Decisiones técnicas](docs/design-decisions.md) · [Lista de comprobación](docs/hardware-review-checklist.md) · [BOM preliminar](docs/bom-draft.csv) · [Historial](CHANGELOG.md)

**Licencia:** pendiente de seleccionar.
