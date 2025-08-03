---
title: "Integrations"
date: 2025-01-08
draft: true
type: docs
---

<div style="display: flex; justify-content: flex-start; margin-bottom: 20px;">

[![Latest Release](https://img.shields.io/github/v/release/paclema/iot-postbox?style=for-the-badge&logo=github&label=Latest%20Release)](https://github.com/paclema/iot-postbox/releases/latest)

</div>

Complete integration guides for connecting your IoT-PostBox to popular home automation platforms and services. The device supports both WiFi/MQTT and LoRaWAN connectivity options.

## 🏠 Home Assistant

### MQTT Integration

Add the mailbox sensor to your Home Assistant configuration:

```yaml
sensor:
  - platform: mqtt
    name: "Mailbox Status" 
    state_topic: "mailbox/events"
    json_attributes_topic: "mailbox/telemetry"
    device_class: "motion"
    icon: "mdi:mailbox"

  - platform: mqtt
    name: "Mailbox Battery"
    state_topic: "mailbox/telemetry"
    value_template: "{{ value_json.battery_percentage }}"
    unit_of_measurement: "%"
    device_class: "battery"
    icon: "mdi:battery"
```

### Automation Example

Create automations to handle mailbox events:

```yaml
automation:
  - alias: "Mail Delivered"
    trigger:
      platform: mqtt
      topic: "mailbox/events"
      payload: "mail_delivered"
    action:
      - service: notify.mobile_app
        data:
          title: "📬 Mail Delivered"
          message: "New mail has arrived in your mailbox!"
      
  - alias: "Mail Collected"
    trigger:
      platform: mqtt
      topic: "mailbox/events" 
      payload: "mail_collected"
    action:
      - service: notify.mobile_app
        data:
          title: "📭 Mail Collected"
          message: "Mail has been collected from your mailbox."
```

## 🔄 Node-RED

### Basic Flow Setup

Create Node-RED flows for advanced event processing:

**MQTT Input Node Configuration:**
- Server: Your MQTT broker
- Topic: `mailbox/events`
- Output: Auto-detect (parsed JSON object)

**Function Node Examples:**

```javascript
// Event Processing Function
var event = msg.payload;
var timestamp = new Date().toISOString();

switch(event) {
    case 'mail_delivered':
        msg.payload = {
            event: 'delivery',
            message: 'New mail delivered',
            timestamp: timestamp,
            priority: 'normal'
        };
        break;
    case 'mail_collected':
        msg.payload = {
            event: 'collection', 
            message: 'Mail collected',
            timestamp: timestamp,
            priority: 'low'
        };
        break;
}

return msg;
```

### Notification Flows

**Telegram Bot Integration:**
1. Add Telegram Bot node
2. Configure bot token and chat ID
3. Connect to event processing function

**Email Notifications:**
1. Add Email node
2. Configure SMTP settings
3. Template message with event details

**Push Notifications:**
1. Add HTTP Request node
2. Configure Pushover/Pushbullet API
3. Send formatted notifications


## 📡 LoRaWAN Networks

### The Things Network (TTN)

**Device Registration:**
1. Create application in TTN Console
2. Register end device with DevEUI, AppEUI, AppKey
3. Configure payload formatters for data decoding

**Payload Decoder Example:**

```javascript
function decodeUplink(input) {
  var data = {};
  var bytes = input.bytes;
  
  // Event type (byte 0)
  switch(bytes[0]) {
    case 0x01:
      data.event = "mail_delivered";
      break;
    case 0x02:
      data.event = "mail_collected";
      break;
  }
  
  // Battery voltage (bytes 1-2)
  data.battery_voltage = ((bytes[1] << 8) | bytes[2]) / 1000.0;
  
  // RSSI and other telemetry (bytes 3+)
  data.rssi = bytes[3] - 200;
  
  return {
    data: data,
    warnings: [],
    errors: []
  };
}
```

### Helium Network

**Device Configuration:**
1. Add device to Helium Console
2. Configure integration (HTTP, MQTT, AWS IoT)
3. Set up data flow and alerting

**Integration Webhook Example:**

```json
{
  "app_eui": "your_app_eui",
  "dev_eui": "your_dev_eui", 
  "payload": "base64_encoded_data",
  "decoded": {
    "event": "mail_delivered",
    "battery_voltage": 3.7,
    "rssi": -85
  }
}
```


## 📱 Mobile Applications

### MQTT Dash (Android)

Configure dashboard tiles:

**Event Status Tile:**
- Type: Text
- Topic: `mailbox/events`
- Color: Dynamic based on payload

**Battery Level Tile:**
- Type: Progress Bar
- Topic: `mailbox/telemetry`
- JSON Path: `$.battery_percentage`

### IoT MQTT Panel (iOS)

Setup monitoring panels:

**Connection Settings:**
- Broker: Your MQTT server
- Port: 1883 (or 8883 for SSL)
- Client ID: `mailbox_monitor`

**Widget Configuration:**
- Switch widget for manual testing
- Gauge for battery monitoring
- Log widget for event history


## 🔧 Advanced Integrations

### Webhook Endpoints

Create HTTP endpoints to receive mailbox events:

```python
from flask import Flask, request, jsonify
import json

app = Flask(__name__)

@app.route('/mailbox/webhook', methods=['POST'])
def mailbox_webhook():
    data = request.json
    
    event = data.get('event')
    timestamp = data.get('timestamp')
    
    # Process event
    if event == 'mail_delivered':
        # Send notifications, log to database, etc.
        send_notification(f"Mail delivered at {timestamp}")
    
    return jsonify({'status': 'received'})

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

### Database Logging

Store mailbox events in database:

```sql
CREATE TABLE mailbox_events (
    id SERIAL PRIMARY KEY,
    event_type VARCHAR(50) NOT NULL,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    battery_voltage FLOAT,
    rssi INTEGER,
    raw_data JSON
);
```

### API Integration

RESTful API for mailbox data:

```python
@app.route('/api/mailbox/events', methods=['GET'])
def get_mailbox_events():
    # Query database for recent events
    events = query_events(limit=50)
    return jsonify(events)

@app.route('/api/mailbox/status', methods=['GET']) 
def get_mailbox_status():
    # Return current status and battery level
    status = get_current_status()
    return jsonify(status)
```

---

[![GitHub Repository](https://img.shields.io/badge/View_on-GitHub-181717?style=for-the-badge&logo=github)](https://github.com/paclema/iot-postbox)
