![version](https://img.shields.io/github/v/tag/Reefwing-Software/MMC5883MA-Arduino-Library) ![license](https://img.shields.io/badge/license-MIT-green) ![release](https://img.shields.io/github/release-date/Reefwing-Software/MMC5883MA-Arduino-Library?color="red") ![open source](https://badgen.net/badge/open/source/blue?icon=github)

# MMC5883MA Arduino Library
 For use with the Duinotech 3 Axis Compass Magnetometer Module

I'm not sure who the author of this code is. Let me know and I will include attribution.

The Duinotech 3-Axis Compass Magnetometer Module (Part Number: XC-4496) can be purchased from Jaycar Electronics. Unfortunately, the module comes with no instructions and very brief specifications:

- Operating Voltage: 5VDC (or 3.3 VDC)
- Resolution: 12 bits
- Interface: I2C
- Includes: 5V to 3.3V level shifter (so you can operate it from 5 VDC)
- Dimensions: 20(L) x 16(W) x 5(H) mm

There are two versions of this board which use different chips.

## The QMC5883L Sensor
The QMC5883L is a multi-chip three-axis magnetic sensor. It is based on technology licensed from Honeywell AMR (Anisotropic Magnetoresistive) technology.

## The MMC5883MA Sensor
The MMC5883MA is a 3-axis magnetic sensor with on-chip signal processing and integrated I2C bus.

## I2C Address
Since you can have multiple devices connected via I2C, all devices have a unique address. The Honeywell HMC5883L uses the following I2C address:

- 7-bit Address: 0x1E (A 7-bit I2C address includes the 7-bit slave address in the first 7 bits of the byte. The eighth bit (the bit in the Least Significant Bit — LSB — position) is the read/write flag. A 0 in the eighth bit indicates a write and a 1 in the eighth bit signifies a read — Figure 3).

The QST QMC5883L uses:

- 7-bit address: 0x0D

The Memsic MMC5883MA uses:

- 7-bit address: 0x30

All devices support standard and fast I2C speed modes (i.e., 100kHz and 400kHz). Arduino boards use the Wire library to communicate with I2C devices. The Wire library expects you to use the 7 bit address. Valid addresses are between 8 and 127, the addresses between 0 and 7 are reserved.

A full description of the board types and appropriate Arduino Libraries is available at my Medium article: [Connecting the Duinotech 3-Axis Compass to an Arduino](https://medium.com/@reefwing/connecting-the-duinotech-3-axis-compass-to-an-arduino-b13c28d7d936).
