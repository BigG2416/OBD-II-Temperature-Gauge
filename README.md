# OBD-II-Temperature-Gauge
OBD-II Coolant Temperature Gauge & Temp Logger to monitor and display various temperature-related data. 

## Motivation 

My car is old and therefore struggles to warm up during the winter months and cool down in the summer. The gauge will display live data to monitor temperatures and analyse whether there is a potential temperature-related issue. 

## Goals 

- Read and display live vehicle data over the CAN bus and log it to CSV
- Create a baseline map of regular warm-up and cooling behaviour from repeated driving tests
- Analyze incoming data against the baseline and report irregularities (slow warm-up, high coolant temps, varying temperatures)
- Validate across different driving conditions and vehicles

## Measured Data Points 

- Coolant temperature (Primary metric)
- Time
- Vehicle Speed & RPM 
- Intake air temperature (IAT)
- Engine Load 
- Ambient Temperature
- Battery/control module voltage

## Project Roadmap 

Phase 1 - Prototype (Verify data collection and storage): 
Car -> ELM-327 adapter -> Bluetooth/USB -> Laptop -> CSV -> Python analysis

Goal: Prove that data logging and analysis work before building hardware components. 

Phase 2 - Standalone Instrument (Self-contained unit): 

Car -> OBD-II port -> CAN Transceiver -> ESP32 -> OLED display - > MicroSD log -> CSV -> Python Analysis 

Goal: Replace the laptop and ELM327 with an ESP32 that reads CAN directly. Display on an LCD encased in a 3D-printed cluster-style case.

## Status 

[] Phase 1: Connect to the car and read live data
[] Phase 1: CSV logging script
[] Phase 1: First logged runs (city, highway, cold start) 
[] Phase 1: Python analysis and baseline map 
[] Phase 2: ESP32 reads CAN through transceiver
[] Phase 2: Live display and microSD logging
[] Phase 2: Testing on other vehicles
[] Phase 2: Report irregularities using Python analysis

## Hardware 

- ELM327 OBD-II Adapter (Phase 1)
- ESP32 development board (Phase 2)
- CAN transceiver module (Phase 2)
- OLED display and microSD module (Phase 2)

## Software

- ESP32 Firmware
- Python 3

## Repository Layout

```
/logger      Phase 1 logging script
/analysis    Python notebooks and plots
/firmware    ESP32 code (Phase 2)
/data        Sample CSV logs
/docs        Wiring notes and photos
```

## Test Conditions (planned)

Cold start, city driving, highway driving, heater on/off, repeated runs. Data to be collected on more than one vehicle.

## Notes

Data was collected on my own vehicle in normal driving. Not intended for safety-critical use.
