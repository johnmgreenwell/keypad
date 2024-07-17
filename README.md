## Keypad library for Arduino

**Authors:**  *Mark Stanley***,** *Alexander Brevig*


This repository is a copy of the code found here [[Arduino Playground]](http://playground.arduino.cc/Code/Keypad).

The source and file structure has been modified to conform to the newer `1.5r2` library specification and is not compatible with legacy IDE's.
For these IDE's, visit the link above to grab the pre `1.0` compatible version, or download it directly here:  [[pre `1.0` version]](http://playground.arduino.cc/uploads/Code/keypad.zip).

Modified by John Greenwell to adapt driver for custom HAL support, 2024.

## Usage

For this modified version, the following hardware abstraction layer (HAL) requirements must be satisfied:

* A header file `hal.h` providing access to HAL namespace classes and methods.
* A `GPIOPort` class within the `HAL` namespace which is initialized with an array of pins and supplies the following methods:
  - Set pin mode (by index in virtual port): `pinMode(uint8_t pin, uint8_t mode)`
  - Write logic level to pin (by index in virtual port): `digitalWrite(uint8_t pin, uint8_t val)`
  - Read logic level from pin (by index in virtual port): `digitalRead(uint8_t pin)`
* A millis() function in the HAL namespace that returns an accurate milliseconds counter to be used for timing.

Some further requirements may also be found. Typically, these will mirror the Arduino framework and should be added to `hal.h`.