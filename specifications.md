# SPARK MAX Specifications

The following tables provide the operating and mechanical specifications for the SPARK MAX motor controller.

{% hint style="danger" %}
DO NOT exceed the maximum electrical specifications. Doing so will cause permanent damage to the SPARK MAX and will void the warranty.
{% endhint %}

### Main Electrical Specifications

| **Parameter** | **Min** | **Typ** | **Max** | **Units** |
| :--- | :---: | :---: | :---: | :---: |
| Operating voltage range \($$V_{IN}$$\) | 5.5 | 12 | 24 | V |
| Absolute maximum supply voltage | - | - | 30 | V |
| Continuous output current | - | - | 60\* | A |
| Maximum output current \(2 second surge\) | - | - | 100 | A |
| Output frequency | - | 20 | - | kHz |

{% hint style="warning" %}
Continuous operation at 60A may produce high temperatures on the heat sink. Caution should be taken when handling the SPARK MAX if it has been running at higher current level for an extended period of time.
{% endhint %}

{% hint style="warning" %}
If using a battery to power SPARK MAX, make sure the fully charged voltage is below 24V allowing for sustained operation. Some battery chemistries and configurations, including 6S LiPo packs, have a charge voltage above the maximum operating voltage for SPARK MAX.
{% endhint %}

### PWM Input Specifications

| **Parameter** | **Min** | **Typ** | **Max** | **Units** |
| :--- | :---: | :---: | :---: | :---: |
| Full-reverse input pulse † | - | 1000 | - | μs |
| Neutral input pulse †† | - | 1500 | - | μs |
| Full-forward input pulse ††† | - | 2000 | - | μs |
| Valid input pulse range | 500 | - | 2500 | μs |
| Input frequency | 50 |  - | 200 | Hz  |
| Input timeout ‡ | - | 50 | - | ms |
| Default Input deadband ‡‡ |  | 5 |  | % |
| Input High Level | 0.5 | 0.7 | 0.9 | V |
| Input Voltage Max | 12 |  |  | V |

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x2020;</td>
      <td style="text-align:left">Brushed: between A and B outputs at 100% duty.
        <br />Brushless: A-&gt;B-&gt;C direction at 100% duty.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2020;&#x2020;</td>
      <td style="text-align:left">Neutral corresponds to zero output voltage (0 V) and is either braking
        or coasting depending on the current idle behavior mode.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2020;&#x2020;&#x2020;</td>
      <td style="text-align:left">
        <p>Brushed: between A and B outputs at 100% duty.</p>
        <p>Brushless: C-&gt;B-&gt;A direction at 100% duty.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2021;</td>
      <td style="text-align:left">If a valid pulse isn&apos;t received within the timeout period, the SPARK
        MAX will disable its output.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2021;&#x2021;</td>
      <td style="text-align:left">Input deadband is added to each side of the neutral pulse width. Within
        the deadband, output state is neutral. The deadband value is configurable
        using the REV Hardware Client or through the CAN interface.</td>
    </tr>
  </tbody>
</table>

### Data Port Specifications

| **Parameter** | **Min** | **Typ** | **Max** | **Units** |
| :--- | :--- | :--- | :--- | :--- |
| Digital input voltage range †  | 0 | - | 5 | V |
| Digital input-high voltage † | 1.85 | - | - | V |
| Digital input-low voltage † | - | - | 1.36 | V |
| Analog input voltage range †† | 0 | - | 3.3 | V |
| 5V supply current \(I5V\) ‡ | - | - | 100  | mA  |
| 3.3V supply current \(I3.3V\) | - | - | 30 | mA |
| Total supply current \(I5V + I3.3V\) | - | - | 100 | mA |

|  |  |
| :--- | :--- |
| † | See [Data Port](feature-description/data-port.md) for more details on the digital pins on the Data Port. |
| ††  | See [Data Port](feature-description/data-port.md) for more details on the analog pin on the Data Port. |
| ‡  | The 5V supply is shared between the Data Port and Encoder Port. |

### Encoder Port Specifications

| **Parameter** | **Min** | **Typ** | **Max** | **Units** |
| :--- | :--- | :--- | :--- | :--- |
| Digital input voltage range † | 0 | - | 5 | V |
| Digital input-high voltage † | 1.85 | - | - | V |
| Digital input-low voltage † | - | - | 1.36 | V |
| Analog input voltage range †† | 0 | - | 3.3 | V |
| 5V supply current \(I5V\) ‡ | - | - | 100  | mA  |
| 3.3V supply current \(I3.3V\) | - | - | 30 | mA |
| Total supply current \(I5V + I3.3V\) | - | - | 100 | mA |

|  |  |
| :--- | :--- |
| † | See [Encoder Port](feature-description/encoder-port.md) for more details on the digital pins on the Data Port. |
| †† | See [Encoder Port](feature-description/encoder-port.md) for more details on the analog pin on the Data Port. |
| ‡ | The 5V supply is shared between the Data Port and Encoder Port. |

### Mechanical Specifications

| **Parameter** | **Min** | **Typ** | **Max** | **Units** |
| :--- | :--- | :--- | :--- | :--- |
| Body length | - | 70 | - | mm |
| Body width | - | 35 | - | mm |
| Body height | - | 25.5 | - | mm |
| Weight | - | 113.3 | - | g |
| Power and motor wire gauge | - | 12 | -  | AWG  |
| Power and motor wire length | - | 15 | - | cm |

