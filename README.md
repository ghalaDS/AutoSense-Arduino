# Arduino Sensor Projects Collection

A collection of two smart Arduino-based sensor systems designed for **energy-saving** and **automated control**. Each project combines hardware components with intuitive logic to create efficient and interactive systems.

---

## Table of Contents

1. [Dual-Control Saver](#dual-control-saver)
2. [Intelligent Proximity Light System](#intelligent-proximity-light-system)

---

## Dual-Control Saver

This project is a smart energy-saving system that uses a **PIR motion sensor** and a **push button** to control a real light bulb using a **relay**. The bulb only turns ON if **motion is detected** *and* **the button is pressed**. When motion stops, the bulb shuts off automatically.

### Project Preview

<table>
  <tr>
    <th>Button State</th>
    <th>Image</th>
  </tr>
  <tr>
    <td>Pressed</td>
    <td><img src="images/button-pressed.png" width="250"/></td>
  </tr>
  <tr>
    <td>Unpressed + Motion</td>
    <td><img src="images/button-unpressed.png" width="250"/></td>
  </tr>
</table>

### Components Used
- Arduino Uno  
- PIR Motion Sensor  
- Push Button  
- Relay Module (to control real light bulb)  
- Real Light Bulb  
- 10kΩ Resistor  
- Jumper Wires  
- Breadboard  

### How It Works

```cpp
| Condition                      | Bulb Behavior             |
|--------------------------------|---------------------------|
| No motion                      | Bulb turns OFF            |
| Motion detected, no button     | Bulb stays OFF            |
| Motion detected + button press | Bulb toggles ON/OFF       |
| Motion stops at any time       | Bulb turns OFF immediately|
```

### Circuit Wiring
- `PIR OUT` → Arduino pin **2**  
- `Button` → Arduino pin **4**  
- `Relay IN` → Arduino pin **5**  
- Bulb connected to relay output terminals  
- GND and 5V connected appropriately  
- 10kΩ pull-down resistor on button

### Try It Yourself
You can try the full simulation here:
[Start Simulation](https://www.tinkercad.com/things/4LO0VkyMW3Q-smooth-turing-vihelmo)

Click "Start Simulation" to watch how the servos sweep back and forth using the Arduino logic.

---

## Intelligent Proximity Light System
A simple and efficient Arduino-based system that uses a Light Dependent Resistor (LDR) and an Ultrasonic Sensor to control an LED. The LED is activated only when ambient light is low and an object is detected within range.

### Features
- Combines analog (LDR) and digital (ultrasonic) sensors
- Automatically activates LED based on real-world conditions
- Ideal for energy-saving smart lighting in dark spaces or corridors

### Project Preview
| LED ON (Dark + Object Detected) | LED OFF (Light or No Object) |
|----------------------------------|-------------------------------|
| <img src="images/sensor_dark.png" width="200"/> | <img src="images/sensor_light.png" width="200"/> |

| Serial Output (Dark) | Serial Output (Light) |
|----------------------|-----------------------|
| <img src="images/serial_output_dark.png" width="250"/> | <img src="images/serial_output_light.png" width="250"/> |


### System Logic
````cpp
if (light < 100 && distance < 100) {
  digitalWrite(ledPin, HIGH);
} else {
  digitalWrite(ledPin, LOW);
}
````
### Components Used
- Arduino Uno
- LDR (Light Dependent Resistor)
- 470Ω Resistor (for LED)
- Ultrasonic Sensor (Ping))) - single SIG pin
- LED
- Breadboard
- Jumper Wires

### Try It Yourself
You can try the full simulation here:
[Start Simulation](https://www.tinkercad.com/things/agbEQ40rsUy-mighty-snicket)

Click "Start Simulation" to watch how the servos sweep back and forth using the Arduino logic.
