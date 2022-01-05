# Navigating the REV Hardware Client

The REV Hardware Client has three tabs to manage different features of the Client. The Hardware Tab is where supported hardware devices are managed. The Downloads Tab allows for the downloading of supported device software for updating when offline. The About Tab has information on what devices are supported, updating the REV Hardware Client, and having issue reporting.&#x20;

Individual devices, like the SPARK MAX, have additional tabs available when the device is selected. For a full overview of the default navigation features of the [REV Hardware Client see the User's Manual](https://docs.revrobotics.com/sparkmax/spark-max-client/getting-started-with-the-spark-max-client/navigating-the-spark-max-client). Below is more information on using the specific features for the SPARK MAX.

## Hardware Tab

The Hardware Tab is used to select devices connected via USB or the USB to CAN bridge for configuration, updates, and more.

![](<../../.gitbook/assets/Hardware Tab - With CAN Bridge.svg>)

Once a SPARK MAX is selected from the Hardware tab a number of device specific tabs will show.

## Basic Tab

The Basic Tab is used to set the most common parameters for the SPARK MAX.

![](<../../.gitbook/assets/SPARK MAX - Basic (modified) (1).svg>)

1. **Device Identify:** Blink the selected SPARK MAX's LED for identification.
2. **CAN ID:** This assigns a SPARK MAX a CAN ID for identification over the CAN BUS. Any configured SPARK MAX **must have** a CAN ID.
3. **Configurations:** This drop down allows you to select pre-existing configurations store on the Windows machine running the SPARK MAX Client or to pull the existing parameters stored on in RAM on the SPARK MAX. This is helpful when configuring multiple motor controllers to the same settings.
4. **Configured Parameters:** Change the motor type, sensor type, idle mode behavior, and more.

## Advanced Tab

The Advanced Tab allows for changing all configurable parameters of the SPARK MAX without needing to set them in code.

![](<../../.gitbook/assets/SPARK MAX - Advanced (modified) (1).svg>)

1. **Search Parameters:** Allows for easy look up of a specific parameter for editing.
2. **Parameter Table:** Select the arrow to show all configurable parameters within a specific group. For more information on each parameter type see [Configuration Parameters](../../software-resources/configuration-parameters.md).

{% hint style="info" %}
Remember to burn the parameters to flash memory before disconnecting the SPARK MAX
{% endhint %}

## Run Tab

The Run Tab allows for the SPARK MAX to operate over USB or a USB to CAN Bridge without the need for a full control system. This is helpful for testing mechanisms and tuning their control loops.

![](<../../.gitbook/assets/SPARK MAX - Run (modified).svg>)

1. **Run:** Choose setpoints to run a motor connected to a SPARK MAX using various modes, including position, velocity, and duty cycle.
2. **PIDF:** Update PIDF parameters on the fly to tune control loops on the SPARK MAX.
3. **View Graph:** Moves the Client over to the Telemetry Tab to show any added signals in graph form when running a SPARK MAX. This is helpful when tuning control loops.

## API Tab

The API tab shows what the current version and latest version of the SPARK MAX APIs are. There are links to installing the current version of WPILib and for installing the SPARK MAX APIs properly.

![](<../../.gitbook/assets/SPARK MAX - API (modified).svg>)

1. **Select Year:** Selects the WPILib release year that is installed for API compatibility.
2. **API Selection:** Ability to choose which language API to download.

## Update Tab

The Update tab shows what version of firmware is on the selected device, if that device is up to date, and update the firmware of the selected device.

![](<../../.gitbook/assets/SPARK MAX - Update CAN ID 1 (modified).svg>)

1. **Download Latest Firmware:** Downloads latest firmware onto the local machine running the Client.
2. **Update Firmware:** Updates the selected device with the latest firmware.
3. **Out-of-date Firmware Warning:** Warning to alert the user there is new firmware available for any connected device.

{% hint style="info" %}
For more information on the firmware updating process see Updating Device Firmware
{% endhint %}
