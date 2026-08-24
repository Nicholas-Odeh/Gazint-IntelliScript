<h1 align="center">Gazint IntelliScript</h1>

IntelliScript is a programmable input device built on an ATmega32U4. The ATmega32U4 provides native USB support, which allows the board to operate as Human Interface Device. Pressing a button on the device executes a preprogrammed sequence of administrative actions onto the workstation the device is connected to. 


![IntelliScript reference build](https://github.com/Nicholas-Odeh/Gazint-IntelliScript/blob/main/Gazint-IntelliScript-V2/Images/Final_product.jpeg)


---

<h1 align="center">Repository layout</h1>


| Folder | Contents | Comments |
|---|---|---|
| Code | `Gazint-IntelliScript-V2.ino` | Complete firmware |
| Bitmaps | Bitmap code | Clean line art for 128×32 displays |
| Device-Housing | 3D-printable enclosure | PLA is fine |
| Images | Project images | Breadboard reference and final product |
| SOP | `Gazint-Intelliscript-SOP` | Authorization, handling, risks, and safe practices |



---
<h1 align="center">Hardware</h1>


### Parts

| Part | Notes |
|---|---|
| Arduino Pro Micro (ATmega32U4) | ATmega32U4 is what makes HID emulation possible. |
| 128×32 SSD1306 OLED, I²C | Uses the I²C address `0x3C`. |
| 2 × momentary tactile buttons | Hotkey A and hotkey B. |
| 2 × 10k resistors | One per button, to GND. |
| 2 × LEDs *(optional)* | Development status indicators only; the firmware runs fine without them. |

### Wiring

| Connection | Pro Micro pin |
|---|---|
| OLED SDA | 2 |
| OLED SCL | 3 |
| OLED VCC / GND | VCC / GND |
| Button A | 16 |
| Button B | 15 |
| Red status LED *(optional)* | 5 |
| Green status LED *(optional)* | 6 |


**Buttons are active-HIGH.** So each button connects its pin to VCC when pressed and needs a pull-down
resistor. Without that resistor, the pin floats.

### Breadboard Visual
![IntelliScript reference circuit](https://github.com/Nicholas-Odeh/Gazint-IntelliScript/blob/main/Gazint-IntelliScript-V2/Images/Circuit-layout.jpeg)
---

<h1 align="center">Safety and responsible use</h1>

IntelliScript is a keystroke-injection device. The host cannot tell its input apart from a
person typing on a real keyboard, and that has consequences worth understanding before you build
one.

- **Use it only on systems you own or are authorized to administer.** 
- **It masks keyboard faults.** 
- **A BIOS hotkey embeds your BIOS password in plaintext**
- **Corporate endpoint tooling may flag or block it.** EDR and USB device-control policies
  frequently treat HID injectors as hostile hardware.


`SOP/Gazint-Intelliscript-SOP.pdf` covers all of this in operational detail — authorization,
custody, and change control.

---
<h1 align="center">Demo</h1>

![IntelliScript demo](https://github.com/Nicholas-Odeh/Gazint-IntelliScript/blob/main/Gazint-IntelliScript-V2/Images/Gazint-Live-Demo.gif)

