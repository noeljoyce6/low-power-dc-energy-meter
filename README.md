# 🔋 Low Power DC Energy Meter

A compact Arduino Nano-based 5V DC energy meter designed to measure, display, and log voltage, current, power, and energy consumption in real-time. This project was developed as part of the Logic Circuit Design (ECT 203) course at Amal Jyothi College of Engineering.

---

## 📌 Objective

To develop a low-power energy meter/logger capable of:
- Measuring voltage, current, power, and energy consumption of DC loads
- Displaying real-time data on an OLED display
- Logging measured data to a microSD card in CSV format

---

## 🧰 Components Used

| Component                 | Quantity | Description                                      |
|--------------------------|----------|--------------------------------------------------|
| Arduino Nano             | 1        | ATmega328P-based microcontroller board           |
| INA219 Power Monitor IC  | 1        | For measuring voltage and current                |
| MicroSD Card Module      | 1        | For logging data                                 |
| 0.96" OLED Display (I2C) | 1        | For real-time display of readings                |
| 7805 Voltage Regulator   | 1        | For converting 9V to 5V                          |
| 9V Battery               | 1        | Power supply                                     |
| 3V Warm White LED Chip   | 1        | Simulated DC load                                |

---

## ⚙️ Working Principle

1. **Power Supply**: 9V battery regulated to 5V using 7805.
2. **Measurement**: INA219 reads current and voltage of the load.
3. **Processing**: Arduino Nano calculates:
   - Power = Voltage × Current
   - Energy (mWh) over time
4. **Display**: OLED shows real-time values.
5. **Logging**: Data is written to a `.csv` file on a microSD card every second.

---

---

## 🧾 Code Structure

- `setup()` initializes peripherals, timer, display, and file.
- `loop()` runs every second via timer interrupt:
  - Fetches readings
  - Updates OLED
  - Logs data to `MEAS.csv` on the SD card

Arduino libraries used:
- [`Adafruit_INA219`](https://github.com/adafruit/Adafruit_INA219)
- [`SSD1306Ascii`](https://github.com/greiman/SSD1306Ascii)
- [`SdFat`](https://github.com/greiman/SdFat)

---

## 📂 File Structure

