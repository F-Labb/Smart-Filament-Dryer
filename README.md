# Smart-Filament-Dryer
**Creality Dry Box 2.0 — Smart ESPHome Upgrade**

**WARNING! This configuration is under development and may not work correctly.**

**What already works:**
1. Initialization and network
2. Fan, heater, and I2C bus
3. Fully functional setup via the Home Assistant interface

**What's not working:**
1. The screen. The graphical interface is not fully implemented.
2. Switching between "Humidity" and "Temperature" modes. I plan to add a time-based mode, like the factory Creality system.

This project is a complete replacement of the Creality Dry Box 2.0 filament dryer's stock electronics with an ESP32-C6 controller. This modification preserves the original heating element and fan, while adding modern control via Home Assistant and Thread protocol support.

**What's inside**

• Base: Case, heating element, and fan from the Creality Dry Box 2.0.

• Brain: ESP32-C6 (with OpenThread).

• Sensor: AHT20 instead of the stock one (higher accuracy and stability).

• Controls: Rotary encoder with a button for full local control without a smartphone / pc.

• Display: OLED (I2C) support for displaying current parameters and settings menu.

**Key improvements over the stock model**

• Smart Fan Control: The fan runs at 100% during active heating and switches to 50% (PWM) when the target temperature is reached, maintaining convection without excessive noise.

• Hysteresis: Heating logic with a 5°C threshold has been implemented, which protects the relay/power switch from frequent switching.

• Home Assistant integration: Full control via Wi-Fi/Thread, humidity and temperature graphs, and drying completion notifications.

• Customizable interface: Adjust screen brightness and shutdown timeout directly from the menu.

**Main pins:**

    Heater    >>  GPIO8
    Fan PWM   >>  GPIO7
    I2C SDA   >>  GPIO19
    I2C SCL   >>  GPIO20
    Enc A     >>  GPIO2
    Enc B     >>  GPIO1
    Enc btn   >>  GPIO3
