# Motor Type - Brushed/Brushless Mode

Brushed and brushless DC motors require different motor control schemes based on the differences in their technology. It is possible to damage the SPARK MAX, the motor, or both if the appropriate motor type isn't configured properly. At the moment, the [NEO Brushless Motor](http://www.revrobotics.com/rev-21-1650/) and the [NEO 550 Brushless Motor](http://www.revrobotics.com/rev-21-1651/) are the only FRC-legal brushless motors compatible with the SPARK MAX, so choosing the correct operating mode should be straightforward.

Brushed or brushless motor types can be configured using the Mode Button, CAN, and USB interfaces.

## Configuration with Mode Button

Follow the steps below to switch motor types with the Mode Button. It is recommended that the motor be left disconnected until the correct mode is selected.

{% hint style="info" %}
Use a small screwdriver, straightened paper clip, pen, or other small implement to press the button. Do not use any type of pencil as the pencil lead can break off inside the SPARK MAX.
{% endhint %}

1. Connect the SPARK MAX to main power, not just USB Power.
2. The Status LED will indicate which motor type is configured by blinking yellow or blue for Brushed Mode, or blinking magenta or cyan for Brushless Mode.
3. Press and hold the Mode Button for approximately 3 seconds.
4. After the button has been held for enough time, the Status LED will change and indicate the different motor type.
5. Release the mode button.

{% hint style="info" %}
Please see the [Status LED Colors and Patterns](../status-led.md) in for more details on the Brushed and Brushless Mode colors.
{% endhint %}

## Configuration with USB

Follow the steps below to switch motor types with the USB and the SPARK MAX Client application. Be sure to download and install the [SPARK MAX Client application](../spark-max-client/getting-started-with-the-spark-max-client/) before continuing.

1. Connect the SPARK MAX to your computer using a USB-C cable.
2. Open the SPARK MAX Client application and verify that the application is connected to your SPARK MAX.
3. On the **Basic** tab, select the appropriate motor type under the **Select Motor Type** menu.
4. Click **Update Configuration** and confirm the change.

## Configuration with CAN

Please see the [API Information](../software-resources/spark-max-api-information/) for information on how to configure the SPARK MAX using the CAN interface. 

