# Proyecto: coche eléctrico a escala

## Objetivo

Coche RC 1/10 con arquitectura de "dominio" tipo automoción real: Raspberry Pi como ECU de percepción/decisión, STM32 como ECU de actuación conectada por CAN.

Requiere el entorno base descrito en [`entorno-raspberry-pi.md`](entorno-raspberry-pi.md).

## Hardware

- Chasis RC 1/10 (tipo Traxxas/HSP o base económica tipo Donkey Car / RC crawler).
- Motor brushless + ESC (control de velocidad electrónico), servo de dirección.
- Raspberry Pi 4/5 + PiCAN2 HAT.
- Cámara (Pi Camera v3 o USB) para percepción (line-following/lane-keeping).
- STM32 Nucleo como ECU de tracción/dirección: recibe comandos por CAN, genera PWM para ESC y servo, lee encoder de rueda.
- IMU (MPU9250/BNO055) por I2C.
- Batería LiPo + BEC para alimentar Pi y electrónica de forma segura y aislada del motor.
- Opcional: LIDAR 2D (RPLIDAR A1) para SLAM/obstáculos.

## Arquitectura software

- **Pi**: ROS2 (percepción con OpenCV/modelo ligero de detección de carril, planificación simple), publica comandos de velocidad/ángulo en un tópico → un nodo bridge los traduce a tramas CAN.
- **STM32**: recibe tramas CAN (velocidad objetivo, ángulo), controla PWM en bucle cerrado con el encoder (PID básico), reporta telemetría (RPM, corriente) de vuelta por CAN.
- Este patrón (Pi = Domain Controller, STM32 = Zone/Actuator ECU) replica la arquitectura zonal que usa la automoción actual.

## Primer hito

Seguimiento de carril con velocidad constante, control PID de dirección basado en cámara, con todo el comando circulando por **CAN real** (no I2C/UART directo), para que el proyecto tenga valor demostrativo de "red vehicular".

## Cómo colaborar en este proyecto

Ver [`../CONTRIBUTING.md`](../CONTRIBUTING.md). Perfiles especialmente útiles aquí: control (PID), visión por computador, firmware STM32/CAN, mecánica/chasis.
