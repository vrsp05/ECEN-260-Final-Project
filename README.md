# Battery Voltage Meter (STM32)

## Overview
This ECEN 260 embedded systems project uses an **STM32 Nucleo-L476RG** microcontroller to measure and display the voltage and estimated charge percentage of common batteries (1.5V, 3V, and 9V). The system reads analog voltage through the ADC, displays results on an I2C LCD, and accepts user commands via UART.

A full walkthrough of the implementation is available in the **[final project code explanation video](https://youtu.be/R2C42Zuq1PI)**, and a short live demonstration can be seen in the **[final project demo video](https://youtube.com/shorts/q6mWsFuafF4)**.

---

## Project Resources
- **[Project Design Essay](https://github.com/vrsp05/ECEN-260-Final-Project/blob/main/Final%20Project%20Design%20Essay.docx)**  
- **[Final Project Report (PDF)](https://github.com/vrsp05/ECEN-260-Final-Project/blob/main/ECEN_260_Final_roject_Report.pdf)**  
- **[Main Source Code (`main.c`)](https://github.com/vrsp05/ECEN-260-Final-Project/blob/main/Final_Project_main.c)**  

---

## Features
- Measures voltage and charge percentage for:
  - 1.5V batteries
  - 3V batteries
  - 9V batteries (using a protective voltage divider)
- Displays real-time data on an LCD1602 via I2C
- UART command interface for battery selection and system control
- LED indicators show the active battery type
- Reset command clears display and system state

---

## How It Works
1. The STM32 board is powered through a USB connection.
2. A battery is connected using alligator clips.
3. The user sends a command through PuTTY to select a battery type:
    VIEW 1.5V
    VIEW 3V
    VIEW 9V
4. The system reads the ADC value, calculates voltage and charge percentage, and updates the LCD.
5. The `RESET` command clears the display and turns off all LEDs.

Only one battery type can be measured at a time.

---

## Hardware Components
- STM32 Nucleo-L476RG  
- LCD1602 display (I2C)  
- LEDs and resistors  
- Voltage divider for 9V measurements  
- Breadboard, jumper wires, and alligator clips  

---

## Testing & Validation
The system was tested under multiple scenarios to verify:
- Accurate voltage and percentage calculations
- Correct LED behavior for each battery type
- Proper UART command handling
- Stable behavior when invalid inputs are provided

Detailed test procedures and results are documented in the **Final Project Report**.

---

## Limitations
- Supports only 1.5V, 3V, and 9V batteries  
- One battery type can be measured at a time  
- LCD output limited to two lines  
- No persistent data storage  

---

## Skills Demonstrated
- Embedded C programming  
- ADC configuration and voltage scaling  
- UART communication  
- I2C display integration  
- Hardware–software integration  
- System testing and debugging  

---

## Notes
This project was completed as part of **ECEN 260** coursework and reflects my early hands-on experience with embedded systems design and microcontroller programming.
