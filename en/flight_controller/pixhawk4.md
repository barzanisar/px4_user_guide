# Pixhawk 4 Flight Controller

Pixhawk 4 is an advanced autopilot designed and made in collaboration with Holybro and the PX4 team.
It is optimized to run the full Dronecode stack, suitable for academic and commercial developers.
It features the currently most advanced processor and sensor technology from ST Microelectronics® and a NuttX
real-time operating system, delivering incredible developer experience with its high performance, ease-of-use and flexibility.

![Pixhawk4 Image](../../assets/hardware/hardware-pixhawk4.png

Assembly/setup instructions for use with PX4 are provided here: [Pixhawk Wiring Quickstart](../assembly/quick_start_pixhawk4.md)


The main features include:

* A new and small form factor
* More computing power and 2X the RAM than previous versions
* New sensors with higher temperature stability
* Integrated vibrations isolation
* Increased ease-of-use: pre-installed with most recent PX4 (v1.7)
* Additional ports for better integration and expansion

## Specifications

* Main Processor: STM32F76xxx, rev. Z
* IO Processor: STM32F103 
* Sensors:
  * Accel/Gyro: ICM-20689
  * Accel/Gyro: BMI055
  * Mag: IST8310
  * Barometer: MS5611
* Dimensions: 44x84x12mm
* Weight: 15.8g
* GPS Module: ublox Neo-M8N GPS/GLONASS receiver; integrated magnetometer IST8310
  * Dimensions: D50mm H14mm
  * Weight: 32g
* Interface:
* 2 x Telemetry (UART with flow control) (TELEM1, TELEM2)
* 1 x UART with I2C (TELEM3)
* 1 x GPS (UART + I2C + Safety Switch + Buzzer)
* 1 x RC input (Futaba S BUS® Compatible RC + Spektrum DSM/DSM2/DSM-X® Satellite Compatible RC)
* 1 x PPM RC input
* 8 x FMU PWM outputs
* 8 x IO PWM outputs
* 2 x Power Brick
* 1 x SPI
* 1 x SBUS output
* 2 x CAN Bus
* 1 x AUX ports (input capturing + ADC)
* 1 x I2C
* 1 x MicroSD card slot
* Micro USB Port


## Pinouts and Schematics

As a CC-BY-SA 3.0 licensed Open Hardware design, all schematics and design files are [available](https://github.com/PX4/Hardware). 

The board is documented in detailed on the [Pixhawk4 project](https://pixhawk.org/modules/pixhawk4) website.


## Availability

**To be added**

## Build Instructions

`make px4fmu-v5_default upload`

