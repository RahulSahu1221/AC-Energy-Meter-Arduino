<div align="center">

# Arduino-Based AC Energy Meter

  <b>Real-Time AC Voltage, Current, Power & Energy Measurement</b>

<p align="center">

![Arduino](https://img.shields.io/badge/Arduino%20Uno-00979D?style=for-the-badge\&logo=arduino\&logoColor=white)
![Proteus](https://img.shields.io/badge/Proteus-8-1769AA?style=for-the-badge)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge\&logo=cplusplus\&logoColor=white)
![ACS712](https://img.shields.io/badge/Sensor-ACS712-orange?style=for-the-badge)

</div>

---

## Overview

The **Arduino-Based AC Energy Meter** is a mini-project designed to measure and display essential AC electrical parameters in real time.

The system measures:

* AC Voltage
* AC Current
* Power Consumption
* Energy Consumption

The project uses an **Arduino Uno**, **ACS712-05B current sensor**, transformer-based voltage sensing circuit, and a **20×4 LCD**. The complete system is developed and tested using **Proteus 8 Professional** simulation.

---

## Objectives

* Measure AC voltage.
* Measure AC current.
* Calculate electrical power.
* Calculate energy consumption.
* Display measured parameters on a 20×4 LCD.
* Validate the system through Proteus simulation.

---

## Hardware Components

| Component              | Purpose                       |
| ---------------------- | ----------------------------- |
| Arduino Uno            | Main controller               |
| ACS712-05B             | AC current sensing            |
| 220V/13V Transformer   | Voltage sensing and isolation |
| 20×4 LCD               | Display                       |
| 100kΩ & 10kΩ Resistors | Voltage signal conditioning   |
| 10µF Capacitor         | Signal conditioning           |

---

## Software & Tools

* **Arduino IDE**
* **Proteus 8 Professional**
* **EmonLib**
* **Embedded C/C++**

---

## Working Principle

The input AC voltage is stepped down from approximately **220 V AC to 13 V AC** using a transformer.

The stepped-down voltage is conditioned using a resistor divider and capacitor network before being supplied to the Arduino's analog input.

The **ACS712-05B** senses the load current and provides an analog output proportional to the current.

The Arduino processes the sensor signals and calculates voltage, current, power, and energy. The results are continuously displayed on the LCD.

```text
          AC SUPPLY
              │
       ┌──────┴──────┐
       │             │
       ▼             ▼
   Transformer     ACS712
       │          Current Sensor
       ▼             │
 Voltage Sensing     │
   & Conditioning    │
       │             │
       └──────┬──────┘
              ▼
        ┌─────────────┐
        │ Arduino Uno │
        └──────┬──────┘
               │
               ▼
          ┌─────────┐
          │ 20×4 LCD│
          └─────────┘
```

---

## Mathematical Calculations

### AC Current

The current is calculated from the ACS712 sensor output:

```text
I = (Vsensor − Voffset) / Sensitivity
```

The program then converts the measured value into an AC current estimate.

### Power

```text
P = V × I
```

where:

* `P` = Power in watts
* `V` = RMS voltage in volts
* `I` = RMS current in amperes

### Energy

```text
E = (P × t) / 3600
```

where:

* `E` = Energy in Wh
* `P` = Power in W
* `t` = Time in seconds

---

## Program Flow

```text
START
  │
  ▼
Initialize LCD
  │
  ▼
Initialize EmonLib
  │
  ▼
Measure AC Voltage
  │
  ▼
Measure AC Current
  │
  ▼
Calculate Power
  │
  ▼
Calculate Energy
  │
  ▼
Display Values
  │
  ▼
Repeat
```

---

## Circuit & Wiring
<img width="1920" height="812" alt="Circuit   Wiring" src="https://github.com/user-attachments/assets/3062bb82-715c-45b3-a9b1-d37a395fb30c" />

---

## LCD Output

Example simulation output:

```text
AC ENERGY METER

V = 220V   I = 3.2A

P = 703.74W E = 7Wh
```
<img width="534" height="342" alt="LCD Output" src="https://github.com/user-attachments/assets/3e40129d-89a1-46d3-9863-8fe583f3d13f" />

---

## Simulation Results

The circuit was successfully simulated using **Proteus 8 Professional**.

| Parameter          |          Result |
| ------------------ | --------------: |
| Input Voltage      |           220 V |
| Transformer Output |          ≈ 13 V |
| Measured Current   |         ≈ 3.2 A |
| Calculated Power   |      ≈ 703.74 W |
| Energy             | Displayed in Wh |

---

## Project Structure

```text
Arduino-AC-Energy-Meter/
│
├── README.md
│
├── AC_Energy_Meter.ino    
│
├── AC_Energy_Meter.pdsprj
|
└── AC_Energy_Meter_Report.pdf
```
---

## Key Features

* Real-time AC voltage measurement
* AC current measurement using ACS712
* Power calculation
* Energy consumption calculation
* 20×4 LCD interface
* Arduino-based processing
* Proteus simulation
* Simple and low-cost architecture

---

## Limitations

* Power factor is assumed to be unity.
* The current measurement method is simplified.
* Energy calculation is based on the calculated power and elapsed time.
* The implementation is primarily simulation-oriented.
* Practical implementation requires proper calibration.

---

## Future Scope

The system can be further enhanced with:

* IoT-based monitoring
* GSM alerts
* Cloud data logging
* Mobile application
* Remote energy monitoring
* Data logging
* Power-factor measurement
* Smart-grid integration

---

## Documentation

The detailed project report is available here:

**[AC Energy Meter Project Report](Documentation/AC_Energy_Meter_Report.pdf)**

The report includes the circuit description, working principle, mathematical calculations, algorithm, source code, simulation results, limitations, applications, and future scope.

---

## Technologies Used

```text
Arduino Uno
ACS712-05B
20×4 LCD
Transformer
Proteus 8 Professional
Arduino IDE
EmonLib
Embedded C/C++
```

---

## Author

**Rahul Sahu**

B.Tech – Electrical & Electronics Engineering

---

## 📄 License

This project is intended for **educational and learning purposes**.
