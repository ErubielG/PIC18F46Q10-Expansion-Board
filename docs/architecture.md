# System architecture / Arquitectura del sistema

## POWER_DC

The barrel jack accepts a **regulated 7–12 V DC source**. A P-channel MOSFET (**FQP27P06**) is used for reverse-polarity protection with its gate-bias network and 12 V Zener. A fixed-output **LM2596T-5.0** buck stage includes a **SB560-T** Schottky diode, **68 µH** inductor, and input/output capacitors.

The earlier input TVS and DC fuse were omitted from the v1.1 schematic. **This does not mean the MOSFET protects against input overcurrent or arbitrary voltage spikes.** Use a protected, current-limited external supply for prototyping.

## POWER_USB

A USB-C receptacle (USB4085-GF-A symbol) is configured as a **5 V power sink** using independent **5.1 kΩ** CC pull-downs. VBUS feeds the USB rail through **FU2 (1 A)**, with local 4.7 µF and 100 nF capacitors and a TVS marked SMBJ6 in the schematic. The exact orderable TVS part and connector footprint need validation. USB data and Power Delivery negotiation are not implemented.

## POWER_SELECT

The schematic selects between **5V_DC_JACK**, OFF and **5V_USB_C** to feed the main 5 V rail. A schematic jumper placeholder must be replaced with a suitable physical DC/OFF/USB switch prior to PCB routing. Main supply filter capacitors and a power-indicator LED are provided.

## PIC_CORE

The PIC18F46Q10 is intended for **PDIP-40**. PORTA through PORTD and available PORTE signals are exposed via headers, together with an auxiliary power header, ICSP header, user pushbutton and LED. The ICSP header includes MCLR/VPP, VDD, GND, PGD and PGC.

The **v1.1** RESET network includes a **10 kΩ pull-up (R5)**, **470 Ω series resistor (R6)**, **100 nF capacitor (C9)** and a pushbutton. C9 is connected to the reset node. Programming behavior and decoupling sufficiency must be rechecked.

## Power constraints / Restricciones

- Nominal system rail: **5 V**, not a guaranteed measured value.
- Keep 5 V components and signal levels compatible with the PIC and external modules.
- Do not connect both external sources without verifying the switching arrangement.
- Validate input source capabilities, conductor sizing, buck layout, heat dissipation and protection during PCB design.
