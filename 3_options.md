# Common Microcontroller Platforms

*updated 2024*

This section provides a concise overview of popular microcontroller platforms, categorized by common application areas and key features. Costs are approximate and can vary.  Refer back to [2. 10 selection factors](2_considerations.md) when considering these options.

## Overview: Choosing the Right Microcontroller

Developing portable and wearable projects involves key decisions regarding power, size, and functionality.  Consider these factors when selecting a microcontroller:

**General Design Considerations:**

* **Power Management:** Crucial for battery life.  Utilize sleep modes, low-power peripherals, and efficient code. Consider PMICs for battery management.
* **Development Tools:** Choose an IDE (Arduino IDE, PlatformIO, manufacturer SDKs) and a language (C/C++, MicroPython, CircuitPython) suitable for your skills and project.
* **Ecosystem:** Leverage hardware ecosystems (like Adafruit Feather) for simplified prototyping and component availability.
* **Wireless:** Select the appropriate wireless protocol (BLE, Wi-Fi, etc.) based on range, data rate, and power needs. The nRF52840 offers excellent multi-protocol support (BLE 5, Thread, Zigbee, NFC).
* **Displays:** Prioritize low-power displays (e.g., e-ink) and consider size and interface (SPI, I2C).
* **Processing (AI/DSP):** For AI/DSP, select MCUs with sufficient processing power, FPU, and DSP. (See recommendations below).


**Microcontroller Recommendations (by Application):**

* **Ultra-Low Power, Minimal Resources (Simple sensors, long battery life):**
    * **Texas Instruments MSP430:** Exceptional power efficiency for basic tasks.
    * **Microchip ATTiny85:**  Tiny and ultra-low power, perfect for space-constrained designs.

* **Compact with USB (USB peripherals, wearables):**
    * **ATmega32U4:** Built-in USB for HID and other USB applications. (See *Microchip AVR* section).

* **Cost-Effective 8-bit (Simple projects, beginners):**
    * **Microchip AVR (ATmega328P, etc.):** Widely used, large community, Arduino IDE compatibility.  (See *Microchip AVR* section).
    * **PIC16/PIC18:**  Microchip's cost-effective options. (See *PIC* section).
    * **STM8:**  Another cost-effective 8-bit option from STMicroelectronics. (See *STM8 Family* section).

* **Low Power with Wireless (Connected sensors, basic wearables):**
    * **Nordic nRF52832:**  Power-efficient BLE connectivity.  (See *Nordic* section).
    * **ESP32-S2:**  Cost-effective for Wi-Fi, usable for some BLE applications. (See *Espressif* section).

* **Balanced Power/Performance with Wireless (Wearables, data logging, IoT):**
    * **Nordic nRF52840:** More powerful than the nRF52832, with additional wireless protocols.  (See *Nordic* section).
    * **Raspberry Pi Pico W:** Affordable dual-core with Wi-Fi, easy to use with MicroPython. (See *Raspberry Pi RP2040* section).

* **High Performance with Wireless (Complex wearables, edge AI, robotics):**
    * **ESP32/ESP32-S3:**  Dual-core with Wi-Fi/Bluetooth. S3 adds a camera interface. (See *Espressif* section).
    * **Arduino Nano RP2040 Connect:**  RP2040 with integrated Wi-Fi, Bluetooth, and onboard sensors. (See *Raspberry Pi RP2040* section).

* **Real-Time Applications & DSP (Signal processing, time-sensitive):**
  * **Teensy (PJRC) Family (e.g., Teensy 4.0, 4.1, LC):**  For audio processing, robotics, and real-time applications, uses Arduino IDE
  * **STM32F4 Series (e.g., STM32F407VG, STM32F446RE):**  Good balance of performance, features (FPU, DSP instructions), and affordability.
  * **STM32H7 Series:**  Significantly more processing power for demanding real-time DSP, more expensive.

