# IoT Analog Clock with Illuminated Control

A Wi-Fi connected wall clock that uses a 60-LED WS2812B ring to display time like traditional analog clock hands. Built with ESP32/ESP8266 running WLED firmware.

## Features

- **Analog Time Display**: LED ring shows hour, minute, and second hands
- **Wi-Fi Connected**: Automatic time sync via NTP
- **Mode Toggle**: Physical illuminated button switches between clock and party modes
- **Web Interface**: Full WLED web control for effects and settings
- **Mobile App**: Control via official WLED mobile apps

## Demo Videos

- **Clock Mode**: `lamp2.0_clockMode.mp4` - See the LED ring displaying time as analog clock hands
- **Effect Mode**: `lamp2.0_effectMode.mp4` - Watch the decorative lighting effects in action

## What's Included

- **PCB Design**: KiCad files for custom control board
- **3D Models**: STL files for case components
- **Laser Cuts**: DXF/SVG files for mounting plates
- **Gerber Files**: Ready for PCB manufacturing
- **Documentation**: Complete build and setup guides

## Quick Start

1. **Hardware**: Follow `HARDWARE.md` for component list and wiring
2. **Software**: See `SOFTWARE.md` for WLED setup and configuration
3. **Resources**: Check `RESOURCES.md` for download links and tools

## Project Structure

```
├── pcb/                    # KiCad PCB design files
├── 3dPrints/              # STL files for 3D printed parts
├── laserCuts/             # DXF/SVG files for laser cutting
├── gerber.zip             # PCB manufacturing files
├── lamp2.0_clockMode.mp4  # Demo video - Clock mode
├── lamp2.0_effectMode.mp4 # Demo video - Effect mode
├── HARDWARE.md            # Component list and assembly guide
├── SOFTWARE.md            # WLED configuration and setup
└── RESOURCES.md           # Download links and resources
```

## How It Works

The clock uses a 60-LED ring where each LED represents a position on a traditional clock face. The ESP32/ESP8266 connects to Wi-Fi, fetches accurate time via NTP, and illuminates LEDs to show:

- **Hour Hand**: Group of LEDs pointing to current hour
- **Minute Hand**: LED(s) indicating current minute  
- **Second Hand**: Single LED sweeping around the ring

Press the illuminated button to toggle between clock mode and decorative lighting effects.

## License

Open source hardware and software project. See individual component licenses in documentation.