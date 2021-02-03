# Updating Device Firmware

### Updating a Single Device

Follow the steps below to update the firmware on your SPARK MAX:

* Connect your SPARK MAX Motor Controller to your computer with a USB-C cable.
* Open the REV SPARK MAX Client application.
* The Client should automatically scan and connect to your SPARK MAX. If your SPARK MAX is running outdated firmware, you will be notified with a pop-up window like the one pictured below:

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/outdatedfirmware.png)

{% hint style="info" %}
If your SPARK MAX is running firmware older than 1.4.0, you may not see a pop-up and will need to proceed directly to the **Network** tab and click **Scan Bus** manually. 
{% endhint %}

* Click **Open Network Tab & Scan Bus** and proceed to the next step.
* Your SPARK MAX should now be listed in the device list. Click the checkbox next to the SPARK MAX you wish to update, and click **Load Firmware**.

![](../../.gitbook/assets/serial_bridge.png)

{% hint style="info" %}
If your SPARK MAX is listed and you are unable to click the checkbox next to it, you must put your SPARK MAX into [Recovery Mode](../../operating-modes/recovery-mode.md). 
{% endhint %}

* Select the latest firmware file in the firmware directory that the client created on startup. If there isn't a firmware directory, you can also navigate to a file that was downloaded manually. Click **Open** once the appropriate firmware file is selected:

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/firmwareselect.png)

* Click **Yes** to confirm the update.

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/clickyes.png)

* Once complete, the Client will rescan the bus and display the updated controllers.

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/updatecomplete.png)

### Updating Multiple Devices with the USB-to-CAN Bridge

SPARK MAX Firmware Version 1.5.0 includes a USB-to-CAN Bridge feature that allows a single USB-connected SPARK MAX to act as a bridge to the entire CAN bus it is connected to. This allows for configuration and simultaneous updating of multiple SPARK MAX controllers without having to connect to each one individually. Using this feature requires the following:

* A USB-connected SPARK MAX that is updated to firmware version 1.5.0 or newer to act as the Bridge.
* Other SPARK MAXs connected on the CAN bus must be individually updated to firmware version 1.4.0 before they are able to receive mass-updates from the Bridging SPARK MAX.

Once these requirements are satisfied, navigate to the **Network** tab, select the controllers you wish to update, and follow the same firmware update procedure described above starting at Step 4.

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/during-update.png)

When complete, the Client will display the number of successfully updated controllers.

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/fw-confirmation.png)

If a controller fails to update it is usually due to the process being interrupted by a bad power or CAN connection. Severe interruptions can cause the firmware update to be corrupted. A corrupted controller can no longer be updated over the USB-to-CAN Bridge, however, it can be recovered by connecting to the controller directly over USB and putting it in [Recovery Mode](https://www.revrobotics.com/sparkmax-users-manual/#section-3-5).

