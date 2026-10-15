# ESP32-Based Smart Distance Monitoring and Obstacle Alert System

## 📌 Project Overview

This project implements a smart distance monitoring system using an ESP32 microcontroller, an HC-SR04 ultrasonic sensor, an OLED display, and a buzzer.

The system measures the distance between the sensor and a nearby object. It displays the measured distance and corresponding safety status on the OLED display. An audible alert is generated when an object enters the warning range.

The project was developed and tested using the Wokwi online simulator.

## 🎯 Objectives

- Interface an ultrasonic sensor with the ESP32.
- Measure distance in centimetres.
- Display distance and status on an OLED.
- Generate buzzer alerts based on distance thresholds.
- Understand embedded C++ programming and sensor interfacing.

## 🧰 Components Used

| Component | Purpose |
|---|---|
| ESP32 DevKit V1 | Main controller |
| HC-SR04 Ultrasonic Sensor | Distance measurement |
| 0.96-inch SSD1306 OLED | Displays distance and status |
| Buzzer | Audible warning |
| Wokwi Simulator | Virtual circuit development and testing |
| Arduino IDE | Embedded C++ development |

## 🔌 Circuit Connections

| Component Pin | ESP32 Pin |
|---|---|
| HC-SR04 VCC | 5V |
| HC-SR04 TRIG | GPIO 5 |
| HC-SR04 ECHO | GPIO 18 |
| HC-SR04 GND | GND |
| OLED VCC | 3V3 |
| OLED GND | GND |
| OLED SDA | GPIO 21 |
| OLED SCL | GPIO 22 |
| Buzzer Positive | GPIO 25 |
| Buzzer Negative | GND |

**Hardware safety:** When using a physical ESP32, protect GPIO 18 from the HC-SR04's 5V ECHO output using a voltage divider or level shifter.

## ⚙️ Working Principle

The HC-SR04 transmits ultrasonic sound waves when triggered. These waves reflect off an object and return to the sensor.

The ESP32 measures the time taken by the sound wave to travel to the object and back. It calculates the distance using:

Distance (cm) = Echo time (µs) × 0.0343 / 2

The measured distance is displayed on the OLED, and the buzzer responds according to the programmed thresholds.

## 💻 Software Logic

1. Initialize the ESP32 GPIO pins and OLED display.
2. Trigger the ultrasonic sensor.
3. Measure the echo duration.
4. Calculate the distance in centimetres.
5. Display the distance and status.
6. Activate or deactivate the buzzer according to the measured distance.
7. Repeat the process continuously.

## 📊 Simulation Results

The system was tested under three distance conditions in Wokwi.

| Distance | Display Status | Expected Buzzer Behaviour |
|---|---|---|
| 115.95 cm | SAFE | OFF |
| 41.37 cm | OBJECT NEAR | Intermittent alert |
| 5.06 cm | WARNING! / TOO CLOSE | Continuous alert |

These tests demonstrate that the simulated system responds to changes in object distance.

## 🌐 Wokwi Simulation

[Open the Smart Distance Monitoring project](https://wokwi.com/projects/477967044546918401)

## 🚀 Applications

- Parking assistance systems
- Obstacle detection in robotics
- Proximity warning systems
- Educational embedded systems projects

## ⚠️ Limitations

- Ultrasonic measurements can be affected by object angle and surface characteristics.
- The system has been tested in simulation; physical hardware performance has not yet been verified.

## 🔮 Future Scope

- Add LED indicators for different distance levels.
- Integrate wireless monitoring using Wi-Fi.
- Develop a mobile dashboard for distance monitoring.
- Test and calibrate the system using physical hardware.

## 👨‍💻 Author

**Swapnil Rawade**  
Electronics and Telecommunication Engineering (ENTC)  
RMD Sinhgad College of Engineering, Pune

## 🛠️ Technologies Used

ESP32 | Embedded C++ | Ultrasonic Sensor | I2C OLED | Wokwi
