# ENG4000 Capstone Low-Print Solar Tracking System
# Low-Footprint Solar Farm & Tracking System

A dual-axis solar tracker designed for a wellness campus in Alberta, built as
a Computer Engineering capstone at York University (ENG 4000) in partnership
with the Foundation of the Energy Collective (FEC).

The system uses four LDR sensors to find the position of maximum irradiance,
drives three stepper motors to orient a panel array toward it, and streams
live telemetry to a Node-RED dashboard. Site placement was optimized using
ArcGIS, and the design was converted to a VR model for stakeholder review.

Team project — six members across Electrical, Computer, Mechanical, and
Software Engineering. This repo contains my contributions plus the shared
team materials.

## What I Worked On

- **Firmware** — embedded C/C++ on Arduino Uno (AVR) driving three stepper
  motors for dual-axis positioning. Polling control loop over four LDR
  sensors, deadband threshold logic to prevent oscillation, and angle-clamping
  safety limits on both axes.
- **Sensor integration** — calibrated the LDR array and diagnosed inconsistent
  readings using a multimeter and oscilloscope; traced intermittent failures
  to EMI from the motor drivers and mitigated with hardware filtering and
  software averaging.
- **Telemetry** — serialized voltage, current, power, temperature, and energy
  as JSON to a Node-RED dashboard for live monitoring.
- **VR visualization** — converted CAD models into an immersive VR scene in
  Blender for design validation and stakeholder presentations.
- **Geospatial analysis** — used ArcGIS to optimize panel placement on the
  real site, reducing land usage while maintaining output targets.
- **Grid integration support** — assisted the electrical team with
  system-level feasibility analysis.

The mechanical design, structural analysis, and power electronics were led
by other team members. Their work is included in the shared repo below for
completeness.

## How It Works

1. Four LDRs sample light intensity from different angles.
2. The firmware picks the maximum reading and identifies which sensor is
   brightest.
3. A deadband threshold prevents the motors from chasing noise.
4. Three stepper motors adjust the panel's horizontal and vertical angles.
5. Angle clamping stops the motors from over-rotating past mechanical limits.
6. Telemetry streams over serial as JSON to Node-RED.

Estimated energy capture improved ~15–20% over a fixed-panel baseline.

## Hardware

- Arduino Uno (AVR ATmega328P)
- 3x stepper motors (1 horizontal, 2 vertical) with drivers
- 4x LDR sensors
- ACS712 current sensor, LM35 temperature sensor, voltage divider
- Addressable LED strip (for status indication)
- Node-RED dashboard on a local server

## Tools

- Arduino IDE
- LTSpice (circuit simulation)
- ArcGIS (geospatial analysis)
- Blender (VR scene)
- Node-RED (telemetry dashboard)
- Siemens NX / AutoCAD (design reference)

## Repo Structure
