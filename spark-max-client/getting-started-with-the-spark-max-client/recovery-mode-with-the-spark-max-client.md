# Recovery Mode with the SPARK MAX Client

{% hint style="info" %}
**We're Updating our Documentation!** For the most up-to-date information about the SPARK MAX and other ION Motor Controllers please check out the following new documentation pages:&#x20;

* [REV ION Brushless ](https://docs.revrobotics.com/brushless)
  * [SPARK MAX Resources](https://docs.revrobotics.com/brushless/links#spark-max-links)
  * [REVLib for SPARK MAX](https://docs.revrobotics.com/brushless/spark-max/revlib)
* [REV Hardware Client Documentation](https://docs.revrobotics.com/rev-hardware-client/)
{% endhint %}

{% hint style="info" %}
This is **legacy documentation** for our discontinued SPARK MAX Client Software. If you are interested in running a SPARK MAX via a computer, please see our newer documentation: [Getting Started with the REV Hardware Client.](../../rev-hardware-client/getting-started-with-the-rev-hardware-client/)
{% endhint %}

When updating the firmware on the SPARK MAX, it is possible for the process to be interrupted or for the firmware to be corrupted by a bad download. In this state, the Status LED will be dark and the SPARK MAX will fail to operate. SPARK MAX has a built-in recovery mode that can force it to accept new firmware even if the controller seems to be bricked. The following procedure requires a small tool, like a straightened paper clip, to press the Mode Button, a USB C cable, and a computer with the [SPARK MAX Client Application](./) installed:&#x20;

1. With the SPARK MAX powered off completely, press and hold the Mode Button.
2. While still holding the Mode Button, connect the SPARK MAX to the computer using the USB cable. The Status LED **will not** illuminate, this is expected.
3. Wait a few seconds for the computer to recognize the connected device, then release the Mode Button.
4. Open the SPARK MAX Client Application. The SPARK MAX will remain dark and it **will not** connect to the Client, this is expected.
5. Navigate to the **Network** tab and click the **Rescan** arrows at the top of the window.
6. The SPARK MAX will be listed under _Devices in Recovery Mode._ Click the checkbox next to the device.
7. Click the **Load Firmware** button.
8. Select the latest firmware file and click **Open**.
9. The firmware should load successfully and the SPARK MAX will now connect to the Client.
