# Updating Device Firmware

### Updating a Single SPARK MAX

* Connect your SPARK MAX Motor Controller to your computer with a USB-C cable.
* Open the REV SPARK MAX Client application.
* The Client should automatically scan and connect to your SPARK MAX.&#x20;

Once the SPARK MAX is connected via USB-C select it within the **Connected Hardware.**&#x20;

![](<../../.gitbook/assets/Hardware Tab - With CAN Bridge (1).svg>)

{% hint style="info" %}
If the SPARK MAX connected via USB-C is running firmware version 1.5.0 or later allows the SPARK MAX to work as a USB to CAN Bridge. Other CAN connected SPARK MAXs running version 1.4.0 can be selected for firmware updates over CAN.
{% endhint %}

Within the Hardware Client, for the SPARK MAX, there are 5 tabs. The Hardware Client will open up on the **Basic** tab. To update firmware select the **Update** tab.&#x20;

![](<../../.gitbook/assets/selecting update tab.svg>)

Under **SPARK MAX Firmware**, select download to download the latest version of the firmware.&#x20;

![](<../../.gitbook/assets/selecting download.svg>)

Once the firmware has downloaded select update.

![](<../../.gitbook/assets/selecting update.svg>)

The update process will flash the firmware image onto the SPARK MAX. The status bar will show the progress of the process.&#x20;

![](<../../.gitbook/assets/writing image.svg>)

Once the firmware update is done your SPARK MAX will show a new status of **Up-to-Date.**

![](<../../.gitbook/assets/up to date.svg>)

{% hint style="info" %}
If your SPARK MAX is running firmware older than 1.4.0, you may need to unplug and replug the USB-C cable into the SPARK MAX for it to reconnect to the Client.&#x20;
{% endhint %}

### Updating Multiple Devices with the USB-to-CAN Bridge

SPARK MAX Firmware Version 1.5.0 includes a USB-to-CAN Bridge feature that allows a single USB-connected SPARK MAX to act as a bridge to the entire CAN bus it is connected to. This allows for configuration and simultaneous updating of multiple SPARK MAX controllers without having to connect to each one individually. Using this feature requires the following:

* A USB-connected SPARK MAX that is updated to firmware version 1.5.0 or newer to act as the Bridge.
* Other SPARK MAXs connected on the CAN bus must be individually updated to firmware version 1.4.0 before they are able to receive mass-updates from the Bridging SPARK MAX.

Once these requirements are satisfied, navigate to the **Hardware** tab, select the **Update All** button.

![](<../../.gitbook/assets/Hardware Tab - Update All CAN Bridge.svg>)

Each device with the Out-of-Date warning will update with the latest version of the firmware.
