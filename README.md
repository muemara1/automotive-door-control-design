# Automotive Door Control System: Static Design

The static software design of a **two-ECU automotive door control system**
whose ECUs communicate over **CAN**. Graduation project of the Embedded
Software Design Masterclass (Sprints / Egypt FWD), 2023.

## The system

| ECU | Inputs / outputs | Role |
|---|---|---|
| **ECU 1** | Door sensor, speed sensor, light input | Reads the sensors and sends their states over CAN |
| **ECU 2** | Lights, buzzer | Receives the states and drives the outputs |

## Deliverables

- **System schematic, flowcharts** and a **layered static design** for each ECU
- **Full API specification** for every module: name, parameters, return type
  and description (see [`Static_Design/Automotive_Door_Lock_Static_Design.pdf`](Static_Design/Automotive_Door_Lock_Static_Design.pdf))
- **A folder and module skeleton** in C that follows the design

## Layered architecture (per ECU)

```
APP        main.c
Service    OS (scheduler) · COM_Manager · Device_Manager
HAL        ECU 1: DOOR · SPEED · LIGHT       ECU 2: LIGHT · BUZZER
MCAL       DIO · TIMER · CAN · UART
Libraries  STD_Types · Bit_Math · Macros
```

The `.c` files hold the module interfaces from the design. The project
focused on architecture and API design, not on the full implementation.
