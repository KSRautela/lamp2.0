# Hardware Components & Assembly

## Bill of Materials (BOM)

| Component | Quantity | Description | Function |
|-----------|----------|-------------|----------|
| Microcontroller | 1 | ESP32 or ESP8266 (NodeMCU/Wemos) | The "brain" running the WLED web server and logic |
| LED Ring | 1 | WS2812B / Neopixel (60 LEDs) | Displays the clock hands and lighting effects |
| Control Switch | 1 | 4-Pin Illuminated Momentary Push Button (Metal) | Physical trigger to change modes; features a built-in LED ring |
| Resistor | 1 | 220Ω - 470Ω (0.25W) | Limits current to the switch's internal LED to prevent burnout |
| Capacitor | 1 | 0.1µF (100nF) Ceramic Disc (Code: 104) | Hardware Debouncing: Filters out electrical noise from the switch press |
| Power Supply | 1 | 5V 2A+ Adapter | Powers both the microcontroller and the LED ring |

## Circuit Connections

### LED Ring Connections (The Output)
- **VCC**: Connected to 5V (External Power or VIN)
- **GND**: Connected to Common Ground
- **DIN (Data In)**: Connected to GPIO 16 (ESP32) or GPIO 2 (ESP8266/D4)
- **Note**: A 330Ω resistor is optional on the Data line for signal integrity over long wires

### Illuminated Switch Connections (The Input)
The 4-pin switch is treated as two separate circuits:

#### The Button Logic (Debounced):
- **Pin 1**: Connected to GND
- **Pin 2**: Connected to GPIO 0 (or similar Digital Pin)
- **Filtering**: The 0.1µF Capacitor bridges Pin 1 and Pin 2 directly. This physically smoothes the voltage spike when the metal contacts touch, ensuring a single clean "click" is registered

#### The Button Light (Always On or Controlled):
- **Positive (+)**: Connected to 5V via the 220Ω Resistor
- **Negative (-)**: Connected to GND

## PCB Design Specifications (KiCad)

### Component Footprints:
- **Capacitor Footprint (C1)**: `Capacitor_THT:C_Disc_D5.0mm_W2.5mm_P2.50mm`
  - Type: Unpolarized
- **Resistor Footprint (R1)**: `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal`
  - Type: Standard 1/4 Watt resistor
- **Terminals**: Use `TerminalBlock_Screw_P5.00mm` or standard 2.54mm Pin Headers for connecting the external Switch and LED Ring wires

## Assembly Notes

1. **Power Considerations**: Ensure your power supply can handle the full LED ring at maximum brightness (60 LEDs × 60mA = 3.6A theoretical max)
2. **Heat Management**: Consider ventilation if running at high brightness for extended periods
3. **Wire Gauge**: Use appropriate wire gauge for power connections (18-20 AWG recommended for power)
4. **Mounting**: Design enclosure to allow easy access to the illuminated button while protecting the electronics