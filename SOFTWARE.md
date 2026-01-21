# Software Configuration & Setup

## Firmware: WLED

This project uses WLED, an open-source ESP8266/ESP32 web server firmware specifically designed for controlling addressable LEDs.

### Installation
1. Download WLED from [https://github.com/Aircoookie/WLED](https://github.com/Aircoookie/WLED)
2. Flash to your ESP32/ESP8266 using ESP Flash Tool or Arduino IDE
3. Connect to the WLED access point and configure Wi-Fi

## Configuration Steps

### 1. LED Setup
Navigate to: **Config > LED Preferences**
- **LED count**: Set to `60`
- **Data Pin**: Set to match your wiring:
  - ESP32: GPIO 16
  - ESP8266: GPIO 2 (D4)
- **LED Type**: WS2812B/SK6812/WS2813
- **Color Order**: GRB (typical for WS2812B)

### 2. Button Setup
Navigate to: **Config > Sync Interfaces**
- **Button 0 GPIO**: Set to the GPIO used for the switch (typically GPIO 0)
- **Button Type**: "Pushbutton"
- **Button Action**: "Preset cycle" or "Toggle preset"

### 3. Clock Overlay Configuration
Navigate to: **Config > Time & Macros**
- **Enable Analog Clock**: ✓ Checked
- **12h LED**: Set to top dead center LED ID (typically LED 0 or 15 depending on your ring orientation)
- **Timezone**: Configure your local timezone
- **NTP Server**: Use default or specify your preferred NTP server

### 4. Preset Configuration

#### Preset 1 (Clock Mode)
- **Name**: "Clock"
- **API Command**: `OL=1` (Enables the clock hands overlay)
- **Effect**: Any base effect (solid color recommended)
- **Colors**: Choose clock hand colors (e.g., white for hour, blue for minute, red for second)

#### Preset 2 (Party/Mood Mode)
- **Name**: "Party"
- **API Command**: `OL=0` (Disables the clock overlay)
- **Effect**: Dynamic effects like "Rainbow", "Color Loop", "Fire", etc.
- **Speed**: Adjust to preference
- **Intensity**: Adjust brightness and effect intensity

### 5. Macro Setup
Navigate to: **Config > Time & Macros**
- **Button Macro**: Configure button press to toggle between Preset 1 and Preset 2
- **Example Macro**: `T=1&T=2` (toggles between presets 1 and 2)

## API Commands Reference

### Clock Control
- `OL=1` - Enable analog clock overlay
- `OL=0` - Disable analog clock overlay
- `OL=2` - Enable digital clock overlay

### Preset Control
- `PS=1` - Load preset 1
- `PS=2` - Load preset 2
- `T=1&T=2` - Toggle between presets 1 and 2

### Time Sync
- `NT` - Force NTP time sync
- `TZ=<offset>` - Set timezone offset

## Functional Description

### Power On Sequence:
1. Device boots up and connects to Wi-Fi
2. Fetches accurate time via NTP (Network Time Protocol)
3. Displays current time on the LED ring using the analog clock overlay

### User Interaction:
1. **Button Press Detection**:
   - Capacitor absorbs contact bounce
   - ESP32 detects clean LOW signal
   - WLED executes the configured macro

2. **Mode Toggle**:
   - **Clock Mode**: Clock hands visible, shows current time
   - **Party Mode**: Clock hands disappear, dynamic lighting effects active

### Clock Hand Representation:
- **Hour Hand**: Typically 1/4 of LEDs lit in a line pointing to current hour
- **Minute Hand**: Single LED or small group pointing to current minute
- **Second Hand**: Single LED sweeping around the ring (optional)

## Troubleshooting

### Common Issues:
1. **Clock not syncing**: Check Wi-Fi connection and NTP server settings
2. **Button not responding**: Verify GPIO pin configuration and wiring
3. **LEDs not lighting**: Check power supply capacity and data pin connection
4. **Time incorrect**: Verify timezone settings and NTP sync

### Debug Commands:
- Access WLED web interface at device IP address
- Use serial monitor for boot messages and error logs
- Check WLED info page for system status

## Advanced Features

### Web Interface Access:
- Connect to device IP address in web browser
- Full control over effects, colors, and timing
- Real-time preview of changes

### Mobile App:
- WLED app available for iOS and Android
- Remote control and scheduling features
- Multiple device management