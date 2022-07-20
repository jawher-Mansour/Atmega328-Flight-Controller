# Atmega328-Flight-Controller
A  Flight Controller board for a quadcopter based on YMFC Joop Brokking's code.

<h1 align="center"><img src="Image/Board Animated GIF.gif" alt="Board Animated GIF" style="width:50%"/></h1>

This is the readme file of the Atmega328-Flight Controller project, which is my contribution to the OPEN SOURCE community. The board was developed by LAB619 Engineering & Consulting Services which is a tech company based in Tunisia that is specialized in custom machine fabrication and embedded solution development, the company is also specialized in developing IoT solutions (LoRa, GPRS, and WiFi), PCB and mechanical design. You can check the website for further information: [LAB619 Engineering & Consulting Services](https://lab619.tn)

This board is an Atmega328 MCU-based flight controller for quadcopters that is easy to build and fun to fly. The board is compatible with Joop BROKKING YMFC-AL (Your Multi-copter Flight Controller -Auto Leveling). Auto leveling means that when you release the sticks the quadcopter levels itself.

## Broadly, this repository consists of:

- Hardware designs (developed using Altium).
- PDF for Schematics
- Bill of Materials Files 
- Footprint Position File 
- Gerber Files 
- Software written using Arduino-IDE
```
📦Atmega328-Flight-Controller
 ┣ 📂Fabrication
 ┃ ┣ 📂Assembly
 ┃ ┣ 📂Gerber
 ┃ ┣ 📂Interactive Bill of Materials
 ┣ 📂Image
 ┣ 📂Altium Files
 ┣ 📂Software
 ┣ 📜.gitignore
 ┣ 📜README.md
 ┣ 📜fabrication and assembly drawings.pdf
 ┗ 📜Schematics.pdf
```
---
## Board Specifications :

The board currently includes:

- MCU: Atmega328 with an I2C, UART, and SPI interfaces.
- IMU: MPU6050 which is a 3-axis gyroscope and a 3-axis accelerometer on the same silicon die with an I2C interface and an interrupt pin.
- 4 PWM outputs to control the motors.
- 4 Timer input channels for the Inputs.
- Batterie voltage measurement system (voltage divider and Zener diode for protection).
- FTDI and ICSP interfaces for programming & debugging.
- LEDs for signaling.


<table>
  <tr>
    <td> 
    <img src="Image/3D rendering/PCB Top view.jpg.jpg"
     alt="PCB Rendred Top View"
     style="display: block; 
     margin-left: auto; 
     margin-right: auto; 
     width: 50%;"/> 
  </td>
  <td>   
   <img src="Image/3D rendering/PCB Bottom view.jpg" 
   alt="PCB Rendred Bottom View"
   style="display: block;
   margin-left: auto;
   margin-right: auto;
   width: 50%;"/> 
  </td>  
  </tr> 
  <tr>
    <td> 
      <center> Top side of the PCB </center>
  </td>
  <td> 
      <center>Bottom  side of the PCB</center>
  </td>  
  </tr> 
</table>

## Getting Started:

In order to program the board, it is necessary to use an **AVR ICSP** Programmer . 

If you don't have an AVR ICSP you can use any Arduino board as a programmer as shown in this [link](https://docs.arduino.cc/built-in-examples/arduino-isp/ArduinoISP)

---
### Fabrication

This board can be manufactured and assembled by JLCPCB. Check fabrication folder for files related to manufacturing the board

---
### How to setup and program the baord 

Use an AVR ICSP programmer or any Arduino board as a programmer to connect to **Atmega328-Flight-Controller**

You need to connect AVR ICSP's 5V,MOSI,MISO,SCK,RESET,GND to Flight Controller board's 5V,MOSI,MISO,SCK,RESET,GND.

Further details can be found on Joop BroKking web page [link](http://www.brokking.net/ymfc-al_main.html) 

<table>
  <tr>
    <td> 
    <img src="Image/SWD.9.jpg" 
   alt=""
     style="display: block; 
     margin-left: auto; 
     margin-right: auto; 
     width: 200px;"/> 
  </td>
  <td>   
   <img src="Image/st-link-v2.jpg" 
   alt=""
     style="display: center; 
     margin-left: auto; 
     margin-right: auto; 
     width: 200px;"/>
  </td>  
  </tr> 
  <tr>
    <td> 
    <center>Programming Pins</center>
  </td>
  <td>   
   <center>AVR ICSP programmer</center>
  </td>  
  </tr> 
</table>

---

## Useful ressources
### Datatsheets

- Atmega328 Datasheet [Atmega328](https://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-7810-Automotive-Microcontrollers-ATmega328P_Datasheet.pdf)
- MPU6050 Datasheet [MPU6050](https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf)

## Credits


- PCB design and hardware engineering : Jawher MANSOUR [Web ](https://jawher-mansour.github.io/) email: jawhermansour@outlook.com

- Software design : Joop Brokking [Web](http://www.brokking.net/)



---

**Note:** ***This repository is reserveed for hte hardware part of this project , as well as the emedded software of the project.***
