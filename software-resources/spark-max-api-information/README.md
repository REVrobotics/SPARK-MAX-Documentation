# SPARK MAX API Information

Below you will find information on how to download and install the SPARK MAX APIs for LabVIEW, Java, and C++.

| **Current API version by Language** |  |
| :--- | :--- |
| LabVIEW | 1.5.2 |
| Java | 1.5.4 |
| C++ | 1.5.4 |

#### Latest API Change Log - Version 1.5.4 - Java/C++ Only

* Updated dependencies for WPILib 2021.1.2
* Adds basic simulation support 
* Adds MacOS X support 
* Fixes issue effecting some C++ projects when using static initialization for the SPARK MAX object

#### Latest API Change Log - Version 1.5.2 - Java/C++ Only

* Fixes possible crash when no CAN bus connected when code is first run.
* Adds the CAN ID of the device to every error message.
* Reduces the timing for error messages, and removes repeated messages to make error diagnostics more clear.
* Makes the base class rev::CANSensor object public to help with some Kotlin wrappers.
* Sends an error to the console if two CANSparkMax objects are created with the same CAN ID.

#### Latest API Change Log - Version 1.5.2 - LabVIEW Only

* Fixes issue with Follow.vi not deploying correctly.

#### Previous API Change Log - Version 1.5.1 - Java/C++

* Updated dependencies for WPILib 2020.1.2
* Removed extra thread for setpoint calls.
  * _Set_ calls now directly call _CAN,_ reducing CAN latency.
* Adds _SetVoltage\(\)_ override for the WPILib SpeedController class.

#### Previous API Change Log - Version 1.5.1 - LabVIEW

* Update to LabVIEW 2019 \(FRC 2020\)

#### Previous API Change Log - Version 1.5.0 - All Languages

* Adds the ability to use an alternate encoder as a feedback device when connected to the SPARK MAX Data Port. When using an alternate encoder, Hard Limit Switches cannot be used on that SPARK MAX.
* Adds the ability to send telemetry data back from a SPARK MAX. This is done by opening a Telemetry Stream for a particular subset of telemetry data \(categorized by TelemetryIDs\). A TelemetryMessage contains the ID, value, timestamp, name, units, and bounds of a particular TelemetryID. Additionally, users can list what subset of telemetry data is available for each SPARK MAX.
* Adds a DeviceScanner that will scan the CANBus for other CAN Devices. Will filter what devices to look for, and users can specify filters to let through different devices.
* Addresses bug with CANEncoder backwards compatibility.
* Addresses bug with the Java Control Frame Period not being properly set.

#### Previous API Change Log - Version 1.4.1 - Java/C++ Only

* Fixes issue in Java/C++ where creating a _CANSparkMax_ object causes the Sensor Type parameter to be set to _NoSensor_. Desired behavior is to leave the existing setting.

#### Previous API Change Log - Version 1.4.0 - All Languages

* **Version 1.4.0 Changes**
  * Adds non-competition heartbeat command when not used with a roboRIO.
  * Adds Raspbian support using official WPILib tools.
  * Adds locking mechanism to prevent simultaneous USB and CAN commands.
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
  * Vendor dependencies now allows building Windowsx86-64 based build target.
  * Moves entire implementation to C level, C++ and Java libraries are now simple wrappers. 
  * Adds API to enable and set soft limits.
  * Fixes possible driver set out of bounds if given a CAN ID less than 0. 
  * _CANSparkMaxLowLevel::SetEncPosition\(\)_ and _CANSparkMaxLowLevel::SetIAccum\(\)_ have been moved to protected and should be accessed via their respective objects: _CANEncoder.SetEncoderPosition\(\)_ and _CANPIDController::SetIAccum\(\)_.
  * _CANSparkMaxLowLevel::SetParameter\*_ and G_etParameter\*_ are changed to private.
  * Adds status 3 periodic frame for analog sensor.
  * Other minor improvements and bug fixes.
* **Version 1.2.1 Changes**
  * Adds initial CAN bootloading functionality.
    * Requires continuous power during update and requires USB recovery if the update fails after erasing the flash \(i.e. power is lost during update\).
    * This is not yet integrated into a formal tool, but is exposed in the API. Future versions will allow recovery over CAN.
  * Adds ability to change units for arbFF between voltage and percent bus voltage \(or percent compensated voltage\).
  * API adds check if its own version is too old based on major and minor revision numbers.
  * Adds version number of API.

#### Previous API Change Log - Version 1.1.9 - LabVIEW

* Fixes potential hang in Follow.vi in the case that an error is on the input terminal. Java/C++ unaffected.

#### Previous API Change Log - Version 1.1.9 - Java/C++ Only

* Fixes loop overrun issues in Java/C++. LabVIEW unaffected.

#### Previous API Change Log - Version 1.1.8 - All Languages

* Adds Smart Velocity Mode
* Fixes inversion issues for IMaxAccum and Output Range
* Updates heartbeat implementation
* Adds default slotID for setDFilter\(\) functions
* Update heartbeat rate from 50ms to 25ms
* Changes fault flag for Overvoltage to IWDTReset

