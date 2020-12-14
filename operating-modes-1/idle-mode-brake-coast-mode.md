# Idle Mode - Brake/Coast Mode

When the SPARK MAX is receiving a neutral command the idle behavior of the motor can be handled in two different ways: **Braking** or **Coasting**.

When in **Brake Mode**, the SPARK MAX will effectively short all motor wires together. This quickly dissipates any electrical energy within the motor and brings it to a quick stop.

When in **Coast Mode**, the SPARK MAX will effectively disconnect all motor wires. This allows the motor to spin down at its own rate.

The Idle Mode can be configured using the Mode Button, CAN, and USB interfaces.

### Configuration with Mode Button

Follow the steps below to switch the Idle Mode between Brake and Coast with the Mode Button.

{% hint style="info" %}
Use a small screwdriver, straightened paper clip, pen, or other small implement to press the button. Do not use any type of pencil as the pencil lead can break off inside the SPARK MAX.
{% endhint %}

1. Connect the SPARK MAX to main power, not just USB Power.
2. The Status LED will indicate which Idle Mode is currently configured by blinking blue or cyan for Brake and yellow or magenta for Coast depending on the motor type.
3. Press and release the Mode Button
4. You should see the Status LED change to indicate the selected Idle Mode.

{% hint style="info" %}
Please see the [Status LED Colors and Patterns](../status-led.md) for more details on the Brushed and Brushless Mode colors.
{% endhint %}

### Configuration with USB

Follow the steps below to switch the Idle Mode between Brake and Coast with the USB and the SPARK MAX Client application. Be sure to download and install the [SPARK MAX Client application](../spark-max-client/getting-started-with-the-spark-max-client/) before continuing.

1. Connect the SPARK MAX to your computer using a USB-C cable.
2. Open the SPARK MAX Client application and verify that the application is connected to your SPARK MAX.
3. On the **Basic** tab, select the desired mode with the **Idle Mode** switch.
4. Click **Update Configuration** and confirm the change.

### Configuration with CAN

Please see the [API Information](../software-resources/spark-max-api-information.md) for information on how to configure the SPARK MAX using the CAN interface. 

