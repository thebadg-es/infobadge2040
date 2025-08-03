
# InfoBadge

**InfoBadge** is a customizable e-paper badge system designed for events, personal identification, or creative display purposes. The project includes both firmware for the badge and a Python GUI for sending data to it over serial.

## 📁 Folder Structure

- `fw/` — Arduino firmware for the badge.
- `fw/fuentes/` — Fonts used in the firmware (see below).
- `kicad/` — PCB design files (KiCad).
- `python/` — Python GUI application for sending text to the badge.
- `.gitignore`, `.git/` — Git configuration files.

## 🔤 Adding Custom Fonts

To use custom fonts in the Arduino firmware:

1. Go to [https://rop.nl/truetype2gfx/](https://rop.nl/truetype2gfx/).
2. Convert your `.ttf` font to a `.h` file compatible with Adafruit GFX.
3. Place the generated font header file (`.h`) into the `fw/fuentes/` folder.
4. Include it in your sketch and use it with `display.setFont(...)`.

This allows you to personalize the badge display with different font styles.

## 🔧 Required Arduino Libraries

Make sure to install the following libraries via the Arduino Library Manager before compiling the firmware:

- **Adafruit GFX Library**
- **Adafruit BusIO**
- **Adafruit EPD** (for e-paper display support)
- **qrcode** — For generating and rendering QR codes on the badge display.

To install:
1. Open Arduino IDE.
2. Go to **Tools > Manage Libraries...**
3. Search and install each of the libraries listed above.

## 💻 Python GUI

The Python application under the `python/` folder allows you to input up to five lines of information:
- Name
- Position
- Webpage
- X account
- QR URL

These strings are sent via serial to the badge. The GUI also allows serial port selection and uses a visual style inspired by [thebadg.es](https://www.thebadg.es).

## 🧠 Microcontroller

This project is based on the **Raspberry Pi RP2040** microcontroller.

## 🔌 Pinout

The following pins are used for onboard components:

```cpp
#define LED1_PIN 28
#define LED2_PIN 27

#define PB1_PIN 29
#define PB2_PIN 26
```

- **LED1** → GPIO 28  
- **LED2** → GPIO 27  
- **Push Button 1 (PB1)** → GPIO 29  
- **Push Button 2 (PB2)** → GPIO 26  


## 📰 Published Article

This project is documented in detail in an article written by the author on Maker Pro and hackster.io:

**Battery-less Display Badge Powered by RP2040**  
📎 [Read the maker.pro project](https://maker.pro/arduino/projects/battery-less-display-badge)

**eInk Badge**  
📎 [Read the Hackster.io project](https://www.hackster.io/pablotrujillojuan/eink-badge-ca154f)

The article explains the motivation, design decisions, and technical details behind this project, including:

- Use of an **e-ink display** for ultra-low power consumption.
- Communication via USB or serial interface.
- How the badge can be used in events or static installations.
- Visual customization with fonts, QR codes, and layout.

It serves as the official project write-up and a helpful resource for anyone wanting to build or extend the InfoBadge.
