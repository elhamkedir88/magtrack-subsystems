# Power & Actuation PCB (Board 1)

Power distribution, safety interlock and actuation interface for MAGTRACK.
Designed by me in EasyEDA for campus CNC milling. Board 2 (logic) was
designed by [teammate].

## Features
- 24 V battery input with 1.5KE33A TVS and 100 µF bulk capacitor
- 5 V rail (LM2596 module) and 3.3 V rail (MP1584EN module)
- K1 relay: MOTOR_ENABLE_SAFE for both BTS7960 drivers; opens on reset
  or power loss (gate pull-down)
- K2 relay: switches the couplant pump ground; flyback diodes D1 to D3
- Dedicated servo header (H1) with 470 µF local capacitor
- 10-pin stack connector to Board 2

## Fabrication notes
Milled in-house: 20 mil clearance, 20 mil minimum trace, 40 to 60 mil
power traces, pads of 1.8 mm or less.

## Documents
`schematic/` · `layout/` · `docs/Board1_Design_Report.pdf`

## Bring-up checklist
1. Check 5.0 V and 3.3 V with nothing connected
2. Confirm both relays stay open at power-up
3. Confirm enable pins read about 0 V with K1 open
4. Connect Board 2

## Status
[Designed / milled / assembled / tested]. Fuse and servo-header
changes: [done / planned].
