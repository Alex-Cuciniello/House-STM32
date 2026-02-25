# 🏠 Smart Home Simulation with STM32 & Simulink

This project simulates a home automation system using STM32 boards. The control logic is built with Simulink and Stateflow, which auto-generates the C code for the microcontroller.

## 🎯 Project Overview
The system simulates common smart home components:
* **Lights:** Standard LEDs
* **Windows/Blinds:** Servo motors
* **Thermostat/Power Loads:** Relays
* **Status Indicators:** RGB LEDs

## ⚙️ How It Works
Users interact with the system in two ways:

### 1. Manual Control (Buttons)
Physical buttons instantly change the state of a component (e.g., turning a light on or off). These changes are temporary.

### 2. Default Configuration (UART Menu)
By connecting to the board via a serial terminal (UART), users access a menu to set the system's default configuration (e.g., whether windows or lights should be open/on by default).

### 💾 Startup Behavior
Whenever the STM32 board is turned on or reset, it ignores any previous manual button presses. It always boots using the latest default configuration saved via the UART menu.

## 📂 Repository Structure
* `Progetto_Embedded_Gruppo11.slx`: The main Simulink/Stateflow model.
* `Core/` & `Drivers/`: Auto-generated C code and STM32 HAL libraries.
* `STM32CubeIDE/`: Project configuration files for STM32CubeIDE.
* `*.ioc`: STM32CubeMX pinout and peripheral configuration.

## 🛠️ How to Use
1. Import the project folder into STM32CubeIDE.
2. To modify the logic, open the `.slx` file in Simulink, edit the state machines, and rebuild the model. This will update the files in the `Core` folder. Do not manually edit the auto-generated C code.
