---
title: "Firmware"
date: 2025-09-25
draft: false
type: docs
---

<div style="display: flex; gap: 12px; align-items: center; margin-bottom: 20px;">

<a href="https://github.com/paclema/iot-postbox/releases/latest">
        <img src="https://img.shields.io/github/v/release/paclema/iot-postbox?style=for-the-badge&logo=github&label=Latest%20Release" alt="Latest Release"/>
</a>
</div>

The IoT-PostBox firmware focuses on long battery life, reliable event detection, and hassle‑free integrations. It is built on the WebConfigServer ecosystem, providing a local web UI for configuration, diagnostics, and OTA updates.


## Main Features

- Web configuration portal (no app required)
- Wi‑Fi/MQTT and optional LoRaWAN notifications
- Deep sleep + instant wake on switch events
- Battery and USB (VBUS) voltage monitoring
- OTA updates from the browser
- Works with Home Assistant, Node‑RED, and LoRaWAN networks (TTN, Helium)


## Installation and first boot

**Initial Configuration:**

Firstly you need to configure the [WebConfigServer](https://github.com/paclema/WebConfigServer) settings. This class is responsible for managing the device's network connections (WiFi, MQTT, LoRaWAN, behavior) and other related settings. You can do this on different ways:
1. Editing the `config.json` file under the `data` directory (recommended on first flash).
2. Using the Web UI after flashing the firmware.
3. Using the device FTP server to modify the `config.json` file directly on the device.

**Hardware Setup:**
1. **Power Connection:** Connect USB-Micro-B cable to J4
2. **Boot Mode:** Hold BOOT button while connecting USB for programming mode or Hold BOOT and press RST to reset if the device is already powered. This is only needed for initial flashing or recovery.
3. **Driver Installation:** Install ESP32-S2 USB drivers if needed

**Firmware Upload:**
You can use PlatformIO with VSCode or the pio CLI to build and upload the firmware:
```bash
# Build and upload firmware
pio run -e IoT-PostBox_v1 -t upload

# Upload data partition with WebConfigServer device config
pio run -e IoT-PostBox_v1 -t uploadfs
```

## Event model

The device differentiates two primary event sources:
- Delivery: mail slot/lid opened to insert mail
- Collection: mailbox door opened to collect mail

On wake, the firmware determines the source, publishes a notification, optionally updates until it goes to deep sleep, and returns to deep sleep to save power.


## MQTT integration

The device publishes events and telemetry via MQTT. The next topics and payloads are used:


### Data message

Topic:  `/iot-postbox_v1/<device_id>/data`

Payload:
```json
{
	"wake_up_pin": -1,           // GPIO pin that triggered wakeup
	"boot_counter": 1,           // Number of boots since last reset
	"vcc": 4.267,                // Internal voltage (V)
	"vBat": 4.267,               // Battery voltage (V)
	"vBus": 5.255,               // USB voltage (V)
	"rssi": -31,                 // WiFi signal strength (dBm)
	"GPIO_4_counter": 0,         // Event count for GPIO 4
	"GPIO_4_state": false,       // Current state of GPIO 4
	"GPIO_5_counter": 4,         // Event count for GPIO 5
	"GPIO_5_state": true,        // Current state of GPIO 5
	"PowerStatus": 2,            // Power status code
	"ChargingStatus": 2          // Charging status code
}
```


## Using IoT-PostBox v1 board in your own project

To build and upload your own firmware project with PlatformIO and the Arduino‑ESP32 framework to this board, add the custom board definition files to your project so that the IoT‑PostBox v1 board can be recognized as a PlatformIO board target. You can download these files from the [IoT‑PostBox repository](https://github.com/paclema/iot-postbox). In the root of your project, create a `boards` directory and place at least:

   - The custom PlatformIO board JSON at [`boards/iot-postbox_v1.json`](https://github.com/paclema/iot-postbox/blob/master/boards/iot-postbox_v1.json)
   - The Arduino variant files under the folder [`boards/variants/iot-postbox_v1/`](https://github.com/paclema/iot-postbox/tree/master/boards/variants) containing the pin definitions and variant initialization functions.
   - And the partition tables from [`board_partitions/esp32/iotpostboxv1_16MB.csv`](https://github.com/paclema/iot-postbox/blob/master/board_partitions/esp32/iotpostboxv1_16MB.csv) if you want to use the same layout.

As a summary, your project structure should include now the following files and folders:
```
your-project/
├─ boards/
│  ├─ iot-postbox_v1.json
│  └─ variants/
│     └─ iot-postbox_v1/
│        ├─ pins_arduino.h
│        └─ variant.cpp
├─ board_partitions/
│  └─ esp32/
│     └─ iotpostboxv1_16MB.csv
└─ platformio.ini
```

In this case, your `platformio.ini` could contain the following environment target:
```ini
[env:IoT-PostBox_v1]
platform = https://github.com/pioarduino/platform-espressif32.git#develop
; or the stable version:
; platform = https://github.com/pioarduino/platform-espressif32/releases/download/stable/platform-espressif32.zip
framework = arduino

board = iot-postbox_v1
board_build.variants_dir = boards/variants
board_build.partitions = ./board_partitions/esp32/iotpostboxv1_16MB.csv
```
