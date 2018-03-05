# Pixhawk 4 Wiring Quick Start

This quick start guide shows how to power the *Pixhawk 4* flight controller and connect its most important peripherals.
  
![Pixhawk 4 Image](../../images/pixhawk4_logo_view.jpg) 

## Wiring Chart Overview

The image below shows standard Pixhawk connections (excepting the motor and servo outputs). We'll go through each main part in the following sections.

![Pixhawk 4 Wiring Overview](../../images/pixhawk4_wiring_overview.jpg)
 
> **Note** More detailed wiring information is [shown below](#detailed-wiring-infographic-copter).


## Mount and Orient Controller

The *Pixhawk 4* should be mounted on the frame using vibration-damping foam pads (included in the kit). It should be
positioned as close to your vehicle’s center of gravity as possible, oriented top-side up 
with the arrow pointing towards the front of the vehicle.

![Pixhawk mounting and orientation](../../images/pixhawk_4_mounting_and_foam.jpg)

> **Note** If the controller cannot be mounted in the
  recommended/default orientation (e.g. due to space constraints) you will
  need to configure the autopilot software with the orientation that you
  actually used: [Flight Controller Orientation](../config/flight_controller_orientation.md).
  

## GPS + Compass

Attach the provided GPS with integrated compass (required) to the GPS port using the 10-wire cable supplied in the kit. 

> **Note** The diagram shows a combined GPS and Compass.  The GPS/Compass should be mounted on the frame as far away from other electronics as possible, with the direction marker towards the front of the vehicle (separating the compass from other electronics will reduce interference).

![Connect compass/GPS to Pixhawk4](../../images/pixhawk_4_compass_gps.jpg)


## Power

Connect the output of a *Power Management Board* (PM board) that comes with the kit to one of the **POWER** bricks of Pixhawk 4 using a 6-wire cable as shown. The PM input **2~12S** will be connected to your LiPo battery. The connections of *Power Management Board*, including power supply and signal connections to the ESCs and servos, are explained in the table below. Note that the PM board also supplies power to the servos via + and - pins of **FMU PWM-OUT**.

The image below shows the power management board provided with Pixhawk 4.

![Pixhawk 4 - Power Management Board](../../images/pixhawk_4_power_management_board.jpg)

| PIN&Connector | Function |    
| --- | --------------------- | 
| I/O PWM-IN   | connect to I/O PWM-OUT port of Pixhawk4 (J17)          |
| M1           |  PWM OUT 1: connect signal wire to ESC of motor 1 here |
| M2           |  PWM OUT 2: connect signal wire to ESC of motor 2 here |
| M3           |  PWM OUT 3: connect signal wire to ESC of motor 3 here |
| M4           |  PWM OUT 4: connect signal wire to ESC of motor 4 here |
| M5           |  PWM OUT 5: connect signal wire to ESC of motor 5 here |
| M6           |  PWM OUT 6: connect signal wire to ESC of motor 6 here |
| M7           |  PWM OUT 7: connect signal wire to ESC of motor 7 here |
| M8           |  PWM OUT 8: connect signal wire to ESC of motor 8 here |
| FMU PWM-IN   |  connect to AUX-OUT port of Pixhawk4(J26)              |   
| FMU PWM-OUT  |  AUX output: connect signal wires to ESC or signal,+,- wires to servos here |                                         
| PWM&ADC-OUT  |  connect to PWM&ADC IN port of Pixhawk4(J22)           |  
| PWM&ADC-IN   |  PWM&ADC input                                         |  
| B+           |  connect to ESC B+ to power the ESC                    |  
| GND          |  connect to ESC Ground                                 |  
| PWR1         |  5.3v output 3A,connect to Pixhawk4 power brick1       | 
| PWR2         |  5.3v output 3A,connect to Pixhawk4 power brick2       | 
| 2~12S        |  Power Input, support to 12S LiPo Battery              | 


<!-- It would be good to have real example of this powering --> 

## Radio Control

A remote control (RC) radio system is required if you want to *manually* control your vehicle (PX4 does not require a radio system for autonomous flight modes). 

You will need to [select a compatible transmitter/receiver](../getting_started/rc_transmitter_receiver.md) and then *bind* them so that they communicate (read the instructions that come with your specific transmitter/receiver). 

The instructions below show how to connect the different types of receivers to Pixhawk 4:

- PPM must connect to the **PPM RC** input port.
  ![Pixhawk 4 - Radio port for PPM receivers](../../images/pixhawk_4_receiver_ppm.jpg)
- PWM receivers must connect to the **PPM RC** input port *via* a PPM encoder 
  [like this one](http://www.getfpv.com/radios/radio-accessories/holybro-ppm-encoder-module.html) (PPM receivers use a single signal wire for all channels, while PWM receivers have an individual wire for each channel).
- Spektrum/DSM or S.BUS receivers must connect to the **SBUS RC** input.
  ![Pixhawk 4 - Radio port for Spektrum receivers](../../images/pixhawk_4_receiver_sbus.jpg)

For more information about selecting a radio system, receiver compatibility, and binding your transmitter/receiver pair, see: [Remote Control Transmitters & Receivers](../getting_started/rc_transmitter_receiver.md).


## Telemetry Radios (Optional)

Telemetry radios may be used to communicate and control a vehicle in flight from a ground station (for example, you can direct the UAV to a particular position, or upload a new mission). One radio must be connected to your vehicle as shown below. The other is connected to your ground station computer or mobile device (usually by USB).

![Pixhawk/Telemetry Radio](../../images/pixhawk_4_telemetry_radio.jpg)

<!-- what configuration is required once you've set up a radio) -->


## Motors

The mappings between PWM (MAIN)/AUX output ports and motor/servos for all supported air and ground frames are listed in the [Airframe Reference](../airframes/airframe_reference.md).

> **Caution** The mapping is not consistent across frames (e.g. you can't rely on the throttle being on the same output for all plane frames). Make sure to use the correct mapping for your vehicle.

<span></span>
> **Tip** If your frame is not listed in the reference then use a "generic" airframe of the correct type.

<!-- INSERT image of the motor AUX/PWM ports? -->


## Other Peripherals

The wiring and configuration of other components is covered within the topics for individual [peripherals](../peripherals/README.md).


## Configuration

General configuration information is covered in: [Autopilot Configuration](../config/README.md).

QuadPlane specific configuration is covered here: [QuadPlane VTOL Configuration](../config_vtol/vtol_quad_configuration.md)

<!-- what about config of other vtol types and plane. Do the instructions in these ones above apply for tailsitters etc? -->


## Further information

- [Pixhawk Quick Start Guide (Holybro)](https://3dr.com/wp-content/uploads/2017/03/pixhawk-manual-rev7-1.pdf)
- [Pixhawk Series](../flight_controller/pixhawk_series.md)
<!-- - [3DR Pixhawk](https://dev.px4.io/hardware-pixhawk.html) (PX4 DevGuide) -->