This API update also requires a firmware update. Please see the SPARK MAX Firmware Updates section for the latest updates. The table below outlines the compatibility between firmware versions and API versions:

![](../../.gitbook/assets/api-compatability-table.svg)

#### Previous API Change Log - Version 1.1.5 \(beta\) - Java/C++ - Version 1.1.4 \(beta\) - LabVIEW

* Version 1.1.5
  * Adds method to stop any REV periodic frames before enabling heartbeat
  * Improvements to heartbeat protocol
  * Moved all heartbeat implementation into its own dependency called by C++ and Java through JNI
  * Removed setControlFrameRate\(\) call and removed repeating packets
    * Updates to control frames are now as fast/slow as the user calls Set\(\) or SetReference\(\)
  * Updates to doxygen/javadocs comments
  * Maven artifacts now include source for both Java and C++
* Version 1.1.3
  * Improvements to setInverted\(\)
  * New API calls for new firmware features
  * Better error message in Java when CAN is not connected
  * Documentation updates are in progress.

## LabVIEW API

| Latest LabVIEW API - Version 1.5.2 |
| :---: |
| [![](../../.gitbook/assets/download-latest-labview-api.svg)](https://www.revrobotics.com/content/sw/max/labview/rev-spark-max_1.5.2-0_windows_all.nipkg)  |

### LabVIEW API Installation Instructions

1. Download the latest API package from the download link above.
2. Make sure LabVIEW for FRC 2021 is installed and updated.
3. Open the REV SPARK MAX LabVIEW Package. The NI Package Manager should automatically open.
4. Click **Next**:

   ![nipackagemanager.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/nipackagemanager.png)

5. Once the installation is complete, you will be able to access the REV SPARK MAX VIs in the **LabVIEW Functions Pallet -&gt; WPI Robotics Library -&gt; Third Party -&gt; REV Robotics -&gt; SPARK MAX**.

   ![sparkmaxpallet.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/sparkmaxpallet.png)

## Java API

| Latest JAVA API - Version 1.5.4 |
| :---: |
| [![](../../.gitbook/assets/download-latest-java-api.svg) ](https://www.revrobotics.com/content/sw/max/sdk/SPARK-MAX-SDK-v1.5.4.zip) |

### Java API Installation Instructions

**Online Installation**

You can use the online method to install the REV Robotics Java API if your development machine is connected to the internet:

1. Open your robot project in VSCode.
2. Click on the WPI icon in the corner to open the WPI Command Pallet.
3. Select **Manage Vendor Libraries**.
4. Select **Install new library \(online\)**.
5. Enter the following installation URL and press ENTER:

   https://www.revrobotics.com/content/sw/max/sdk/REVRobotics.json

**Offline Installation**

#### Latest Java API - Version 1.5.4

1. Download and unzip the latest SPARK MAX Java API into the _C:\Users\Public\wpilib\2020_ directory on windows and _~/wpilib/2021_ directory on Unix systems.
2. Follow the [Adding an offline-installed Library](https://docs.wpilib.org/en/latest/docs/software/wpilib-overview/3rd-party-libraries.html) instructions from WPI.

#### Java API Documentation

For a list and description of all classes:

* [Online SPARK MAX Java Documentation](https://www.revrobotics.com/content/sw/max/sw-docs/java/index.html)
* [Offline SPARK MAX Java Documentation \(pdf\)](https://www.revrobotics.com/content/sw/max/sw-docs/SPARK-MAX-Java-API-Offline.pdf)

## C++ API

| Latest C++ API - Version 1.5.4 |
| :---: |
| [![](../../.gitbook/assets/download-latest-c++-api.svg) ](https://www.revrobotics.com/content/sw/max/sdk/SPARK-MAX-SDK-v1.5.4.zip) |

### C++ API Installation Instructions

**Online Installation**

You can use the online method to install the REV Robotics C++ API if your development machine is connected to the internet:

1. Open your robot project in VSCode.
2. Click on the WPI icon in the corner to open the WPI Command Pallet.
3. Select **Manage Vendor Libraries**.
4. Select **Install new library \(online\)**.
5. Enter the following installation URL and press ENTER:

   https://www.revrobotics.com/content/sw/max/sdk/REVRobotics.json

**Offline Installation**

#### Latest C++ API - Version 1.5.4

1. Download and unzip the latest SPARK MAX C++ API into the _C:\Users\Public\wpilib\2020_ directory on windows and _~/wpilib/2021_ directory on Unix systems.
2. Follow the [Adding an offline-installed Library](https://docs.wpilib.org/en/latest/docs/software/wpilib-overview/3rd-party-libraries.html) instructions from WPI.

#### C++ API Documentation

For a list and description of all classes:

* [Online SPARK MAX C++ Documentation](https://www.revrobotics.com/content/sw/max/sw-docs/cpp/index.html)
* [Offline SPARK MAX C++ Documentation \(pdf\)](https://www.revrobotics.com/content/sw/max/sw-docs/SPARK-MAX-Cpp-API-Offline.pdf)

