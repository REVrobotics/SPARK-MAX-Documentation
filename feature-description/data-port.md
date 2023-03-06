# Data Port

Located on the top of the SPARK MAX, the Data Port allows for extra sensor input and future feature development. The connector details can be found below.&#x20;

![](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product\_images/uploaded\_images/dataportpinout.png)

#### Data Port Connector Information

| **Connector Pin** | **Pin Type** | **Pin Function**           |
| ----------------- | ------------ | -------------------------- |
| 1                 | Power        | +3.3V                      |
| 2                 | Power        | +5V                        |
| 3                 | Analog       | Analog Input               |
| 4                 | Digital      | Forward Limit Switch Input |
| 5                 | Digital      | Encoder B                  |
| 6                 | Digital      | Multi-function Pin         |
| 7                 | Digital      | Encoder A                  |
| 8                 | Digital      | Reverse Limit Switch Input |
| 9                 | Digital      | Encoder C / Index          |
| 10                | Ground       | Ground                     |

Using the [SPARK MAX Data Port Breakout Board](data-port.md#spark-max-data-breakout-board-features) ([REV-11-1278](https://www.revrobotics.com/rev-11-1278/)) makes interfacing with the SPARK MAX Data Port easier.&#x20;

## Limit Switch Inputs

SPARK MAX has two limit switch inputs that, when triggered, can independently prevent motion in both the forward and reverse directions. By default, when the pin for the corresponding direction is grounded, SPARK MAX will override any input commands for that direction and force the output into the neutral state. Input commands for the opposite direction will still be processed unless the corresponding limit signal is also triggered.

The default polarity is compatible with Normally Open (NO) style limit switches, who's contacts are shorted together when the switch is pressed. The Limit Switch Inputs can be configured for the opposite polarity using the USB or CAN interfaces. When configured for the opposite polarity, Normally Closed (NC), the limit will be triggered when the pin is left disconnected from ground. In other words, connecting the pin to ground will release the limit. The following table shows these configurations in detail:

#### Limit Switch Operation

![](../.gitbook/assets/spark-max-limit-switch-export.svg)

## Quadrature Encoder Input

The Quadrature Encoder Input on the Data Port is compatible with standard quadrature encoder signals, usually labeled as channel A, channel B, and Index. SPARK MAX shares these signals with the Encoder Port on the output side of the controller, therefore the Index signal is shared with the third brushless encoder signal C. When in Brushless Mode, these Data Port pins cannot be used with an external encoder. See [Alternate Encoder Mode](../operating-modes/using-encoders/alternate-encoder-mode.md) for information on how to configure the SPARK MAX to accept an alternative encoder source when running in Brushless Mode.

When in Brushed Mode, an external encoder can be connected through either the Data Port or the Encoder Port.

The SPARK MAX encoder signals are not pulled high internally. This is to ensure the maximum compatibility with different types of encoders.

## Analog Input

The Analog Port on the SPARK MAX can measure voltages up to 3.3V with 12-bit resolution. The SPARK MAX Data Port Breakout includes a 5V to 3.3V amplifier circuit so that 5V signals can be sensed with the Analog Input pin.

Analog input is supported on firmware versions 1.4.0 and newer.

## Multi-function Pin

This pin is reconfigured when the SPARK MAX is configured in Alternate Encoder Mode.

## Power Rails

The SPARK MAX Data Port can provide both 3.3V and 5V power to connected devices. Please check [Data Port Specifications](../#data-port-specifications) for details on the supply current capabilities of both rails.

## SPARK MAX Data Port Breakout Board - Features

The SPARK MAX Data Port Breakout Board ([REV-11-1278](https://www.revrobotics.com/rev-11-1278/)) makes it easy to connect external sensors to the SPARK MAX Data Port.

* Solder pads for every Data Port pin
* Analog input 5V to 3.3V converter
  * Built-in amplifier maps 0V - 5V analog signals to the native 0V - 3.3V range of the SPARK MAX Analog Input
  * Configurable resistors can bypass the amplifier (move R3 to R4 position)
* Pass-through Data Port connector
  * Connect other sensors with data port compatible cables while using this breakout
* Mounts directly to SPARK MAX
  * No need for a data port cable
  * Securely mounts to the SPARK MAX zip-tie notches
