# Basic Configurations

SPARK MAX has many operating modes that can be configured through its CAN and USB interfaces. Additionally, the following basic operating modes can be configured with the MODE button located on the top of the SPARK MAX:

* Idle Behavior: Brake/Coast
* Motor Type: Brushed/Brushless

**Mode configuration must be done with power applied to the SPARK MAX.**

{% hint style="info" %}
Configuring the idle behavior and motor type using the mode button is a quick way to set up a SPARK MAX without using a computer. This is most useful when you are controlling the SPARK MAX through its PWM interface or when testing the affect of Braking or Coasting on a mechanism.
{% endhint %}

### Idle Behavior

Whenever the SPARK MAX is receiving a neutral signal \(no motor movement\) or no signal at all \(robot disabled\), it can either brake the motor or let it coast. When in Brake Mode, MAX will short the motor wires to each other, electrically braking the motor. This slows the motor down very quickly if it was spinning and makes it harder, but not impossible to back-drive the motor when it is stopped.

* With power turned on, press and release the MODE button to switch between Brake and Coast Mode.
* The STATUS LED will indicate which mode it is in. See the [STATUS LED Colors and Patterns section](../status-led.md#standard-operation) for more information.

### Motor Type

It is very important to have the SPARK MAX configured for the appropriate motor type. 

{% hint style="danger" %}
Operating in Brushed Mode with a brushless motor connected will permanently damage the motor!
{% endhint %}

With power turned on, press and hold the MODE button for approximately 3 - 4 seconds.

* The STATUS LED will change and indicate which motor type is selected. See the [STATUS LED Colors and Patterns section](../status-led.md#standard-operation) for more information.
* Release the MODE button.

