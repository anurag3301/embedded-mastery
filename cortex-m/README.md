# Raspberry Pi Pico / Pico W - 1 Year Mastery Syllabus

A **comprehensive 12-month syllabus** to master embedded systems using **Raspberry Pi Pico / Pico W**, progressing from setup and fundamentals to advanced peripherals and capstone projects.

---

## 📦 MODULE 1 (Month 1–2): Setup & Core Foundations

### Month 1: Getting Started with Hardware and SDK

#### Week 1: Environment Setup

* Buy 2x Raspberry Pi Pico / Pico W
* Flash one as **PicoProbe** using UF2 method
* Connect second Pico using **SWD** via PicoProbe
* Install Tools:

  * `arm-none-eabi-gcc`, CMake, OpenOCD
  * `pico-sdk`, VS Code, `Cortex-Debug` extension

#### Week 2: First Project - Blink

* Understand SDK + CMakeLists structure
* Write a C program to blink LED
* Understand GPIO control (`gpio_init`, `gpio_set_dir`, `gpio_put`)

#### Week 3: Buttons and Input

* Read input from GPIO pin
* Implement software debouncing
* Blink LED only when button is pressed

#### Week 4: UART Communication

* Set up UART for logging
* Use serial monitor for input/output
* Echo terminal input from PC

---

### Month 2: Timers, PWM, and ADC

#### Week 5: PWM

* Learn PWM basics in SDK
* Control LED brightness with PWM duty cycle
* Control a servo using `gpio_set_function` and PWM

#### Week 6: ADC

* Connect potentiometer or LDR to ADC pin
* Read and scale analog value
* Display on UART

#### Week 7: Timers

* Use `sleep_ms`, `sleep_us`, and `add_alarm_in_us`
* Create periodic task without `while` loop delays

#### Week 8: Mini Project

* **Thermometer Logger**:

  * Read temp sensor using ADC
  * Print temperature on UART
  * Use timer-based periodic sampling

---

## 🧪 MODULE 2 (Month 3–4): Peripheral Interfaces & Communication

### Month 3: I2C, SPI, and Displays

#### Week 9: SPI Interface

* Connect and configure SPI OLED
* Display text via SPI

#### Week 10: I2C Sensors

* Read from I2C RTC (DS3231) or IMU (MPU6050)
* Display sensor data over UART

#### Week 11: OLED with I2C

* Use SSD1306 OLED with I2C
* Display real-time temperature or sensor data

#### Week 12: Mini Project

* **Sensor + Display**:

  * Use I2C IMU to read orientation
  * Display on OLED

---

### Month 4: Interrupts, Memory, Intro to PIO

#### Week 13: GPIO Interrupts

* Configure interrupt handlers
* Detect rising/falling edges

#### Week 14: Memory Map

* Study Pico memory layout
* Learn linker script basics
* Understand stack/heap allocation

#### Week 15: Intro to PIO

* Write basic PIO blink program
* Use `pioasm`, configure state machines

#### Week 16: Mini Project

* **Rotary Encoder** with interrupt + OLED feedback

---

## 🧠 MODULE 3 (Month 5–6): DMA, PIO & Performance

### Month 5: DMA Transfers

#### Week 17: DMA Fundamentals

* Setup DMA to copy memory
* Transfer ADC data into a buffer using DMA

#### Week 18: Profiling

* Use oscilloscope to measure timing
* Compare CPU polling vs DMA

#### Week 19: Project - ADC Logger

* Use DMA to sample analog waveform
* Send via UART or store on buffer

#### Week 20: Review Week

* Revise DMA, timers, PIO basics
* Consolidate multiple techniques

---

### Month 6: PIO Deep Dive

#### Week 21: PIO Assembly

* Learn instruction set (set, mov, in, out, jmp, etc.)
* Implement PIO blinker in ASM

#### Week 22: WS2812 LEDs

* Control NeoPixels using PIO
* Time pulses precisely

#### Week 23: VGA Signal Generation

