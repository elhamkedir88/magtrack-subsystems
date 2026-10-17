# Automated Scanning & Dosing Subsystem

## Problem
The baseline design dragged a spring-loaded ultrasonic probe over
corroded steel with continuous couplant flow. This caused transducer
wear, couplant run-off on vertical walls, and poor control of scan
spacing (a 0.5° heading drift changes the helix pitch by ~28 mm per
revolution, versus a 7.2 mm limit).

## Solution
Indexed, step-and-shoot scanning with three parts:
- **X-axis stage:** Nema 11 stepper, lead screw, 200 mm stroke
- **Z-axis dwell cam:** single-lobe cam on an MG995 servo lowers the
  probe at stationary nodes (14 mm stroke, near-zero servo torque in dwell)
- **Micro-dosing:** peristaltic pump meters 80% glycerin ahead of the
  probe (12 mm needle offset, ~50 µL baseline dose)

## Key design decisions
- 6.0 mm square scan grid (8.0 mm probe, 2 mm overlap); 12 mm step rejected (4 mm gaps)
- Dual-spring design: compliance spring (0.54 N/mm, 2.6 mm spacer) gives 4.4 N contact force
- Cam pressure angle ≈ 29° with harmonic rise; servo torque margin ≥ 2.1×
- Squeeze-film and Tate's-law analysis to size the dose and settle time
- Five safety interlocks (I1 to I5) combining hardware and firmware

## Verification (planned)
Six tests with pass criteria: dose calibration, contact force/servo load,
ultrasonic accuracy on a step wedge (±0.1 mm target), raster coverage,
droplet retention at 0/90/180/270°, and spring-only return/interlocks.

## Status
Design Rev 2 complete. Test results: [pending / add as completed].

## Files
- `report/MAGTRACK_Scanning_Dosing_Design_Report_Rev2.pdf`
