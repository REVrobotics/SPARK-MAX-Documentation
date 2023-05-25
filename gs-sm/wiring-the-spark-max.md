# Wiring the SPARK MAX

## Required Materials

* 12V Battery
* 120A Circuit Breaker
* Power Distribution Panel
* SPARK MAX
* Brushed or Brushless Motor
* USB Type-C Cable

## Prepare the Components

### Test Bed

Using a test bed is an easy way to get started with using the SPARK MAX and verify connections and code. For the initial bring up of the SPARK MAX a test bed with a single SPARK MAX, a brushless or brushed motor, and a [properly wired Power Distribution Panel with breaker](https://docs.wpilib.org/en/stable/docs/getting-started/getting-started-frc-control-system/how-to-wire-a-robot.html#attach-battery-connector-to-pdp) is recommended.&#x20;

### Electrical Connections

The power and motor wires are permanently connected to the SPARK MAX and are not replaceable. So take care not to cut these wires too short. It is highly recommended to install connectors on these wires to simplify both the power and motor connections. A common connector used for this purpose is the Anderson Power Pole connector. Follow our [Anderson Power Pole](../tips-and-tricks/anderson-power-pole-connectors.md) guide for tips on how to properly crimp these connectors.

{% hint style="warning" %}
Make sure power is disconnected or turned off before making any electrical connections on your test bed or robot.
{% endhint %}

Connect the integrated SPARK MAX power leads labeled V+ (red) and V- (black) to an available channel on the Power Distribution Panel. If you need to extend the length of the integrated wires, it is recommended to use 12AWG wire or larger (lower gauge number).

## Motor Connections

The first step is determining the type of motor you wish to connect. The SPARK MAX supports two types of motors: brushed DC and brushless DC. An easy way to determine the motor type is to look at the number of primary (larger) motor wires. Brushed motors only have 2 primary motor wires, while brushless motors have 3 primary wires and additional smaller sensor wires.

![](<../.gitbook/assets/image (5).png>)

### NEO Brushless Motor Connections

Connect the three motor wires; red, black, and white, to the matching SPARK MAX output wires labeled A (red), B (black), and C (white).

![](<../.gitbook/assets/neo-motor-connectors (1).png>)

Next connect the NEO or NEO 550's encoder cable to the port labeled ENCODER just above the output wires.

![](<../.gitbook/assets/neo-encoder-connector (1).png>)

{% hint style="warning" %}
The encoder sensor cable is _**required**_ for the operation of brushless motors with SPARK MAX. The motor will not spin without it.
{% endhint %}

### Brushed DC Motor Connections

Connect the two motor wires, M+ (red) and M- (black), to the SPARK MAX output wires labeled A (red) and B (black).

The third output wire, labeled C (white), is not used when driving a brushed motor and should be secured and insulated. We recommend tying it back with a zip-tie and covering the end with a piece of electrical tape. Do not cut this wire in case you wish to use a brushless motor in the future. In the example below the extra unused motor wire is insulated by the white connector and secured in the block.

![](<../.gitbook/assets/cim-motor-connectors (1).png>)

## Verify Connection

Carefully check all connections before continuing and verify that all colors match. The SPARK MAX can be permanently damaged if the power connection is reversed.

{% hint style="info" %}
Leave the CAN cable disconnected for now, we will wiring this up later.
{% endhint %}

