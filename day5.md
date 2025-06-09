Resource - https://www.youtube.com/watch?v=INulDwT4HqA&list=PLgwJf8NK-2e55CdbY_WnY6pejPHoojCkJ&index=6

ChatGPT link - https://chatgpt.com/share/6845cf14-bc38-8005-b464-708db132fb07

# 🔧 Harvard Architecture in AVR Microcontroller (ATmega32) – Detailed Summary

---

## 🧠 Von Neumann vs Harvard Architecture

### Von Neumann Architecture
- **First invented**.
- Single memory space for both **RAM (data)** and **ROM (program)**.
- **Common address and data buses** for both code and data.
- CPU **cannot access code and data at the same time**.
- Results in **slower execution** due to bus bottlenecks.

### Harvard Architecture
- **Later invention** designed to overcome Von Neumann's limitations.
- **Separate memories** for RAM and ROM.
- **Dedicated address and data buses** for each.
- CPU can **fetch instructions and access data simultaneously**.
- **Faster and more efficient** execution.
- **ROM and RAM can have overlapping address ranges** due to separate buses.

---

## 💡 AVR Microcontrollers Use Harvard Architecture

AVR microcontrollers (e.g., ATmega32) use Harvard architecture to boost performance, especially in embedded applications.

---

## 🧱 Internal Block Structure of ATmega32

### 🧮 CPU (Central Processing Unit)
- **32 General Purpose Registers**: `R0` to `R31`.
- **ALU (Arithmetic Logic Unit)**: Performs operations like ADD, SUB, AND, OR, COMPARE.
- **Instruction Decoder**: Decodes instructions fetched from ROM.
- **Program Counter (PC)**: Holds the address of the **next instruction** to execute.

---

## 💾 Memory System in ATmega32

### 📘 Flash Memory (ROM / Program Memory)
- **Size**: 32 KB
- **Type**: Non-volatile
- **Architecture**: 32K × 8 bits, arranged as **16K × 16 bits**
- Can **fetch 16-bit instructions in a single cycle**.
- Uses a **16-bit data bus**, address bus, and control bus.

> Even though CPU is 8-bit, it fetches 16-bit instructions for efficiency.

---

### 📘 SRAM (Static RAM / Data Memory)
- **Size**: 2 KB
- **Type**: Volatile (data is lost when power is off)
- Stores variables, temporary data, and stack.

---

### 📘 EEPROM (Electrically Erasable Programmable ROM)
- **Size**: 1 KB
- **Type**: Non-volatile
- Used to store **permanent data** like configuration values.

---

## ⏱️ Timers
- **Timer 0**: 8-bit
- **Timer 1**: 16-bit
- **Timer 2**: 8-bit
- Used for:
  - Delays
  - Event counting
  - PWM
  - Time-based interrupts

---

## 🚨 Interrupt System
- Supports **~23 interrupts**
- Types include:
  - **External Hardware Interrupts**: `INT0`, `INT1`, `INT2`
  - **Timer Interrupts**
  - **Serial Communication Interrupts**

---

## 🧲 I/O Ports and Peripherals
- **Ports**: `PORTA`, `PORTB`, `PORTC`, `PORTD`
  - Used to connect **input/output peripherals**
- **Peripheral Interfaces**:
  - **ADC**
  - **UART**
  - **SPI**
  - **I2C (TWI)**

---

## 🔌 Internal Bus System

- **Address Bus**: 16-bit
- **Data Bus**: 8-bit
- **Control Bus**:
  - Generates synchronization signals like:
    - `MEM_READ`, `MEM_WRITE`
    - `IO_READ`, `IO_WRITE`

---

## ✅ Advantages of Harvard Architecture in AVR
- **Simultaneous access** to instructions and data
- **Improved performance** and reduced latency
- Ideal for **real-time embedded systems**
- **Most modern microcontrollers** follow Harvard architecture

---

## 🧠 Final Thoughts
AVR microcontrollers like **ATmega32** are built using Harvard architecture for **speed, reliability, and efficiency**. Understanding this structure helps you write more optimized and predictable embedded software.

---