* Use PIO to send VGA sync signals
* Display simple patterns (stripes, colors)

#### Week 24: Custom Protocol

* Create GPIO-based custom communication protocol using PIO

---

## 🔁 MODULE 4 (Month 7–8): Multicore, RTOS & Debugging

### Month 7: Multicore Programming

#### Week 25: Core 1 Task

* Use SDK’s multicore library
* Assign independent task to core 1

#### Week 26: Cooperative Scheduling

* Create loop-based cooperative task manager
* Run tasks based on timers

#### Week 27: Simple Scheduler

* Build basic round-robin scheduler
* Print active task on UART

#### Week 28: Mini Project

* **Dual-core UART Logger + ADC Sampler**

---

### Month 8: RTOS & Debugging

#### Week 29: FreeRTOS Basics

* Port FreeRTOS to Pico
* Create tasks, queues, semaphores

#### Week 30: PicoRTOS or FemtoOS

* Study minimal RTOS internals
* Understand context switching

#### Week 31: SWD + gdb Debugging

* Set breakpoints
* Inspect variables, call stacks

#### Week 32: Unit Testing

* Use Unity test framework for C code
* Write tests for basic drivers (ADC, button)

---

## 🧬 MODULE 5 (Month 9–10): USB, Power, Bootloaders

### Month 9: USB Programming

#### Week 33: USB Serial

* Set up USB CDC device
* Use `stdio_usb` for communication

#### Week 34: USB HID Keyboard

* Emulate a keyboard using Pico
* Send keypresses from button inputs

#### Week 35: Linker Script Exploration

* Modify linker script to relocate `.text`, `.bss`, etc.
* Place specific functions in known locations

#### Week 36: Bootloader

* Create bootloader that jumps to user app
* Add button or UART-based trigger

---

### Month 10: Power & Protocols

#### Week 37: Low Power Modes

* Disable unused peripherals
* Use sleep modes efficiently

#### Week 38: Power Optimized Task Loop

* Sleep MCU when no task is active
* Wake on interrupt or RTC

#### Week 39: Sleep Logger Project

* Log timestamp + wake reason
* Store to EEPROM or SD card

#### Week 40: PIO Protocol Decoder

* Use PIO to decode IR or serial protocol
* Display on UART or OLED

---

## 🚀 MODULE 6 (Month 11–12): IoT & Capstone Projects

### Month 11: Wi-Fi & Cloud Integration

#### Week 41: Connect to Wi-Fi (Pico W)

* Use official SDK to connect to AP
* Handle reconnect and timeout

#### Week 42: MQTT Publishing

* Send sensor data to MQTT broker
* Use Node-RED / Mosquitto to receive

#### Week 43: TLS Secure Communication

* Use MbedTLS or SDK’s SSL client
* Secure connection to cloud services

#### Week 44: OTA Updates

* Download config or new binary
* Flash using USB or custom bootloader

---

### Month 12: Final Projects & Showcase

#### Week 45: Choose Final Project

* Logic Analyzer (PIO + DMA)
* RC Controller (PWM + IMU)
* Data Logger (LCD + SD card)
* USB Macro Pad
* IoT Sensor Node

#### Week 46: Prototype

* Implement main logic and interfaces
* Validate hardware & peripherals

#### Week 47: Polish

* Add enclosure, error handling, power logic
* Test reliability

#### Week 48: Publish & Share

* Document all code and hardware
* Upload to GitHub
* Record demo or blog write-up

---

## ✅ Tooling Reference

* **Build**: CMake, pico-sdk
* **Debug**: OpenOCD + gdb, `Cortex-Debug`
* **Test**: Unity (unit testing C)
* **Flash**: picotool, drag-n-drop UF2, SWD

## 📚 Further Reading

* [Pico SDK Docs](https://raspberrypi.github.io/pico-sdk-doxygen/index.html)
* [PIO Guide](https://www.raspberrypi.com/documentation/microcontrollers/pico/PIO.html)
* [Getting Started PDF](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf)
