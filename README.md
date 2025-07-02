# ESP8266 Rain Forecaster

A compact, battery-powered rain forecast display built with the ESP8266-12E. Designed to run efficiently on a 350mAh LiPo battery, this device fetches weather data from the internet and displays a simple, at-a-glance rain forecast on a 0.96" OLED screen.

## ☁️ Project Goal

This project aims to provide a quick and easy way to check if it's going to rain — perfect for keeping by the door or kitchen. The device stays in deep sleep to conserve battery and wakes up only when a button is pressed.

## 🌧️ Features

- 📡 **WiFi Weather Fetching**  
  Connects to an online weather API to get real-time rain forecast data.

- 🖥️ **OLED Display**  
  Clear output on a 128x64 SSD1306 I2C screen (e.g., "Rain Likely", "No Rain Today", etc.).

- 🔋 **Low Power Operation**  
  Runs on a 350mAh LiPo battery with TP4056 charging circuit. Uses deep sleep to extend battery life.

- 🔘 **Button-Wake System**  
  Wakes from deep sleep when a pushbutton is pressed.

- 🔄 **Future OTA Support** *(optional)*  
  Can be extended to support OTA firmware updates.

## 🧰 Hardware Components

| Component           | Description                              |
|--------------------|------------------------------------------|
| ESP8266-12E         | WiFi microcontroller module              |
| SSD1306 OLED        | 128x64 I2C display                       |
| TP4056 Charger      | LiPo charging module with protection     |
| 350mAh LiPo         | Rechargeable battery                     |
| Pushbutton          | To wake the device from deep sleep       |
| Resistors/Wires     | For pull-up/down and basic wiring        |

## 🔋 Power Management

- The ESP8266 stays in **deep sleep** to conserve battery.
- A pushbutton connects `RST` to `GND` to reset and wake the chip.
- Total consumption < 1mA while sleeping.

## 🚀 Setup Instructions

1. **Flash the code** to the ESP8266 using Arduino IDE or PlatformIO.
2. **Connect to WiFi** and fetch weather using a service like [OpenWeatherMap](https://openweathermap.org/api).
3. **Connect the button** between `RST` and GND for wake-up.
4. **Wire up the display** using I2C (`SDA` and `SCL`).
5. **Power the board** from a 3.7V LiPo via TP4056 (OUT+ to ESP VIN).


## 🔧 Libraries Used

- `ESP8266WiFi`
- `ArduinoJson`
- `Adafruit_GFX`
- `Adafruit_SSD1306`
- `HTTPClient` / `WiFiClientSecure` (if using HTTPS)

## 💡 Example Output


☀️ No Rain Expected Today

🌧️ Light Rain in Afternoon

⚠️ Heavy Rain Incoming



## 📝 License

This project is open-source and released under the MIT License.

---

Built with love and practicality – a simple weather helper for daily life.

