# SPARK MAX Client Troubleshooting

### Error During First-time Firmware Update

If this is the first time installing the SPARK MAX Client or connecting a SPARK MAX in Recovery Mode, you may see an error the first time you try to update firmware on your computer. The DFU driver is one of two drivers installed by the Client and is used for updating firmware. It may not install completely until a SPARK MAX in DFU Mode \(Recovery Mode\) is plugged in to the computer.

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
  * Normal operating mode: Device Manager -&gt; Ports \(COM & LPT\) -&gt; USB Serial Device \(COMx\)
  * Recovery mode: Device Manager -&gt; Universal Serial Bus Controllers -&gt; STM Device in DFU Mode
    * If the device shows up with errors or as STM32 BOOTLOADER, try installing the [DFU drivers](https://www.revrobotics.com/content/sw/max/STMDFUDriver.zip) separately.

