# Introduction to Microcontrollers

### What is a **Microcontroller (MCU)**?

* **Definition**: A single integrated circuit containing a processor core, Flash memory, RAM, and peripherals, ideal for embedded applications.

* **Key Components**:
    * **CPU (Central Processing Unit)**: Fetches and executes instructions.
        * **RISC (Reduced Instruction Set Computing)**: Simpler instructions, faster execution.
        * **CISC (Complex Instruction Set Computing)**: More complex instructions, potentially fewer instructions needed.
        * **Instruction Set**: Instructions the CPU understands.
        * **Clock Speed (Hz)**: Instructions executed per second. Higher speed = faster processing.
    * **Memory**:
        * **Flash Memory (Non-volatile)**: Stores your program code.  Think of it as the hard drive of your MCU.
        * **RAM (SRAM, Volatile)**:  Stores data that your program is actively using. Like your computer's RAM, its contents are lost when power is off.
        * **EEPROM/FRAM (Non-volatile):**  Stores small amounts of data that need to be retained even when power is off (e.g., configuration settings).
        * *Other memory types exist (**ROM, PROM**, etc.) but are less common in modern MCUs.*

    * **Peripherals**:
        * **GPIO (General Purpose Input/Output):** These are the most basic peripherals.  They can be configured as either inputs (to read signals) or outputs (to send signals).
        * **ADC (Analog-to-Digital Converter)** / **DAC (Digital-to-Analog Converter)**: Converts between real-world analog signals (like sensor readings) and the digital signals your MCU understands.
        * **Communication Interfaces**:
            * **UART**: Simple serial communication (sensors, displays, debugging).
            * **SPI**: Synchronous, full-duplex serial communication (displays, memory, sensors).
            * **I2C**: Two-wire serial bus, multiple devices (sensors, EEPROMs).
            * **USB**: Connects peripherals to computers (HID, CDC, MSC).
            * **CAN**: Robust communication (automotive, industrial).
            * **Ethernet**: Wired networking.
            * **Wi-Fi**: Wireless networking.
            * **Bluetooth**: Short-range wireless (Classic, BLE).
            * **LoRaWAN**: Long-range, low-power WAN (IoT).
            * **Cellular**: Communication over cellular networks.
        * **Timers/Counters**: Precise timing, event counting.
            * **PWM (Pulse Width Modulation)**: Controls average power (motor control, LED dimming).
            * **Input Capture**: Captures external event time.
            * **Output Compare**: Generates output signal at specific time.
        * **DMA (Direct Memory Access)**:  Peripheral-to-memory data transfer without CPU involvement.
        * **Other**: RTC, Watchdog Timer, CRC/Hash.
* **Embedded Systems**: Dedicated, application-specific systems using MCUs.
* **MCU vs. Microprocessor**: MCUs integrate memory and peripherals; microprocessors require external components.

### Why Use Microcontrollers?
* **Advantages**:
    * **Cost-effectiveness**: Integration reduces component count and board space.
    * **Power efficiency**: Low power consumption is crucial for battery-powered and portable devices.
    * **Small size**: Compact for space-constrained applications.
    * **Real-time control**: Precise timing and fast response for critical tasks.
    * **Dedicated functionality**: Optimized for specific tasks, maximizing efficiency.
    * **Wide range of applications**:  From **IoT** devices and industrial automation to robotics, consumer electronics, medical devices, and aerospace systems.
 
 ---
Next: [2. Considerations](2_considerations.md)