# InGraw Runtime

**InGraw Runtime** is a lightweight, modular, and fully configurable runtime environment for the **InGraw Core 5** platform.  
It is not a traditional operating system: Linux functions solely as a **low-level execution engine**, while end users interact exclusively with their own system without seeing Linux boot logs, terminals, or default shell environments.

InGraw Runtime is designed to enable developers, makers, and engineers to rapidly prototype, test, and deploy custom applications or hardware control systems in a **safe sandboxed environment**, without modifying SPI flash or onboard storage until explicitly desired.

---

## Table of Contents

- [Key Features](#key-features)
- [Boot Flow](#boot-flow)
- [Benefits](#benefits)
- [Supported Use Cases](#supported-use-cases)
- [License](#license)

---

## Key Features

- **Invisible Linux Engine**
  - The kernel and initramfs reside on SPI flash, but by default do not produce console output or GUI.
  - No automatic login, terminal, or system messages are presented.

- **Flexible System Sources**
  - User systems can be loaded from eMMC, SD card, or via USB OTG live boot.
  - Sandboxed execution ensures that testing new applications does not modify persistent storage.

- **Block-Based Editor**
  - Visual, Scratch/Blockly-inspired editor for creating full systems.
  - Supports hardware I/O (GPIO, SPI, UART, I2C, CAN), timers, USB modules, and displays.
  - Generates device tree overlays, service configurations, and runtime mappings for InGraw Core 5.

- **Live USB OTG Testing**
  - Boot and test systems without flashing the device.
  - Immediate reset capabilities after testing.

- **Universal Applicability**
  - Enables creation of systems for 3D printers, CNC machines, industrial panels, consoles, and IoT devices.
  - Provides a full “OS-like” user experience tailored to the user’s application while abstracting away Linux.

---

## Boot Flow

1. **Power On InGraw Core 5**  
2. **Minimal U-Boot**
   - No automatic boot; waits for user system input.
   - Supports SPI flash, eMMC, SD card, and USB OTG boot.
3. **Kernel + Initramfs**
   - Loaded into RAM only.
   - Does not initialize framebuffer or terminal by default.
   - Provides sandboxed environment for runtime applications.
4. **User System Load**
   - Loaded from eMMC, SD card, or USB OTG.
   - Runtime applies IO mappings, timers, and modules based on editor-generated configuration.
5. **User Application Execution**
   - Runs in full sandboxed environment.
   - Presents custom UI, HMI, or control panels.
   - No shell, logs, or background Linux services visible to the user.

---

## Benefits

- **Safe Sandboxed Environment** – test new systems without affecting persistent storage.
- **Rapid System Prototyping** – visual editor abstracts low-level OS and hardware details.
- **Flexible Deployment** – supports SD, eMMC, and live USB OTG boot.
- **Professional User Experience** – system behaves like a complete OS while remaining fully user-defined.
- **Modular and Extensible** – new blocks, drivers, and modules can be added without kernel recompilation.

---

## Supported Use Cases

- 3D printer and CNC machine controllers
- Industrial HMI and control panels
- Gaming or console systems
- IoT and smart home devices
- Rapid prototyping of embedded systems and custom hardware

---

## License

> **IMPORTANT:** InGraw Runtime is the intellectual property of **InGraw Co.**  
> At this time, the project **is not available for public use**. No part of the software may be used, copied, or redistributed without explicit permission from InGraw Co.  
> Future licensing terms will be determined once the project reaches a stable public release.
