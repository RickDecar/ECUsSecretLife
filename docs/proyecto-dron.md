# Proyecto: dron cuadricóptero

## Objetivo

Dron con Raspberry Pi como companion computer sobre un flight controller dedicado — el control de vuelo crítico en tiempo real (estabilización) no se reinventa, se apoya en ArduPilot/PX4.

## Hardware

- Frame 250-450mm (F450 es un clásico fiable para empezar).
- Flight controller con ArduPilot o PX4 (Pixhawk 6C, o más económico: Matek H743).
- 4x motor brushless + ESC (o ESC 4 en 1) + hélices acordes al frame.
- Raspberry Pi 4 (o Zero 2W para ahorrar peso, con menos cómputo) conectada al FC por UART/telemetría vía **MAVLink**.
- GPS + brújula (módulo M8N o M10 con compass integrado).
- Cámara (Pi Camera o FPV analógica + digitalizador) para detección de marcadores AprilTag/ArUco (aterrizaje de precisión).
- Batería LiPo 3S/4S + PDB.
- Telemetría radio (SiK 915/433MHz) para monitorizar desde tierra con QGroundControl.

## Arquitectura software

- **FC**: corre ArduPilot/PX4 (estabilización, PID de vuelo, ya resuelto).
- **Pi**: corre DroneKit-Python o MAVSDK para lógica de misión de alto nivel — recibe telemetría, envía waypoints, decide maniobras según visión.

## Primer hito

Misión autónoma de despegue → vuelo a waypoints GPS → detección de marcador ArUco → aterrizaje de precisión guiado por visión.

## Nota sobre CAN

DroneCAN (antes UAVCAN) es el estándar real en dron/robótica que usa CAN. Se puede añadir más adelante con ESCs o sensores DroneCAN vía un adaptador CAN-USB, dando paridad conceptual con el [proyecto del coche](proyecto-coche.md), que sí usa CAN desde el primer hito.

## Cómo colaborar en este proyecto

Ver [`../CONTRIBUTING.md`](../CONTRIBUTING.md). Perfiles especialmente útiles aquí: ArduPilot/PX4, visión por computador (detección de marcadores), integración MAVLink, montaje/tuning de multirrotores.
