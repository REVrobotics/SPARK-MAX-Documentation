# SPARK MAX Client Troubleshooting

{% hint style="info" %}
**We're Updating our Documentation!** For the most up-to-date information about the SPARK MAX and other ION Motor Controllers please check out the following new documentation pages:&#x20;

* [REV ION Brushless ](https://docs.revrobotics.com/brushless)
  * [SPARK MAX Resources](https://docs.revrobotics.com/brushless/links#spark-max-links)
  * [REVLib for SPARK MAX](https://docs.revrobotics.com/brushless/spark-max/revlib)
* [REV Hardware Client Documentation](https://docs.revrobotics.com/rev-hardware-client/)
{% endhint %}

{% hint style="info" %}
This is **legacy documentation** for our discontinued SPARK MAX Client Software. If you are interested in running a SPARK MAX via a computer, please see our newer documentation: [Getting Started with the REV Hardware Client.](../rev-hardware-client/getting-started-with-the-rev-hardware-client/)
{% endhint %}

### Error During First-time Firmware Update

If this is the first time installing the SPARK MAX Client or connecting a SPARK MAX in Recovery Mode, you may see an error the first time you try to update firmware on your computer. The DFU driver is one of two drivers installed by the Client and is used for updating firmware. It may not install completely until a SPARK MAX in DFU Mode (Recovery Mode) is plugged in to the computer.&#x20;

If you see an error during your first firmware update, please do the following:

1. Close the Client application.
2. Unplug the SPARK MAX from the computer.
3. Plug the SPARK MAX back into the computer.
4. Open the Client application.

Alternatively, you can preemptively finalize the DFU driver installation by following the [Recovery Mode](https://www.revrobotics.com/sparkmax-users-manual/#section-3-5) steps before using the Client for the first time.

We are aware of this issue and will be releasing a fix in a future update of the SPARK MAX Client.

### Troubleshooting

As we get feedback from users and identify exact causes for issues, please look back here for troubleshooting help. If you are running into issues running the SPARK MAX Client try the following **BEFORE** contacting [support@revrobotics.com](mailto:support@revrobotics.com):

* Try running the SPARK MAX Client as an Administrator
* Make sure that Windows is fully up-to-date. Some computers have Windows Update disabled and need to be updated manually.
* Check the Device Manager and verify that the SPARK MAX shows up as one of the following two devices with no caution symbols:
  * Normal operating mode: Device Manager -> Ports (COM & LPT) -> USB Serial Device (COMx)
  * Recovery mode: Device Manager -> Universal Serial Bus Controllers -> STM Device in DFU Mode
    * If the device shows up with errors or as STM32 BOOTLOADER, try installing the [DFU drivers](https://www.revrobotics.com/content/sw/max/STMDFUDriver.zip) separately.
