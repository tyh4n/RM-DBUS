# RM_DBUS Arduino Library

A lightweight Arduino library for encoding and transmitting DJI DBUS protocol signals (Robomaster format). Designed for ESP32 and other Arduino-compatible boards.

## Key Features

- Simple API for sending DBUS control signals
- Supports all standard DBUS channels (4 RC, 2 switches, mouse, keyboard)
- Optimized for ESP32 but works with other Arduino boards
- Handles all DBUS protocol formatting automatically

## Typical Use Cases

- Converting gamepad/joystick inputs to DBUS signals
- Creating custom wireless controllers for DJI systems
- Robotics projects requiring DBUS protocol

## Getting Started

1. Install via Arduino Library Manager
2. Include in your sketch: `#include <RM_DBUS.h>`
3. Initialize with `DBUS.begin()`
4. Set channel values with `DBUS.write_channel()`
5. Transmit with `DBUS.update()` and `DBUS.send()`

## Example

```cpp
#include <RM_DBUS.h>

RM_DBUS DBUS;

void setup() {
  DBUS.begin();
}

void loop() {
  DBUS.write_channel(1, 1024); // Set throttle
  DBUS.update();
  DBUS.send();
  delay(10);
}
```

## License

MIT License - Free for personal and commercial use