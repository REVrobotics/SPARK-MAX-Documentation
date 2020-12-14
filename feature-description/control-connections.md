# Control Connections

The SPARK MAX can be controlled by three different interfaces, servo-style PWM, controller area network \(CAN\), and USB. The following sections describe the physical connections to these interfaces in detail. For details on the operation and protocols of the PWM, CAN, and USB interfaces, please see the [section on Control Interfaces](../operating-modes-1/control-interfaces.md).

## CAN/PWM Port

The CAN/PWM Port is located on the power input side of the SPARK MAX. This port can be connected to either a servo-style PWM signal or a CAN bus with other devices. Connector details can be found below.

![](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/can-pwm-portpinout.png)

#### CAN/PWM Port Connector Information

| Connector Pin | CAN Function | PWM Function |
| :--- | :--- | :--- |
| 1 | CAN High | Signal |
| 2 | CAN Low | Ground |
| 3 | CAN High | Signal |
| 4 | CAN High | Ground |

#### Matting Connector Information

| **Description** | **Manufacturer** | **Part Number** | **Vendor** | **Vendor P/N** |
| :--- | :--- | :--- | :--- | :--- |
| JST-PH 4-pin Housing | JST | PHR-4 | DigiKey | [455-1164-ND](https://www.digikey.com/products/en?keywords=455-1164-ND) |
| JST-PH Contact | JST | SPH-002T-P0.5L | DigiKey | [455-2148-1-ND](https://www.digikey.com/products/en?keywords=455-2148-1-ND) |
| Recommended Crimping Tool | IWISS | SN-2549 | Amazon | [SN-2549](https://www.amazon.com/IWISS-Crimping-AWG28-18-Ratcheting-Connector/dp/B01N4L8QMW/ref=sr_1_2?ie=UTF8&qid=1546882885&sr=8-2&keywords=sn-2549) |

Identical-function pins are electrically connected inside the SPARK MAX, therefore the CAN daisy-chain is completed internally and any two signal and ground pairs can be used for PWM. 

## USB-C Port

The USB-C Port is located on the power input side of the SPARK MAX. It supports USB 2.0 and 5V power for the SPARK MAX's internal microcontroller. While you can configure the SPARK MAX without main power, you will not be able to spin a motor.

