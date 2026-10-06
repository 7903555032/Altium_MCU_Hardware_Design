# Altium MCU Hardware Design

A custom STM32-based MCU hardware platform designed in **Altium Designer**, covering schematic capture, component selection, power architecture, peripheral interfaces, and PCB layout.

The project is intended as a practical embedded-hardware design platform for developing and testing STM32-based firmware and peripheral interfaces.

---

## Project Overview

This project focuses on designing a custom MCU development board around an **STM32 microcontroller**, moving beyond development boards such as the STM32 Nucleo toward a custom hardware implementation.

### Key Design Areas

- STM32 MCU hardware design
- Power supply and power distribution
- Decoupling and bypass capacitors
- SWD programming/debugging interface
- UART communication
- I2C communication
- SPI communication
- GPIO interfaces
- Interrupt interfaces
- IMU/sensor interface
- Reset and boot configuration
- PCB component placement and routing
- Design Rule Check (DRC) / Electrical Rule Check (ERC)

---

## Hardware Architecture

The board is structured around the following major blocks:

```text
                    ┌─────────────────────┐
                    │     USB / Power     │
                    │     Input Stage     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Power Regulation  │
                    │   & Distribution    │
                    └──────────┬──────────┘
                               │
                               ▼
        ┌────────────────────────────────────────┐
        │              STM32 MCU                 │
        │                                        │
        │  GPIO    UART    SPI    I2C    SWD     │
        └────┬──────┬──────┬──────┬──────┬───────┘
             │      │      │      │      │
             ▼      ▼      ▼      ▼      ▼
          GPIO   UART   SPI    I2C    Debug
                                      / SWD
                              
                         ┌──────────────┐
                         │ IMU / Sensor │
                         │ Interfaces   │
                         └──────────────┘
