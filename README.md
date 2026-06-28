# Mini UPS LX-2BUPS Monitor using Wemos D1, INA219 & OLED 128x32

This project is an IoT-based power monitoring system for the **LX-2BUPS Mini UPS** module. Utilizing a **Wemos D1 (ESP8266)**, the system measures power parameters such as voltage, current, and power consumption via the **INA219** sensor and displays the real-time data on a compact **OLED 128x32** display.

---

## 🚀 Features

* **Real-time Power Telemetry:** Monitors bus voltage (V), shunt current (mA), and power consumption (mW) from the LX-2BUPS.
* **Compact Display UI:** Clean and readable layout optimized for 128x32 I2C OLED screens.
* **I2C Efficiency:** Both the sensor and the display share the same I2C bus, minimizing wire clutter and saving GPIO pins on the Wemos D1.

---

## 🛠️ Hardware Requirements

| Component | Description | Quantity |
| :--- | :--- | :--- |
| **Wemos D1 Mini / R1** | ESP8266 Development Board | 1 |
| **LX-2BUPS Module** | Mini Uninterruptible Power Supply (UPS) | 1 |
| **INA219 Sensor** | High-side Current and Voltage Monitor (I2C) | 1 |
| **OLED 128x32** | SSD1306 I2C Display Module | 1 |

---

## 🔌 Wiring & Pinout

Since both the INA219 and OLED display utilize the **I2C protocol**, they share the same clock (SCL) and data (SDA) lines from the Wemos D1.

### I2C Connections (Shared Bus)
* **Wemos D1 D1 (SCL)** ➡️ INA219 SCL ➡️ OLED SCL
* **Wemos D1 D2 (SDA)** ➡️ INA219 SDA ➡️ OLED SDA
* **Wemos D1 3.3V** ➡️ VCC (INA219 & OLED)
* **Wemos D1 GND** ➡️ GND (INA219 & OLED)

### Power Measurement (INA219 to LX-2BUPS)
* **INA219 Vin+** ➡️ LX-2BUPS Output / Battery Positive (Depending on what you want to measure)
* **INA219 Vin-** ➡️ Load / Device Input

---

## 💻 Software & Libraries

To compile the firmware using the Arduino IDE or PlatformIO, you will need to install the following libraries:

1.  **Adafruit INA219** (by Adafruit) - For current and voltage sensing.
2.  **Adafruit SSD1306** & **Adafruit GFX Library** - For driving the 128x32 OLED screen.

---

## 🛠️ Setup and Installation

1.  Clone this repository to your local machine:
    ```bash
    git clone [https://github.com/RizkyPratamaRusdiana/Mini-UPS-LX-2BUPS-Wemos.git](https://github.com/RizkyPratamaRusdiana/Mini-UPS-LX-2BUPS-Wemos.git)
    ```
2.  Open the project folder in **Arduino IDE** or **VS Code (PlatformIO)**.
3.  Install the required libraries via the Library Manager.
4.  Select **Wemos D1 R1** or **LOLIN(WEMOS) D1 mini** as your target board.
5.  Compile and Upload the code.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
