# Entorno en Raspberry Pi

Configuración base para que la Raspberry Pi actúe como computador de percepción/decisión, hablando CAN con un nodo STM32.

**Hardware base**: Raspberry Pi 4 (4-8GB) o Pi 5 — margen necesario para visión/ROS2.

## 1. Sistema operativo

Ubuntu Server 22.04/24.04 LTS de 64 bits (mejor soporte de ROS2) o Raspberry Pi OS Lite 64-bit.

## 2. Interfaz CAN física

La Pi no tiene CAN nativo → HAT con transceptor:

- **PiCAN2 / PiCAN2 Duo** (MCP2515 + MCP2551/SN65HVD230) — opción más usada y fiable.
- Alternativa low-cost: módulo MCP2515 + TJA1050 por SPI.

## 3. Habilitar SocketCAN

En `/boot/config.txt`:

```
dtoverlay=mcp2515-can0,oscillator=16000000,interrupt=25
dtoverlay=spi-bcm2835
```

Luego:

```
sudo ip link set can0 up type can bitrate 500000
```

## 4. Herramientas CAN

- `can-utils` (`candump`, `cansend`, `cangen`)
- `python-can` para scripting/logging
- `SavvyCAN` (GUI de análisis de tramas) — opcional

## 5. Capa de integración robótica

ROS2 Humble/Jazzy, con un nodo `ros2_socketcan` como bridge CAN ↔ ROS2, para que el resto del stack (percepción, planificación) hable ROS2 estándar.

## 6. Microcontrolador AUTOSAR-like

La Pi no soporta AUTOSAR Classic → se añade un **STM32 Nucleo/Discovery** como nodo CAN real.

- AUTOSAR "de verdad" requiere stacks de pago (Vector/EB, con evaluaciones gratuitas limitadas tipo EB tresos) o alternativas open-source como Arctic Core.
- Alternativa realista para el arranque del proyecto: **mini-stack propio inspirado en AUTOSAR** (capas COM, PDU Router, aplicación) sobre HAL de STM32 + FreeRTOS. Ver Fase 5 del [`ROADMAP.md`](../ROADMAP.md) para la evolución hacia un stack real.

## 7. Toolchain cruzada

`arm-none-eabi-gcc` + PlatformIO para agilizar el build del STM32 desde la Pi o desde un PC de desarrollo.

## 8. Contenedores (opcional)

Docker en la Pi para aislar el stack ROS2/percepción de la capa CAN de bajo nivel.
