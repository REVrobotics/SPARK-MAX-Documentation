# SPARK MAX Specifications

The following tables provide the operating and mechanical specifications for the SPARK MAX motor controller.

{% hint style="danger" %}
DO NOT exceed the maximum electrical specifications. Doing so will cause permanent damage to the SPARK MAX and will void the warranty.
{% endhint %}

### Main Electrical Specifications

{% hint style="warning" %}
Continuous operation at 60A may produce high temperatures on the heat sink. Caution should be taken when handling the SPARK MAX if it has been running at higher current level for an extended period of time.
{% endhint %}

{% hint style="warning" %}
If using a battery to power SPARK MAX, make sure the fully charged voltage is below 24V allowing for sustained operation. Some battery chemistries and configurations, including 6S LiPo packs, have a charge voltage above the maximum operating voltage for SPARK MAX.
{% endhint %}

### PWM Input Specifications

|      |                                                                                                                                                                                                               |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| †    | <p>Brushed: between A and B outputs at 100% duty. <br>Brushless: A->B->C direction at 100% duty.</p>                                                                                                          |
| ††   | Neutral corresponds to zero output voltage (0 V) and is either braking or coasting depending on the current idle behavior mode.                                                                               |
| †††  | <p>Brushed:  between A and B outputs at 100% duty.</p><p>Brushless: C->B->A direction at 100% duty.</p>                                                                                                       |
| ‡    | If a valid pulse isn't received within the timeout period, the SPARK MAX will disable its output.                                                                                                             |
| ‡‡   | Input deadband is added to each side of the neutral pulse width. Within the deadband, output state is neutral. The deadband value is configurable using the REV Hardware Client or through the CAN interface. |

### Data Port Specifications

| **Parameter**                      | **Min** | **Typ** | **Max** | **Units** |
| ---------------------------------- | ------- | ------- | ------- | --------- |
| Digital input voltage range †      | 0       | -       | 5       | V         |
| Digital input-high voltage †       | 1.85    | -       | -       | V         |
| Digital input-low voltage †        | -       | -       | 1.36    | V         |
| Analog input voltage range ††      | 0       | -       | 3.3     | V         |
| Analog input (12bit)               | -       | 81      | -       | μV        |
| 5V supply current (I5V) ‡          | -       | -       | 100     | mA        |
| 3.3V supply current (I3.3V)        | -       | -       | 30      | mA        |
| Total supply current (I5V + I3.3V) | -       | -       | 100     | mA        |

|     |                                                                                                          |
| --- | -------------------------------------------------------------------------------------------------------- |
| †   | See [Data Port](feature-description/data-port.md) for more details on the digital pins on the Data Port. |
| ††  | See [Data Port](feature-description/data-port.md) for more details on the analog pin on the Data Port.   |
| ‡   | The 5V supply is shared between the Data Port and Encoder Port.                                          |

### Encoder Port Specifications

| **Parameter**                      | **Min** | **Typ** | **Max** | **Units** |
| ---------------------------------- | ------- | ------- | ------- | --------- |
| Digital input voltage range †      | 0       | -       | 5       | V         |
| Digital input-high voltage †       | 1.85    | -       | -       | V         |
| Digital input-low voltage †        | -       | -       | 1.36    | V         |
| Analog input voltage range ††      | 0       | -       | 3.3     | V         |
| 5V supply current (I5V) ‡          | -       | -       | 100     | mA        |
| 3.3V supply current (I3.3V)        | -       | -       | 30      | mA        |
| Total supply current (I5V + I3.3V) | -       | -       | 100     | mA        |

|    |                                                                                                                |
| -- | -------------------------------------------------------------------------------------------------------------- |
| †  | See [Encoder Port](feature-description/encoder-port.md) for more details on the digital pins on the Data Port. |
| †† | See [Encoder Port](feature-description/encoder-port.md) for more details on the analog pin on the Data Port.   |
| ‡  | The 5V supply is shared between the Data Port and Encoder Port.                                                |

### Mechanical Specifications

| **Parameter**               | **Min** | **Typ** | **Max** | **Units** |
| --------------------------- | ------- | ------- | ------- | --------- |
| Body length                 | -       | 70      | -       | mm        |
| Body width                  | -       | 35      | -       | mm        |
| Body height                 | -       | 25.5    | -       | mm        |
| Weight                      | -       | 113.3   | -       | g         |
| Power and motor wire gauge  | -       | 12      | -       | AWG       |
| Power and motor wire length | -       | 15      | -       | cm        |
