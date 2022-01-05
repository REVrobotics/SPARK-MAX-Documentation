# Recovery Mode

When updating the firmware on the SPARK MAX, it is possible for the process to be interrupted or for the firmware to be corrupted by a bad download. In this state, the Status LED will be dark and the SPARK MAX will fail to operate. SPARK MAX has a built-in recovery mode that can force it to accept new firmware even if the controller seems to be bricked. The following procedure requires a small tool, like a straightened paper clip, to press the Mode Button, a USB C cable, and a computer with the [REV Hardware Client](../rev-hardware-client/getting-started-with-the-rev-hardware-client/) installed:&#x20;

* With the SPARK MAX powered off completely, press and hold the Mode Button.
* While still holding the Mode Button, connect the SPARK MAX to the computer using the USB cable. The Status LED **will not** illuminate, this is expected.
* Wait a few seconds for the computer to recognize the connected device, then release the Mode Button.
* Open the REV Hardware Client. The SPARK MAX will remain dark and it **will not** connect to the Client, this is expected.
* Select the SPARK MAX in Recovery Mode from the REV Hardware Client

![](<../.gitbook/assets/Recovery Mode Dectected.svg>)

* Press the Update Button

![](<../.gitbook/assets/Recovery Mode - Update Firmware.svg>)

* Wait for the Firmware Update to complete

![](<../.gitbook/assets/Recovery Mode - Updating.svg>)

* Once completed the SPARK MAX will disconnect then reconnect to the REV Hardware Client. Select the SPARK MAX to start the configuration process

![](<../.gitbook/assets/Recovery Mode - Completed.svg>)

{% hint style="info" %}
The Recovery Mode is also available with the [Legacy SPARK MAX Client](../spark-max-client/getting-started-with-the-spark-max-client/recovery-mode-with-the-spark-max-client.md)
{% endhint %}