* **Image/Audio AI (On-device machine learning):**
    * **ESP32-S3:** Good balance of performance, memory, and cost.
    * **STM32F7/H7:**  Powerful for demanding DSP and AI due to FPU and dedicated DSP instructions. (See *STM* section).
    * **Microchip SAM D51:** Cortex-M4F with FPU suitable for some DSP/AI tasks. *See (*Microchip* section)*
    * **Dedicated AI Accelerators:**  For complex AI, consider dedicated hardware (e.g., Google Coral) used in conjunction with a suitable MCU.

  
## Popular MCU Platform Details

### Microchip AVR 

*Used in many Arduino boards*

* **ATmega328P (e.g., Arduino Uno, Nano):**
    * **Approx. Cost:** $1 - $5
    * **Compute Power:** Low to moderate
    * **Key Features:** 8-bit AVR core, versatile peripherals, widely used in Arduino projects.
    * **Pros:** Large community support, Arduino IDE compatibility, widely available, inexpensive.
    * **Cons:** Limited resources (memory, peripherals) compared to 32-bit MCUs.

* **ATmega32U4 (e.g., Arduino Leonardo, Micro, SparkFun Pro Micro):**
    * **Approx. Cost:** $7 - $15
    * **Compute Power:** Low to moderate
    * **Key Features:** 8-bit AVR core, built-in USB controller.
    * **Pros:** Built-in USB for HID devices and serial communication, Arduino IDE support.
    * **Cons:** Limited resources compared to 32-bit MCUs. Slightly more expensive than the ATmega328P.

* **ATtiny85 (and other ATTiny variants):**
    * **Approx. Cost:** $0.50 - $3
    * **Compute Power:** Low
    * **Key Features:** Simplified AVR core, very small footprint, low power consumption.
    * **Pros:** Ultra-low power, inexpensive, easy for basic tasks, small size.
    * **Cons:** Extremely limited resources (memory, peripherals).


### Raspberry Pi RP2040

* **Raspberry Pi Pico:**
    * **Approx. Cost:** $4 - $10
    * **Compute Power:** Moderate to High (Dual-Core ARM Cortex-M0+)
    * **Key Features:** Dual-core RP2040 chip, flexible I/O, PIO state machines.
    * **Pros:** Affordable, dual-core, versatile programming, MicroPython and C/C++ support.
    * **Cons:** Fewer advanced peripherals compared to some 32-bit MCUs, no built-in wireless.

* **Raspberry Pi Pico W:**
    * **Approx. Cost:** $6 - $12
    * **Compute Power:** Moderate to High (Dual-Core RP2040)
    * **Key Features:**  Dual-core RP2040 chip, integrated Wi-Fi 4.
    * **Pros:** Affordable, easy-to-use Wi-Fi.
    * **Cons:** Shared resources may impact performance, Wi-Fi adds to power consumption.

* **Arduino Nano RP2040 Connect:** 
    * **Approx. Cost:** $25 - $35
    * **Compute Power:** Moderate to high (dual-core RP2040)
    * **Key Features:** RP2040, Wi-Fi, Bluetooth, IMU, microphone.
    * **Pros:** Arduino compatibility, integrated sensors and wireless.
    * **Cons:** Larger and more expensive than Pico W, higher power consumption.

### Texas Instruments (TI)

* **Texas Instruments MSP430 Family:**
    * **Approx. Cost:** $2 - $20
    * **Compute Power:** Low to moderate (16-bit)
    * **Key Features:** Ultra-low power consumption, integrated analog peripherals.
    * **Pros:** Excellent power efficiency for battery-powered applications.
    * **Cons:** 16-bit architecture, less powerful than 32-bit MCUs for complex tasks.

### Peripheral Interface Controller (PIC)

* **PIC16:**
    * **Approx. Cost:** $0.50 - $2
    * **Compute Power:** Low
    * **Key Features:** Harvard architecture, compact instruction set.
    * **Pros:** Very low cost, simple to use for basic control.
    * **Cons:** Limited resources, less powerful than other options.

* **PIC18:**
    * **Approx. Cost:** $1 - $5
    * **Compute Power:** Low to moderate
    * **Key Features:** Enhanced PIC architecture, more resources than PIC16.
    * **Pros:** More powerful than PIC16, cost-effective.
    * **Cons:** Smaller community support compared to AVR.


