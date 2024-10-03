# Beyond Microcontrollers

*updated 2024*

This section briefly covers alternatives to MCUs: programmable logic, application processors, single-board computers (SBCs), and specialized AI/ML accelerators at the edge.  These offer greater power/flexibility but increased cost and complexity. Consider them for projects needing substantial processing, hardware acceleration, an OS, or on-device machine learning.


### Programmable Logic & Highly Configurable Devices:

* **PSoC (Programmable System-on-Chip) - Infineon:**
    * **Approx. Cost:** $5 - $30+ (depending on features and complexity)
    * **Compute Power:** Moderate to High (configurable architecture)
    * **Key Features:** Highly configurable analog and digital blocks, allowing for custom peripheral creation. Suited for complex systems and signal processing. Programmed using PSoC Creator.  Offers a blend of MCU functionality with FPGA-like flexibility.
    * **Example Applications:** Industrial control, automotive systems, medical devices, consumer electronics where flexibility and integrated analog capabilities are essential.

* **FPGA (Field Programmable Gate Arrays):**
    * **Approx. Cost:** $10 - $1000+ (wide range based on complexity, resources, and features).
    * **Compute Power:** Very High (parallel processing, custom hardware).
    * **Key Features:**  Highly customizable hardware offering true parallel processing capabilities. Enables the implementation of complex logic circuits and custom hardware designs. Typically used in high-performance or specialized applications requiring hardware acceleration. Requires specialized design tools and HDLs (VHDL/Verilog).
    * **Example Applications:** High-performance computing, specialized applications, hardware acceleration (e.g., image/signal processing, networking, aerospace, custom protocols).


### Application Processors (High-end SoCs - Not Typically Standalone MCUs):

* **Qualcomm Snapdragon - Qualcomm:**
    * **Approx. Cost:** Varies widely ($20 - $200+).
    * **Compute Power:** Very high (multi-core processors, GPUs, specialized hardware).
    * **Key Features:** Integrated cellular, Wi-Fi, Bluetooth, GPS, and other mobile-specific features.  Highly integrated, complex SoCs.
    * **Example Applications:** Smartphones, tablets, laptops (running complex OSes and apps).  Generally not suitable for typical standalone embedded projects due to cost, complexity, and power requirements.
  

### General Purpose Single-Board Computers (SBCs):

* **Raspberry Pi 5:**
    * **Approx. Cost:** $60 - $80+ (depending on RAM and configuration).
    * **Compute Power:** High (Quad-core ARM Cortex-A76 processor). Significantly faster than previous generations.
    * **Key Features:** Powerful processor, improved graphics capabilities, multiple RAM options (up to 8GB), dual display output, PoE+ support, diverse connectivity (USB3, Gigabit Ethernet).  Large community, extensive documentation, runs Raspberry Pi OS (based on Debian).
    * **Example Applications:** Desktop computing, media centers, retro gaming, robotics, home automation, education, embedded systems requiring significant processing and graphical capabilities.

* **Older Raspberry Pi Models (2/3/4):**  While superseded by the Pi 5, these remain cost-effective options, especially where the full power of the Pi 5 isn't required. They offer reduced performance and may lack features like dual 4K display and PoE+.

    * **Raspberry Pi 4** ($35 - $55):  A good balance of performance and price, but slower than the Pi 5.
    * **Raspberry Pi 3** ($25 - $40): Suitable for less demanding projects. Noticeably slower than the Pi 4/5.
    * **Raspberry Pi 2** ($20 - $35):  Best for basic projects. Significantly slower than later models.
  
* **Raspberry Pi Zero 2 W:**
    * **Approx. Cost:** $15.
    * **Compute Power:** Moderate (Quad-core ARM Cortex-A53 processor).  A significant upgrade over the original Pi Zero, but less powerful than the Raspberry Pi 4/5.
    * **Key Features:**  Compact size, low power consumption, Wi-Fi and Bluetooth connectivity. Runs Raspberry Pi OS Lite. Excellent for embedded projects and where space and power are limited.
    * **Example Applications:**  Portable computing, robotics, IoT devices, headless servers, projects requiring small form factor.

* **BeagleBone Family:**
    * **Approx. Cost:** $55 - $250+ (depending on the model).
    * **Compute Power:** Moderate to High (usually single-core ARM processors, but some newer models have multi-core).
    * **Key Features:** Open-source hardware and software, extensive community support, real-time processing capabilities (PRU-ICSS), lots of GPIO, good for interfacing with external hardware. Runs Linux.
    * **Example Applications:** Robotics, industrial control, data acquisition, networking appliances, custom embedded Linux systems.


### AI/ML Accelerated Single-Board Computers (Edge Computing):

* **Google Coral Dev Board:**
    * **Approx. Cost:** $50 - $150+
    * **Compute Power:** High (Edge TPU for TensorFlow Lite).
    * **Key Features:** Edge TPU coprocessor for low-power inferencing.  Various form factors (USB, Dev Board, SoM). Dev Board uses NXP i.MX 8M SoC (Cortex-A53, Cortex-M4F) and runs Debian Linux.
    * **Example Applications:** Edge AI, image/object recognition, voice control, on-device ML.

* **NVIDIA Jetson Family:**
    * **Approx. Cost:** $50 - $1000+
    * **Compute Power:** High to Very High (GPU, AI-focused).
    * **Key Features:** Powerful NVIDIA GPUs, supports CUDA, TensorFlow, PyTorch, etc.  Scalable platform (Nano to AGX Orin). Runs Linux for Tegra (L4T).
    * **Example Applications:** Robotics, autonomous vehicles, AI drones, industrial automation, demanding edge AI.

* **Sipeed MAix:**
    * **Approx. Cost:** $15 - $50
    * **Compute Power:** Moderate (K210 KPU).
    * **Key Features:** Cost-effective K210 KPU, supports MicroPython, C/C++, TensorFlow Lite. Available as modules/boards. Often used with MaixPy IDE.
    * **Example Applications:** Entry-level AI, education, robotics, object recognition, budget-friendly edge AI.


**Considerations for AI/ML Projects:**

* **Processing Power:** Evaluate CPU, AI accelerators (TPUs, KPUs), and memory bandwidth.
* **Memory:** Ensure sufficient Flash and RAM for models and data.
* **Power Consumption:** Consider project's power budget and MCU efficiency.
* **Software:** Look for support for AI/ML frameworks (TensorFlow Lite, PyTorch), libraries, pre-trained models, and example code.
* **Real-time Performance:**  Assess processing speed and latency for real-time inference.
* **Connectivity:** Consider Wi-Fi, Bluetooth, or other communication interfaces.
* **Development Ecosystem:**  Prioritize good documentation, community support, and debugging tools. 

---
Previous: [3. Options](3_options.md)  |  Next: [5. Examples](5_examples.md)