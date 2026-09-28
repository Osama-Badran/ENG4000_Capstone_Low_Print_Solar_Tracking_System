# ENG4000 Capstone Low-Print Solar Tracking System

A dual-axis solar tracker designed for a wellness campus in Alberta. The system
uses four LDR sensors to find the position of maximum irradiance, drives three
stepper motors to orient a panel array toward it, and streams live telemetry to
a Node-RED dashboard. Site placement was optimized using ArcGIS, and the design
was converted to a VR model for stakeholder review.

Computer Engineering capstone at York University (ENG 4000), in partnership
with the Foundation of the Energy Collective (FEC).

## How It Works

1. Four LDRs sample light intensity from different angles.
2. The firmware picks the maximum reading and identifies which sensor is
   brightest.
3. A deadband threshold prevents the motors from chasing noise.
4. Three stepper motors adjust the panel's horizontal and vertical angles.
5. Angle clamping stops the motors from over-rotating past mechanical limits.
6. Telemetry streams over serial as JSON to a Node-RED dashboard.

Estimated energy capture improved ~15–20% over a fixed-panel baseline.

## Hardware

- Arduino Uno (AVR ATmega328P)
- 3x stepper motors (1 horizontal, 2 vertical) with drivers
- 4x LDR sensors
- ACS712 current sensor, LM35 temperature sensor, voltage divider
- Addressable LED strip for status indication
- Node-RED dashboard on a local server

## Tools

- Arduino IDE
- LTSpice (circuit simulation)
- ArcGIS (geospatial analysis)
- Blender (VR scene)
- Node-RED (telemetry dashboard)
- Siemens NX / AutoCAD (design reference)

## Team

- Osama Badran — Computer Engineering
- Mohammad Gorjian — Electrical Engineering
- Naweedullah Hussaini — Mechanical Engineering
- David Luu — Software Engineering
- Kevin Nguyen — Computer Engineering
- Thivian Varnacumaaran — Electrical Engineering

Client: Foundation of the Energy Collective (FEC)
Supervisor: Hugh Chesser, York University
