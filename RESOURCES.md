# Project Resources & Downloads

## Required Software Downloads

### WLED Firmware
- **Main Repository**: [WLED GitHub](https://github.com/Aircoookie/WLED)
- **Latest Release**: [Download Firmware](https://github.com/Aircoookie/WLED/releases/latest)
- **Web Installer**: [WLED Web Installer](https://install.wled.me/) (Easiest installation method)

### Mobile Apps

#### Android
- **Google Play Store**: [WLED App](https://play.google.com/store/apps/details?id=com.aircoookie.WLED)
- **Direct APK Download**: [GitHub Releases](https://github.com/Aircoookie/WLED/releases) (Look for `.apk` files)
- **F-Droid**: [WLED on F-Droid](https://f-droid.org/packages/com.aircoookie.WLED/) (Open source app store)

#### iOS
- **App Store**: [WLED for iOS](https://apps.apple.com/app/wled/id1475695033)

### Development Tools

#### For ESP32/ESP8266 Programming
- **Arduino IDE**: [Download](https://www.arduino.cc/en/software)
- **PlatformIO**: [Download](https://platformio.org/install)
- **ESP Flash Tool**: [Espressif Download](https://www.espressif.com/en/support/download/other-tools)

#### For PCB Design (KiCad)
- **KiCad EDA**: [Download](https://www.kicad.org/download/)
- **Version Used**: KiCad 7.x or later recommended

## Useful Links

### Documentation
- **WLED Wiki**: [https://kno.wled.ge/](https://kno.wled.ge/)
- **WLED API Documentation**: [JSON API](https://kno.wled.ge/interfaces/json-api/)
- **ESP32 Documentation**: [Espressif Docs](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/)

### Community & Support
- **WLED Discord**: [Join Server](https://discord.gg/KuqP7NE)
- **WLED Reddit**: [r/WLED](https://www.reddit.com/r/WLED/)
- **GitHub Issues**: [Report Bugs](https://github.com/Aircoookie/WLED/issues)

### Hardware Suppliers
- **LED Rings**: Search for "WS2812B 60 LED Ring" on:
  - Amazon
  - AliExpress
  - Adafruit
  - SparkFun
- **ESP32/ESP8266**: Available from most electronics suppliers
- **Illuminated Buttons**: Search for "16mm illuminated momentary switch"

## Installation Quick Start

### 1. Flash WLED (Easiest Method)
1. Visit [install.wled.me](https://install.wled.me/)
2. Connect your ESP32/ESP8266 via USB
3. Click "Install" and follow the web installer

### 2. Install Mobile App
- **Android**: Install from Play Store or download APK from GitHub releases
- **iOS**: Install from App Store

### 3. Hardware Assembly
- Follow the wiring diagram in `HARDWARE.md`
- Use the PCB files in the `pcb/` folder for custom boards

## Version Compatibility

| Component | Minimum Version | Recommended |
|-----------|----------------|-------------|
| WLED Firmware | 0.13.0 | Latest stable |
| Mobile App | 1.0.0 | Latest |
| KiCad | 6.0 | 7.0+ |
| Arduino IDE | 1.8.0 | 2.0+ |

## License Information

- **WLED**: MIT License
- **This Project**: Open source (see LICENSE file)
- **Mobile Apps**: Follow respective app store terms