---
title: "USBtoUART"
date: 2025-07-25
# lastmod: 2025-07-25
draft: false
type: docs
titleHide: true    # Oculta el título
---
<!-- {{< github-readme user="paclema" repo="USBtoUART" >}} -->

<div style="display: flex; justify-content: flex-start; margin-bottom: 20px;">

[![Latest Release](https://img.shields.io/github/v/release/paclema/USBtoUART?style=for-the-badge&logo=github&label=Latest%20Release)](https://github.com/paclema/USBtoUART/releases/latest)

</div>

A compact USB-C to UART bridge board based on the Silicon Labs CP2102N chip and featuring a dedicated XC6220B331ER LDO regulator, designed for debugging, programming, and serial communication with microcontrollers and embedded systems.

**Why this board?** Unlike typical USB-to-UART bridges, this board features a dedicated LDO regulator that supplies up to 1A at 3.3V, ensuring stable power delivery to the target board while providing reliable data communication.

<p align="center" width="100%">
  <a href="/projects/usbtouart/_DSC3896.JPG">
    <img src="/projects/usbtouart/_DSC3896.JPG" alt="USBtoUART" width="600"/>
  </a>
</p>

| Top View | 3D Rendering | Bottom View |
|:--------:|:------------:|:-----------:|
| [![USBtoUART Top View](/projects/usbtouart/USBtoUART_top.png)](/projects/usbtouart/USBtoUART_top.png) | [![USBtoUART 3D View](/projects/usbtouart/USBtoUART.png)](/projects/usbtouart/USBtoUART.png) | [![USBtoUART Bottom View](/projects/usbtouart/USBtoUART_bottom.png)](/projects/usbtouart/USBtoUART_bottom.png) |

## Features

- **USB-C Connector**: Modern USB-C interface for reliable power and data connection (USB 2.0)
- **CP2102N Bridge Chip**: High-performance USB to UART bridge controller (up to 3 Mbaud)
- **High-Power LDO**: Dedicated XC6220B331ER regulator providing up to 1A at 3.3V for connected devices (the CP2102N operates directly from USB 5V)
- **Status LEDs**: Visual indicators for Power (PWR), Transmit (TX), and Receive (RX)
- **UART Breakout**: Dedicated 6-pin UART connector with standard pinout
- **Extended GPIO Access & Breadboard Compatibility**: Exposes extra CP2102N GPIO pins via dual 10-pin headers, designed for direct insertion into standard breadboards to simplify prototyping and expand control options
- **Auto-Reset Circuit**: Dual MOSFET transistor circuit enables automatic reset of the connected microcontroller during programming
- **Compact Form Factor**: Optimized 2-layer PCB layout with surface-mount components (0805 package size)

## Pin Configuration

### UART Connector (J3)
> **Note:** In ESP8266 and ESP32 family chips, their GPIO0 pin is used to control boot mode (e.g., entering flash mode for programming). The labeled GPIO0 pin in this connector is intended to be connected to the target chip's GPIO0 pin to control the boot mode. This usage may not apply to other target chips, so verify your specific hardware requirements.
> 
| Pin | Function | Description |
|-----|----------|-------------|
| 1   | 3V3      | 3.3V Power Output |
| 2   | EN       | Enable/Reset |
| 3   | GPIO0    | Boot mode control |
| 4   | TXD      | UART Transmit |
| 5   | RXD      | UART Receive |
| 6   | GND      | Ground |

### Extended Port Connectors
- 10-pin male headers providing access to power rails (3.3V, 5V, GND) and CP2102N GPIO signals
- Enable powering and controlling external circuits directly from the board
- Compatible with standard breadboard and prototyping setups
- Standard 2.54mm (0.1") pin spacing

#### PORT1 (J2)
| Pin | Function | Description |
|-----|----------|-------------|
| 1   | GPIO.6   | CP2102N GPIO 6 |
| 2   | GPIO.0   | CP2102N GPIO 0 |
| 3   | GPIO.1   | CP2102N GPIO 1 |
| 4   | GPIO.2   | CP2102N GPIO 2 |
| 5   | GPIO.3   | CP2102N GPIO 3 |
| 6   | CHR0     | Battery Charging Detection 0 |
| 7   | CHR1     | Battery Charging Detection 1 |
| 8   | CHREN    | Battery Charging Enable |
| 9   | SUSPEND  | USB Suspend State |
| 10  | /SUSPEND | USB Suspend State (Inverted) |

#### PORT2 (J4)
| Pin | Function | Description |
|-----|----------|-------------|
| 1   | +5V      | 5V Power Output (from USB connector) |
| 2   | GPIO.5   | CP2102N GPIO 5 |
| 3   | GPIO.4   | CP2102N GPIO 4 |
| 4   | RTS      | Request To Send |
| 5   | CTS      | Clear To Send |
| 6   | DSR      | Data Set Ready |
| 7   | DTR      | Data Terminal Ready |
| 8   | DCD      | Data Carrier Detect |
| 9   | CLK      | Clock output |
| 10  | GND      | Ground |

## Interactive Bill of Materials 
<!-- [Open in full screen](/projects/usbtouart/ibom.html) -->

> [!NOTE]
> Explore components to view details and placement information. [View Fullscreen 🔍](/projects/usbtouart/ibom.html)


<br>
<div style="width: 100%; height: 600px; overflow: hidden; border: 1px solid #ddd;">
  <iframe src="/projects/usbtouart/ibom.html" 
          width="100%" 
          height="600px" 
          frameborder="0"
          style="transform: scale(0.75); transform-origin: 0 0; width: 133%; height: 133%;">
  </iframe>
</div>

## Technical Documentation

{{< tabs items="Schematic,PCB Top,PCB Bottom,All Layers" >}}
{{< tab >}}
<iframe src="/projects/usbtouart/USBtoUART_sch.pdf#navpanes=0" 
        width="100%" 
        height="600px" 
        style="border: 1px solid #ddd;">
</iframe>
{{< /tab >}}

{{< tab >}}
<iframe src="/projects/usbtouart/USBtoUART_brd_top.pdf#navpanes=0" 
        width="100%" 
        height="600px" 
        style="border: 1px solid #ddd;">
</iframe>
{{< /tab >}}

{{< tab >}}
<iframe src="/projects/usbtouart/USBtoUART_brd_bottom.pdf#navpanes=0" 
        width="100%" 
        height="600px" 
        style="border: 1px solid #ddd;">
</iframe>
{{< /tab >}}

{{< tab >}}
<iframe src="/projects/usbtouart/USBtoUART_brd_layers.pdf#navpanes=0" 
        width="100%" 
        height="600px" 
        style="border: 1px solid #ddd;">
</iframe>
{{< /tab >}}

{{< /tabs >}}


## 3D Model

> [!NOTE]
> Explore the 3D model interactively. Use mouse to rotate, zoom and pan. [View Fullscreen 🔍](/projects/usbtouart/viewer.html)

<br>

<iframe src="/projects/usbtouart/viewer.html" 
        width="100%" 
        height="600px" 
        style="border: 1px solid #ddd; border-radius: 8px;">
</iframe>

---

[![GitHub Repository](https://img.shields.io/badge/View_on-GitHub-181717?style=for-the-badge&logo=github)](https://github.com/paclema/USBtoUART)