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

Connect the output of a *Power Module* (PM) to one of the **POWER** ports using a 6-wire cable as shown. The PM input will be connected to your LiPo battery, while the main output will supply vehicle ESCs/motors via the power management board that comes in the kit.

The power module supplies the flight controller with power from the battery and also sends information about the analog current and voltage supplied via the module (including both power to the flight controller and to motors etc). 

The image below shows typical power-supply wiring when using Pixhawk 4.

![Pixhawk 4 - Power Module](../../images/pixhawk_4_power_module.jpg)

> **Warning** The power module supplies the flight controller itself, but cannot power servos and other hardware connected to the controller's PWM OUT and AUX OUT ports. For copter this does not matter because the motors are separately powered. 

For vehicles, such as plane or VTOL, where PWM OUT or AUX OUT is attached to devices that draw power (e.g. a servo used in a plane) then you will need to power the PWM OUT or AUX OUT using a [BEC](https://en.wikipedia.org/wiki/Battery_eliminator_circuit) that can be connected to the pins VDD_SERVO and GND of Pixhawk output ports.

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

<span></span>
> **Note** The output rail must be separately powered, as discussed in the [Power](#power) section above.
  
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
