# SPARK MAX Firmware Change Log

It is recommended to keep your SPARK MAX up-to-date with the latest firmware. The SPARK MAX Client application will automatically download the latest firmware, but you can also download the firmware manually below:

| Latest Firmware - Version 1.5.2 |
| :---: |
| [![](../.gitbook/assets/download-latest-firmware.svg)](https://www.revrobotics.com/content/sw/max/firmware/SPARK-MAX-FW-v1.5.2.dfu) |

{% hint style="warning" %}
This firmware **will not work with SPARK MAX beta hardware units** distributed by REV to the SPARK MAX Beta testers. It is only compatible with units received after 12/20/2018.
{% endhint %}

#### Latest Firmware Change Log - Version 1.5.2

* Fixes issue with the _kDataPortConfig_ parameter not enabling Alternate Encoder Mode on a power cycle after it has been configured and saved to flash.
* Improves Gate Driver Fault recovery.

#### Previous Firmware Change Log - Version 1.5.1

* Improvements to BLDC commutation timing.
  * Most noticeable at high RPMs only achievable by the NEO 550.
* Fixes rare case where the SPARK MAX Status LED shows normal driving but no actual output is occurring until a reboot of the controller.

#### Previous Firmware Change Log - Version 1.5.0

* Version 1.5.0 Changes
  * Adds a unique hash key to the firmware. This key is a hashed value based on the unique 96-bit device ID guaranteed to be unique for every STM32 device. The hash value itself is 32-bits to make transmission/reception and on-board comparison easier. It is unlikely for a key collision especially since most buses have only a small number of devices.
  * Adds ID Query command to have all devices which match the CAN ID sent to return their unique hash key. This is typically used to identify all devices with CAN ID 0 but can be used to identify devices with conflicting CAN IDs.
  * Adds ID Assign command, which sends a unique hash key and a CAN ID, which is received by any device whose CAN ID matches the ID field. The device whose unique hash matches has their own CAN ID set to the desired value. This is for initial or automatic provisioning, or to re-address devices with the same CAN ID.
  * Adds identify command which flashes the LED blue/magenta. This command uses the CAN ID, or the unique hash if CAN ID = 0.
  * Complete overhaul of USB interface, creating a generic USB-to-CAN driver connection to act as the bridge to the interface.
  * Adds [Alternate Encoder Mode](http://www.revrobotics.com/sparkmax-users-manual/#section-3-6) for BLDC external encoder support.
  * Adds device manufacturing info to firmware frame.
  * Adds retry frame to CAN bootloader if there is an issue.
* Version 1.4.1 Changes
  * Fixes issue where creating a CANSparkMax object would cause the SensorType parameter to be set to NoSensor.

#### Previous Firmware Change Log - Version 1.4.0

* **Version 1.4.0 Changes**
  * Adds non-competition heartbeat command when not used with a roboRIO.
  * Adds Raspbian support using official WPILib tools.
  * Adds locking mechanism to prevent simultaneous USB and CAN commands.
  * Proportional blink codes now match inversion settings \(i.e. positive input is always green, and negative input is always red\).
  * Limit switch and soft limits now follow inversion settings.
  * Motor controller inversion now in the firmware instead of the API.
  * Adds a configurable range for absolute feedback devices \(currently only applicable to an absolute mode analog sensor\), which also prevents users from setting a setpoint out of range.
  * Adds ability to use both absolute and relative analog sensors as feedback devices
  * Adds filtering for Analog sensor with settings for velocity moving average filter
  * Adds ability to configure how errors are tracked and handled by the user.
    * Calls can be automatically registered and tracked, with any errors displayed to the DriverStation or users can use the _GetLastError\(\)_ after calls to determine if an error has been thrown. This is done by changing the error timeout through _SetCANTimeout\(\)_, where a timeout of 0 means that the calls are non-blocking, and errors are checked in a separate thread and sent through to the driver station.
  * Other minor improvements and bug fixes.
* **Version 1.3.0 Changes**
  * Ability to configure the feedback device for the PIDController.
  * Addition of CANAnalog which will function as a possible feedback device.
  * Added API for using encoders with brushed DC motors.
  * Adds API to enable and set soft limits.
  * All control modes now reset integrator on limit switch activation for long as the limit switch is held.
  * Smart Motion now honors acceleration rate after limit switch changes from triggered to not triggered.
  * Fixes issue where sticky faults can be cleared incorrectly when a new fault is set and the old fault is no longer present.
  * Adds status 3 periodic frame for analog sensor.
  * Other minor improvements and bug fixes.
* **Version 1.2.1 Changes**
  * Adds initial CAN bootloading functionality.
    * Requires continuous power during update and requires USB recovery if the update fails after erasing the flash \(i.e. power is lost during update\).
    * This is not yet integrated into a formal tool, but is exposed in the API. Future versions will allow recovery over CAN.
  * Fix to bus voltage measurement, previous version reported a lower value.
  * Additional accuracy improvements to all ADC measurements.
  * Adds additional filtering to bus voltage.
  * Fix for Follow settings not being reapplied after power cycle.
  * Adds ability to change units for arbFF between voltage and percent bus voltage \(or percent compensated voltage\).

#### Previous Firmware Change Log - Version 1.1.33

* Fixes issue that causes a Gate Driver Fault if the NEO is spinning at a certain speed during power up.
  * e.g. while still moving after a breaker trips for more than ~1.4s after breaker recovery.
* Fixes issue where configuration data can be corrupted under a unique set of conditions, including loss of power while configuration settings are being saved to flash memory.
  * Issue symptoms: Controller cannot be controlled by a normal address and would report a firmware version of 0.0.0 in the Client, even after a successful firmware update. **Updating a controller that is in this state to 1.1.33 will recover the controller.**

#### Previous Firmware Change Log - Version 1.1.31

* Adds new Smart Velocity mode - uses same constrains as the Smart Motion mode but outputs velocity instead of position. This is not a motion profiling mode, but rather provides acceleration limiting as opposed to simple ramp rates.
* Improvements to heartbeat implementation.
* CAN ID of 0 now considered 'unconfigured' and will not be enabled.
* Changes the default output range for all PID slots to be \[-1,1\] instead of \[0,0\]
* Changes setpoint commands to 'stick' instead of relying on periodic frames from the controller.
* Follow mode can now persists through a power-cycle.
* Periodic Status 2 \(position data\) frame rate default changed from 50ms to 20ms.
* Watchdog changed to 220ms.
* Proportional blink codes while driving now have a minimum blink rate \(minimum is same as 10% applied output blink rate\).
* Fault flag 'over voltage' replaced with 'IWDT Reset'.
* Velocity and Position conversion factors are now used for all internal PID calculations.

This firmware update requires an API update. Please see the [API Information](spark-max-api-information/) section for the latest updates. The table below outlines the compatibility between firmware versions and API versions:

![](../.gitbook/assets/api-compatability-table.svg)

#### Previous Firmware Change Log - Version 1.1.26 \(beta\)

* Adds new Smart Motion mode utilizing trapezoidal motion profiling
* Improvements to velocity decoding for low speeds and associated PID control loops requiring control at low speeds
* Improvements to gate driver fault handling
* Adds voltage compensation mode
* Adds ability to set the stored sensor position
* Adds ability to set the maximum PID integral accumulator value to prevent integral windup
* Adds ability to set the PID I accumulator value
* Adds filter function to PID derivative value
* Adds closed-loop current control
* Adds closed-loop ramp rate separate from open-loop
* Adds ability to follow Phoenix 4.11 motor controllers
  * _Note:_ This feature depends on the firmware of the Phoenix controllers, and is not controlled by REV. We will do our best to build this functionality, but this is not an officially supported feature.
* Adds ability to set a unit conversion for both velocity and position units
* Adds ability to reset to factory defaults
* Improvements to smart current limits
* Improvements to current data sent over CAN
* Improvements to internal settings table implementation
* Calling the constructor no longer resets the encoder count. This must be done manually by running CANEncoder.setPosition\(\)

#### Previous Firmware Change Log - Version 1.0.385

* Fixes PWM control issue introduced by version 1.0.384.

#### Previous Firmware Change Log - Version 1.0.384

* Fixes GetPostition\(\) randomly returning 0.
* Fixes momentary velocity spike when accelerating from 0 speed.
* Fixes issue related to rapid control mode switching by the user.
* Fixes issue related to extreme low voltage CAN bus operation.
* Adds conversion for motor temperature.
* Improvement to "Has Reset" flag.
* Improvements to brownout fault indicator.
* Improvements to brownout behavior.

## Factory Images

When updating the SPARK MAX Firmware we recommend using the SPARK MAX Client and the latest firmware file listed in the [firmware changelog](spark-max-firmware-change-log.md). When updating normally, key configuration parameters, such as the CAN ID, will be preserved through an update, preventing the need to reconfigure every time you update. In some rare instances it may be beneficial to completely reinstall the factory firmware and reset all configuration parameters. Factory images can be found below:

* [Factory Image Version 1.1.33](https://www.revrobotics.com/content/sw/max/firmware/SPARK-MAX-Firmware_v1.1.33_FactoryDefaults.dfu)
* [Factory Image Version 1.1.31](https://www.revrobotics.com/content/sw/max/firmware/SPARK-MAX-Firmware_v1.1.31_FactoryDefaults.dfu)
* [Factory Image Version 1.0.385](https://www.revrobotics.com/content/sw/max/firmware/SPARK-MAX-Firmware_v1.0.385_FactoryDefaults.dfu)
* [Factory Image Version 1.0.381](https://www.revrobotics.com/content/sw/max/firmware/SPARK-MAX-Firmware_v1.0.381_FactoryDefaults.dfu)

