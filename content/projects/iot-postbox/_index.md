---
title: "IoT-PostBox"
date: 2025-08-03
draft: false
type: docs
titleHide: true    # Oculta el título
---

<div style="display: flex; justify-content: flex-start; margin-bottom: 20px;">

[![Latest Release](https://img.shields.io/github/v/release/paclema/iot-postbox?style=for-the-badge&logo=github&label=Latest%20Release)](https://github.com/paclema/iot-postbox/releases/latest)

</div>

**Never miss a delivery again.** Transform your ordinary mailbox into a smart notification system that instantly alerts you when mail arrives or is collected. This battery-powered IoT sensor runs for months on a single charge and seamlessly integrates with your home automation setup.

<p align="center" width="100%">
  <a href="/projects/iot-postbox/v1.x/_DSC4963.jpg">
    <img src="/projects/iot-postbox/v1.x/_DSC4963.jpg" alt="IoT-PostBox v1.2" width="600"/>
  </a>
</p>

## How it Works

**Installation:** The device is installed inside the mailbox with switches positioned to detect when the mail slot or door is opened.

**Operation Flow:**
1. **Detection**: Switch sensors detect when the mail slot opens (delivery) or mailbox door opens (collection)
2. **Processing**: Device wakes from low-power sleep, identifies the trigger source, and processes the event
3. **Notification**: Sends wireless notification via WiFi/MQTT or LoRaWAN to your home system
4. **Sleep**: Returns to ultra-low power mode to preserve battery life

**Benefits:**
- Real-time delivery and collection notifications
- Know when mail has been collected  
- Monitor mailbox activity remotely
- Integrate mailbox status into home automation systems

## Project Evolution

{{% steps %}}

### Early Development (v0.x)
- ESP8266-based designs with basic functionality
- WiFi connectivity with MQTT messaging
- Simple power management and battery charging
- Proof of concept and field testing

### Current Generation (v1.x)
- ESP32-S2 based platform with enhanced capabilities
- **Dual connectivity**: WiFi for local networks + LoRaWAN for wide-area coverage
- **Advanced power management**: Deep sleep with intelligent wake-up
- **Native USB programming**: No external adapters needed
- **Improved power architecture**: Load sharing circuit (USB/battery) with dual LDO design
- **External antenna support**: uFL connectors for WiFi and LoRaWAN antennas
- **Enhanced battery monitoring**: Dedicated ADC sensing for VBAT and VBUS voltage
{{% /steps %}}

## System Components

**📱 Smart Firmware**   
Built on the [WebConfigServer](https://github.com/paclema/WebConfigServer) ecosystem for easy configuration and monitoring. Includes web dashboard, OTA updates, and extensive customization options.

{{< cards cols="2" >}}
{{< card link="./firmware" title="Firmware Documentation" icon="code">}}
{{< /cards >}}

**⚡ Custom Hardware**  
Purpose-built PCBs with integrated battery management, charging systems, and optimized power consumption. Available in two generations:

{{< cards cols="2" >}}
{{< card link="./v1.x" title="IoT-PostBox v1.x (ESP32-S2)" icon="chip" tag="Current" tagType="info">}} 
{{< card link="./v0.x" title="IoT-PostBox v0.x (ESP8266)" icon="chip" tag="Legacy" tagType="warning">}} 
{{< /cards >}}

**🔌 Easy Integration**   
Works with popular home automation platforms like Home Assistant, Node-RED, and LoRaWAN networks (TTN, Helium).

{{< cards cols="2" >}}
{{< card link="./integrations" title="Integrations guides" icon="cloud">}}
{{< /cards >}}

<br>

---

[![GitHub Repository](https://img.shields.io/badge/View_on-GitHub-181717?style=for-the-badge&logo=github)](https://github.com/paclema/iot-postbox)