### Espressif (ESP)

* **ESP8266:**
    * **Approx. Cost:** $2 - $8
    * **Compute Power:** Low to Moderate
    * **Key Features:** Wi-Fi, very cost-effective.
    * **Pros:** Extremely affordable for basic Wi-Fi projects.
    * **Cons:** Limited resources, no Bluetooth.

* **ESP32:**
    * **Approx. Cost:** $5 - $20
    * **Compute Power:** Moderate to high (dual-core)
    * **Key Features:** Wi-Fi, Bluetooth, Bluetooth LE, extensive I/O.
    * **Pros:** Powerful, feature-rich, low cost, large community support.
    * **Cons:** Higher power consumption than some dedicated low-power MCUs.

* **ESP32-S2:**
    * **Approx. Cost:** $15 - $25
    * **Compute Power:** Moderate
    * **Key Features:** Wi-Fi, USB-C, often includes LiPo charging.
    * **Pros:** Compact, balanced features and power consumption.
    * **Cons:** Single-core.

* **ESP32-S3:**
    * **Approx. Cost:** $20 - $30
    * **Compute Power:** Moderate to High (Dual-core)
    * **Key Features:** Wi-Fi, Bluetooth 5, camera interface.
    * **Pros:** Increased memory and processing, advanced peripherals.
    * **Cons:** Higher power consumption than ESP32-S2.

### Nordic

* **nRF52832:**
    * **Approx. Cost:** $10 - $20
    * **Compute Power:** Low to moderate
    * **Key Features:** BLE 5, NFC.
    * **Pros:** Affordable entry to BLE development.
    * **Cons:** Fewer features than nRF52840.

* **nRF52840:**
    * **Approx. Cost:** $10 - $30
    * **Compute Power:** Moderate
    * **Key Features:** BLE 5, 802.15.4 (Thread, Zigbee), NFC.
    * **Pros:** Excellent BLE performance, multiple wireless protocols.
    * **Cons:** More complex than simpler BLE solutions.

### STMicroelectronics (STM)

* **STM8 Family:**
    * **Approx. Cost:** $1 - $10
    * **Compute Power:** Low to moderate
    * **Key Features:** Robust ecosystem, various peripherals.
    * **Pros:** Cost-competitive, reliable for industrial applications.
    * **Cons:** Less community support for hobbyist projects than some other options.

* **STM32 Family:**
    * **STM32L Series (Ultra-Low Power):**  
        * **Approx. Cost:** $3 - $20
        * **Compute Power:** Low to moderate (32-bit)
        * **Key Features:** ARM Cortex-M cores optimized for low power, various peripherals.
        * **Pros:** Good balance of power efficiency and processing power, access to the STM32 ecosystem.
        * **Cons:** Can be more complex to use than simpler 8-bit MCUs.
    * **STM32 F/G Series (General Purpose):**
        * **Approx. Cost:** $2 - $50+
        * **Compute Power:** Moderate to High (32-bit)
        * **Key Features:** Wide range of ARM Cortex-M cores (M0 to M7), extensive peripherals, large ecosystem.
        * **Pros:** Scalable performance, excellent community support.
        * **Cons:** Steeper learning curve for beginners.
    * **STM32WB/WL Series (Wireless):**
        * **Approx. Cost:** $5 - $30+
        * **Compute Power:** Moderate to High (32-bit)
        * **Key Features:** ARM Cortex-M cores with integrated wireless (Bluetooth 5, 802.15.4), various peripherals.
        * **Pros:** Good performance, access to STM32 ecosystem, variety of options.
        * **Cons:**  Can be more complex than simpler wireless solutions.
    * **STM32F7/H7 (High-Performance):**
        * **Approx. Cost:** $15 - $50+
        * **Compute Power:** Very High (32-bit)
        * **Key Features:** High-performance ARM Cortex-M7/M4 cores, advanced peripherals, DSP, FPU often included.
        * **Pros:**  High processing power for demanding applications.
        * **Cons:** More complex to use, higher power consumption.


