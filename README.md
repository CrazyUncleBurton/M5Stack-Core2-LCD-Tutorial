# M5Stack-Core2-LCD-Testing

by Bryan A. "CrazyUncleBurton" Thompson
Last Updated 2/21/2026

## Concepts

In this project we show you how to download a project from GitHub, then compile it for the M5Stack Core2 Microcontroller, then upload it to the microcontroller.  The program is basic - it reads from an I2C sensor array and then outputs the data to the microcontroller LCD.

## Hardware

Microcontroller:  M5Stack Core2
Sensor: M5Stack Unit ENV III Temp/Pressure/Humidity sensor + 4 wire Grove cable

Connect cable to sensor, then connect to red port on Microcontroller.

## Documentation

See the project files / docs folder for a PDF of the tutorial.

## M5Stack Core2 AWS Hardware

### On / Off / Reset

Power On/Off Operations:
Power On: Click the power button on the left side
Power Off: Long press the power button on the left side for 6 seconds
Reset: Click the RST button on the bottom

### CP2104 USB C Serial Port Controller

G1 - RXD
G3 - TXD

### Port A - Red

Black - GND
Red - 5V
Yellow - G32
White - G33

This is a HY2.0-4P connector, also called a Grove connector.  

### Port B - Black

Black - GND
Red - 5V
Yellow - G26
White - G36

This is a HY2.0-4P connector, also called a Grove connector.  

### Port C - Blue

Black - GND
Red - 5V
Yellow - G13
White - G14

This is a HY2.0-4P connector, also called a Grove connector.  

### M5Bus

1 - GND
2 - G35 - ADC
3 - GND
4 - G36 - ADC
5 - GND
6 - RST - EN
7 - G23 - MOSI
8 - G25 - DAC
9 - G38 - MISO
10 - G26 - DAC
11 - G18 - SCK
12 - 3V3
13 - G3 - RXD0
14 - G1 - TXD0
15 - G13 - RXD2
16 - G14 - TXD2
17 - G21 - IntSDA
18 - G22 - IntSCL
19 - G32 - ExtSDA
20 - G33 - ExtSCL
21 - G27 - GPIO
22 - G19 - GPIO
23 - G2 - I2S_DOUT
24 - G0 - I2S_LRCK
25 - NC
26 - G34 - I2S_DATA
27 - NC
28 - 5V
29 - NC
30 - BAT

### Internal I2C Connections

MPU6886 3 Axis Gyro / 3 Axis Accelerometer I2C Address 0x68, G21=SDA, G22=SCL
AXP192 Power Management IC, I2C Address 0x34,  G21=SDA, G22=SCL, Green Power Indicator AXP_IO1=VCC, AXP_LDO3=/, Vibration Motor AXP_LDO3=VCC,
BM8563 Real Time Clock - I2C Address=0x51,  G21=SDA, G22=SCL, Int goes to AXP192
FT6336  Capacitive Touch Controller - I2C Address=0x38,  G21=SDA, G22=SCL, G39=INT, AXP_IO4=RST
ATECC608 - I2C Address 0x35,  G21=SDA, G22=SCL
ILI9342C - 2.0" 320x240 - G38=MISO, G23=MOSI, G18=SCK, G5=CS, G15=DC, AXP_IO4=RST, AXP_DC3=BL, AXP_LDO2=PWR, 
TF Card - Supports up to 16GB - G38=MISO, G23=MOSI, G18=SCK, G4=CS

### Other Internal Hardware

SK6812-LED - G25=DATA
NS4168 Amplifier - BCLK=G12, LRCK=G0, DATA=G2, 
SPM1423 Mic - CLK=G0, DATA=G34,

### Internal ADCs

They are totally unreliable.  Don't use them.  Also there's no Vref, so you're dependent on the accuracy of the voltage at the power pin.

## References

Microcontroller Info:
<https://docs.m5stack.com/en/core/core2_for_aws>

Sensor Info:
<https://docs.m5stack.com/en/unit/envIII>

Display Library:
<https://docs.m5stack.com/en/arduino/m5core2/display>
<https://docs.m5stack.com/en/arduino/m5gfx/m5gfx_functions>
