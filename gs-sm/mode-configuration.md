# Basic Configurations

{% hint style="info" %}
**We're Updating our Documentation!** For the most up-to-date information about the SPARK MAX and other ION Motor Controllers please check out the following new documentation pages:&#x20;

* [REV ION Brushless ](https://docs.revrobotics.com/brushless)
  * [SPARK MAX Resources](https://docs.revrobotics.com/brushless/links#spark-max-links)
  * [REVLib for SPARK MAX](https://docs.revrobotics.com/brushless/spark-max/revlib)
* [REV Hardware Client Documentation](https://docs.revrobotics.com/rev-hardware-client/)
{% endhint %}

SPARK MAX has many operating modes that can be configured through its CAN and USB interfaces. Additionally, the following basic operating modes can be configured with the MODE button located on the top of the SPARK MAX:&#x20;

* [Idle Behavior](../operating-modes/idle-mode-brake-coast-mode.md): Brake/Coast
* [Motor Type](../operating-modes/motor-type-brushed-brushless-mode.md): Brushed/Brushless

**Mode configuration must be done with power applied to the SPARK MAX.**

{% hint style="info" %}
Configuring the idle behavior and motor type using the mode button is a quick way to set up a SPARK MAX without using a computer. This is most useful when you are controlling the SPARK MAX through its PWM interface or when testing the affect of Braking or Coasting on a mechanism.
{% endhint %}

### Idle Behavior

Whenever the SPARK MAX is receiving a neutral signal (no motor movement) or no signal at all (robot disabled), it can either brake the motor or let it coast. When in Brake Mode, MAX will short the motor wires to each other, electrically braking the motor. This slows the motor down very quickly if it was spinning and makes it harder, but not impossible to back-drive the motor when it is stopped.

* With power turned on, press and release the MODE button to switch between Brake and Coast Mode.
* The STATUS LED will indicate which mode it is in. See the [STATUS LED Colors and Patterns section](../status-led.md#standard-operation) for more information.

### Motor Type

It is very important to have the SPARK MAX configured for the appropriate motor type.&#x20;

{% hint style="danger" %}
Operating in Brushed Mode with a brushless motor connected will permanently damage the motor!
{% endhint %}

With power turned on, press and hold the MODE button for approximately 3 - 4 seconds.

* The STATUS LED will change and indicate which motor type is selected. See the [STATUS LED Colors and Patterns section](../status-led.md#standard-operation) for more information.
* Release the MODE button.