### Microchip

* **Microchip SAM Family (SAMD, etc.):** 
    
    *(Some SAMD MCUs are also good for low-power)*
    * **Approx. Cost:** $5 - $20
    * **Compute Power:** Moderate to high (32-bit)
    * **Key Features:** ARM Cortex-M cores, various peripherals, DMA controller.
    * **Pros:** Wide selection, good performance for 32-bit applications.
    * **Cons:** Ecosystem may not be as large as STM32.

### Specialized Microcontrollers 

*(MCUs with advanced features for specific tasks)*

* **Real-Time Applications** 

    *(For demanding time-sensitive tasks)*

    * **Teensy (PJRC) Family:** *Example: Teensy 4.0*
        * **Approx. Cost:** $20 - $40
        * **Compute Power:** High
        * **Key Features:** Powerful ARM Cortex-M7, high-speed USB, optimized for audio/MIDI, real-time applications.
        * **Pros:** Excellent for audio, USB, and real-time applications requiring very low latency.
        * **Cons:** Higher cost than other 32-bit MCUs.  Not all Teensy boards have dedicated DSP hardware; their strength lies in their speed and timing capabilities.


* **Microcontrollers with DSP/FPU** 

    *(For signal processing and complex math)*

    * **STM32F4 Series (STMicroelectronics):** 
        *Example: STM32F407VG*
        * **Approx. Cost:** $5 - $20
        * **Compute Power:** High (32-bit)
        * **Key Features:**  ARM Cortex-M4 core with FPU and DSP instructions, rich peripherals.
        * **Pros:**  Excellent performance for signal processing, good community support.
        * **Cons:** Can be more complex for beginners than simpler MCUs.


    * **STM32H7 Series (STMicroelectronics):**
        *Example: STM32H743ZI*
        * **Approx. Cost:** $10 - $30+
        * **Compute Power:** Very High (32-bit)
        * **Key Features:**  High-performance ARM Cortex-M7 core with double-precision FPU and DSP, advanced peripherals.
        * **Pros:**  Extremely powerful for demanding signal processing applications.
        * **Cons:**  Higher cost and complexity.

    * **Microchip SAMD51 (Microchip):** 

        *Example: ATSAMD51J20A*
        * **Approx. Cost:** $5 - $15
        * **Compute Power:** Moderate to High (32-bit)
        * **Key Features:** ARM Cortex-M4F core with FPU, suitable for some DSP tasks.
        * **Pros:** Good performance and value.
        * **Cons:** DSP capabilities not as extensive as dedicated DSP processors.
* **Microcontrollers for AI/ML**
  
  *Not many options yet, most use phones or SBC (single board computer)*

  * **Google Coral Dev Board Micro:** (Pre-order?)
      * **Approx. Cost:** $75 - $150 
      * **Compute Power:** High; Dual-core Cortex-M7/M4 + dedicated Edge TPU for ML acceleration.
      * **Key Features:** Integrated camera, microphone, Edge TPU,  64MB RAM, 128MB Flash.
      * **Pros:** Powerful for on-device ML, relatively power-efficient for its performance. Simplifies multimedia hardware design.  Suitable for complex embedded systems.
      * **Cons:** High cost compared to most MCUs. More complex software/integration.  Higher power consumption than simpler, lower-power MCUs.

  
* **AI/ML Frameworks for Microcontrollers:**
    * **TensorFlow Lite:**
        * now called **LiteRT**
        * [Supported MCUs](https://ai.google.dev/edge/litert/microcontrollers/overview) 
        * [Examples](https://experiments.withgoogle.com/collection/tfliteformicrocontrollers)
    * **Other TinyML Frameworks:** 
        * **uTensor:** Lightweight, memory-efficient, supports various platforms.
        * **CMSIS-NN:** ARM's optimized neural network kernels for Cortex-M. Can be used with TensorFlow Lite.
        * **Glow:** Compiler for neural networks, targets various backends including MCUs.

---
Previous: [2. Considerations](2_considerations.md)  |  Next: [4. Beyond Microcontrollers](4_beyond_mcus.md)