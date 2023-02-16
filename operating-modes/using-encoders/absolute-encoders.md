# Absolute Encoders

The SPARK MAX does not need to be configured to a specific mode to accept input from an absolute encoder as long as the encoder is connected to the SPARK MAX Data Port.&#x20;

#### Absolute Encoder Specifications

| Parameter                    | Specification     |
| ---------------------------- | ----------------- |
| Encoder Output Voltage Level | 5.0V              |
| Encoder Type Supported       | Duty Cycle or PWM |

{% hint style="info" %}
Absolute encoder input is supported by [SPARK MAX Firmware](../../software-resources/spark-max-firmware-change-log.md) Version 1.6.0 and newer,&#x20;
{% endhint %}

## Connecting an Absolute Encoder

Connecting an absolute encoder that is not a Through Bore Encoder will likely require a custom wiring harness or [SPARK MAX Data Port Breakout Board](https://www.revrobotics.com/rev-11-1278/) to connect the necessary encoder power, ground, and signals to the SPARK MAX Data Port. When using an Absolute Encoder use the following pinout information for the Data Port:

![](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product\_images/uploaded\_images/dataportpinout.png)

#### Data Port Connector Information

| **Connector Pin** | **Pin Type** | **Pin Function**           |
| ----------------- | ------------ | -------------------------- |
| 1                 | Power        | +3.3V                      |
| 2                 | Power        | +5V                        |
| 3                 | Analog       | Analog Input               |
| 4                 | Digital      | Forward Limit Switch Input |
| 5                 | Digital      | Encoder B                  |
| 6                 | Digital      | Absolute/PWM Input         |
| 7                 | Digital      | Encoder A                  |
| 8                 | Digital      | Reverse Limit Switch Input |
| 9                 | Digital      | Encoder C / Index          |
| 10                | Ground       | Ground                     |
