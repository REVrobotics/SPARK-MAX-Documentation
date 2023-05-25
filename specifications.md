# SPARK MAX Specifications

The following tables provide the operating and mechanical specifications for the SPARK MAX motor controller.&#x20;

{% hint style="danger" %}
DO NOT exceed the maximum electrical specifications. Doing so will cause permanent damage to the SPARK MAX and will void the warranty.
{% endhint %}

### Main Electrical Specifications

<table><thead><tr><th>Parameter</th><th>Min</th><th width="230">Typ</th><th>Max</th><th>Units</th></tr></thead><tbody><tr><td>Operating Voltage Range</td><td>5.5</td><td>12</td><td>24</td><td>V</td></tr><tr><td>Absolute Maximum Supply Voltage</td><td>-</td><td>-</td><td>30</td><td>V</td></tr><tr><td>Continuous Output Current</td><td>-</td><td>-</td><td>60*</td><td>A</td></tr><tr><td>Maximum Output Current (2 second surge)</td><td>-</td><td>-</td><td>100</td><td>A</td></tr><tr><td>Output Frequency</td><td>-</td><td>20</td><td>-</td><td>kHz</td></tr></tbody></table>

{% hint style="warning" %}
\*Continuous operation at 60A may produce high temperatures on the heat sink. Caution should be taken when handling the SPARK MAX if it has been running at higher current level for an extended period of time.
{% endhint %}

{% hint style="warning" %}
If using a battery to power SPARK MAX, make sure the fully charged voltage is below 24V allowing for sustained operation. Some battery chemistries and configurations, including 6S LiPo packs, have a charge voltage above the maximum operating voltage for SPARK MAX.
{% endhint %}

### PWM Input Specifications

| Parameter                    | Min | Typ  | Max  | Units |
| ---------------------------- | --- | ---- | ---- | ----- |
| Full-reverse Input Pulse †   | -   | 1000 | -    | μs    |
| Neutral Input Pulse ††       | -   | 1500 | -    | μs    |
| Full-forward Input Pulse ††† | -   | 2000 | -    | μs    |
| Valid Input Pulse Range      | 500 | -    | 2500 | μs    |
| Input Frequency              | 50  | -    | 200  | Hz    |
| Input Timeout ‡              | -   | 50   | -    | ms    |
| Default Input Deadband ‡‡    | -   | 5    | -    | %     |
| Input High Level             | 0.5 | 0.7  | 0.9  | V     |
| Input Voltage Max            | 12  | -    | -    | V     |

|      |                                                                                                                                                                                                               |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| †    | <p>Brushed: between A and B outputs at 100% duty. <br>Brushless: A->B->C direction at 100% duty.</p>                                                                                                          |
| ††   | Neutral corresponds to zero output voltage (0 V) and is either braking or coasting depending on the current idle behavior mode.                                                                               |
| †††  | <p>Brushed:  between A and B outputs at 100% duty.</p><p>Brushless: C->B->A direction at 100% duty.</p>                                                                                                       |
| ‡    | If a valid pulse isn't received within the timeout period, the SPARK MAX will disable its output.                                                                                                             |
| ‡‡   | Input deadband is added to each side of the neutral pulse width. Within the deadband, output state is neutral. The deadband value is configurable using the REV Hardware Client or through the CAN interface. |

### Data Port Specifications

<table data-header-hidden><thead><tr><th width="217">Parameter</th><th width="150">Min</th><th width="200">Typ</th><th>Max</th><th>Units</th></tr></thead><tbody><tr><td><strong>Parameter</strong></td><td><strong>Min</strong></td><td><strong>Typ</strong></td><td><strong>Max</strong></td><td><strong>Units</strong></td></tr><tr><td>Digital input voltage range † </td><td>0</td><td>-</td><td>5</td><td>V</td></tr><tr><td>Digital input-high voltage †</td><td>1.85</td><td>-</td><td>-</td><td>V</td></tr><tr><td>Digital input-low voltage †</td><td>-</td><td>-</td><td>1.36</td><td>V</td></tr><tr><td>Analog input voltage range ††</td><td>0</td><td>-</td><td>3.3</td><td>V</td></tr><tr><td>Analog input (12bit)</td><td>-</td><td>81</td><td>-</td><td>μV</td></tr><tr><td>5V supply current (I5V) ‡</td><td>-</td><td>-</td><td>100 </td><td>mA </td></tr><tr><td>3.3V supply current (I3.3V)</td><td>-</td><td>-</td><td>30</td><td>mA</td></tr><tr><td>Total supply current (I5V + I3.3V)</td><td>-</td><td>-</td><td>100</td><td>mA</td></tr></tbody></table>

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
