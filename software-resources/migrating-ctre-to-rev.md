# Migrating from CTRE Phoenix to SPARK MAX

{% hint style="info" %}
**We're Updating our Documentation!** For the most up-to-date information about the SPARK MAX and other ION Motor Controllers please check out the following new documentation pages:&#x20;

* [REV ION Brushless ](https://docs.revrobotics.com/brushless)
  * [SPARK MAX Resources](https://docs.revrobotics.com/brushless/links#spark-max-links)
  * [REVLib for SPARK MAX](https://docs.revrobotics.com/brushless/spark-max/revlib)
* [REV Hardware Client Documentation](https://docs.revrobotics.com/rev-hardware-client/)
{% endhint %}

Many teams have been using various CTRE motor controllers such as the Talon SRX and Talon SPX, and have concerns about porting software between platforms. Fortunately the feature set and code required is similar between the two, and porting from one to the other is easy. Below shows the common tasks and the changes required to convert from the code for CTRE Phoenix devices to the SPARK MAX.&#x20;

## JAVA

### Include Library

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
import com.revrobotics.CANEncoder;
import com.revrobotics.CANPIDController;
import com.revrobotics.CANSparkMax;
import com.revrobotics.ControlType;
import com.revrobotics.CANSparkMaxLowLevel.MotorType;
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
import com.ctre.phoenix.motorcontrol.can.*;
import com.ctre.phoenix.motorcontrol.*;
```
{% endtab %}
{% endtabs %}

### Create Object CAN ID 1

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
private CANSparkMax sparkMax = new CANSparkMax(deviceID, MotorType.kBrushless);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```
TalonSRX talonSRX = new TalonSRX(1);
```
{% endtab %}
{% endtabs %}

### Reset Factory Defaults

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
sparkMax.restoreFactoryDefaults();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```
talonSRX.configFactoryDefault();
```
{% endtab %}
{% endtabs %}

### Select Encoder

This is a brushed motor feature and not needed for using brushless motors with SPARK MAX

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
encoder = sparkMax.getEncoder();
encoder.setInverted(false);
sparkMax.setFeedbackDevice(encoder);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
talonSRX.configSelectedFeedbackSensor(FeedbackDevice.CTRE_MagEncoder_Relative, kPIDLoopIdx, Constants.kTimeoutMs);
talonSRX.setSensorPhase(true);
```
{% endtab %}
{% endtabs %}

### Set closed loop constants

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
pidController.setP(kP);
pidController.setI(kI);
pidController.setD(kD);
pidController.setIZone(kIz);
pidController.setFF(kFF);
pidController.setOutputRange(kMinOutput, kMaxOutput);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX.configNominalOutputForward(0, kTimeoutMs);
talonSRX.configNominalOutputReverse(0, kTimeoutMs);
talonSRX.configPeakOutputForward(kMaxOutput, kTimeoutMs);
talonSRX.configPeakOutputReverse(kMinOutput, kTimeoutMs);

talonSRX.config_kF(kPIDLoopIdx, kP, kTimeoutMs);
talonSRX.config_kP(kPIDLoopIdx, kI, kTimeoutMs);
talonSRX.config_kI(kPIDLoopIdx, kD, kTimeoutMs);
talonSRX.config_kD(kPIDLoopIdx, kF, kTimeoutMs);
```
{% endtab %}
{% endtabs %}

### Run Closed Loop Velocity Control

For this example velocity is set at 500 RPM

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
pidController.setReference(500.0, ControlType.kVelocity);
```
{% endtab %}

{% tab title="Phoenix Framework " %}
```java
// Convert from 500 RPM to 'native units'
double VelocityinUnitsPer100ms  = 500.0 * 4096 / 600;
talonSRX.set(ControlMode.Velocity, VelocityinUnitsPer100ms ); 
```
{% endtab %}
{% endtabs %}

### Read RPM of Motor

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
encoder.getVelocity();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX.getSelectedSensorVelocity(kPIDLoopIdx) * 600 / 4096;
```
{% endtab %}
{% endtabs %}

### Read Applied Output Percent

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
sparkMax.getAppliedOutput();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX.getMotorOutputPercent();
```
{% endtab %}
{% endtabs %}

### Run Closed Loop Position Control

This example runs a position control loop for 10 rotations.

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
pidController.setReference(10.0, ControlType.kPosition);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
targetPositionRoations = 10.0 * 4096;
talonSRX.set(ControlMode.Position, targetPositionRotations);
```
{% endtab %}
{% endtabs %}

### Change Units from 'rotations' to 'inches'

This example assumes a 4" wheel on a 15:1 reduction

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
encoder.setPositionFactor(M_PI * 4/15);
```
{% endtab %}

{% tab title="Phoenix Framwork" %}
```java
// No Equivellant
```
{% endtab %}
{% endtabs %}

### Run Closed Loop Position Control for a set distance

This example assumes a 4" wheel on a 15:1 reduction to move 2 feet (24 inches).

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
pidController.setReference(24.0, ControlType.kPosition);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
targetPositionRotations = (M_PI * 4 / 15 * 4096) * 24;
talonSRX.set(ControlMode.Position, targetPositionRotations);
```
{% endtab %}
{% endtabs %}

### Save Parameters

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
// Run after all parameters are set in RobotInit()
sparkMax.burnFlash();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
//Automatic
```
{% endtab %}
{% endtabs %}

### Follow another device

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
sparkMax1.follow(sparkMax2);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX1.follow(talonSRX2);
```
{% endtab %}
{% endtabs %}

### Invert a device

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
sparkMax.setInverted(true);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```
talonSRX.setInverted(true);
```
{% endtab %}
{% endtabs %}

### Configure a limit switch

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
forwardLimit = sparkMax.getForwardLimitSwitch(LimitSwitchPolarity.kNormallyOpen);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX.configForwardLimitSwitchSource(
                                        LimitSwitchSource.LimitSwitchSource_FeedbackConnector,
                                        LimitSwitchNormal.LimitSwitchNormal_NormallyOpen,
                                        kTimeoutMs);
```
{% endtab %}
{% endtabs %}

### Disable a limit switch

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
forwardLimit.EnableLimitSwitch(false);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX.overrideLimitSwitchesEnable(true);
```
{% endtab %}
{% endtabs %}

## C++

### Include Library

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
#include "rev/CANSparkMax.h"
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
#include "ctre/Phoenix.h"
```
{% endtab %}
{% endtabs %}

### Create Object CAN ID 1

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
rev::CANSparkMax sparkMax{1, rev::CANSparkMax::MotorType::kBrushless};
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
TalonSRX* talon = new TalonSRX(1);
```
{% endtab %}
{% endtabs %}

### Reset Factory Defaults

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
sparkMax.RestoreFactoryDefaults();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
talon->ConfigFactoryDefault();
```
{% endtab %}
{% endtabs %}

### Select Encoder

This is a brushed motor feature and not needed for using brushless motors with SPARK MAX.

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
rev::CANEncoder encoder = sparkMax.GetEncoder(rev::CANEncoder::EncoderType::kQuadrature, 4096);
encoder.SetInverted(true);
sparkMax.SetFeedbackDevice(encoder);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
talonSRX->ConfigSelectedFeedbackSensor(FeedbackDevice::CTRE_MagEncoder_Relative, 0, kTimeoutMs);
talonSRX->SetSensorPhase(true);
```
{% endtab %}
{% endtabs %}

### Set closed loop constants

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
rev::CANPIDController pidController = sparkMax.GetPIDController();
pidController.SetFeedbackDevice(encoder);

pidController.SetP(kP);
pidController.SetI(kI);
pidController.SetD(kD);
pidController.SetIZone(kIz);
pidController.SetFF(kFF);
pidController.SetOutputRange(kMinOutput, kMaxOutput);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
talonSRX->ConfigNominalOutputForward(0, kTimeoutMs);
talonSRX->ConfigNominalOutputReverse(0, kTimeoutMs);
talonSRX->ConfigPeakOutputForward(1, kTimeoutMs);
talonSRX->ConfigPeakOutputReverse(-1, kTimeoutMs);

 talonSRX->Config_kF(kPIDLoopIdx, 0.1097, kTimeoutMs);
talonSRX->Config_kP(kPIDLoopIdx, 0.22, kTimeoutMs);
talonSRX->Config_kI(kPIDLoopIdx, 0.0, kTimeoutMs);
talonSRX->Config_kD(kPIDLoopIdx, 0.0, kTimeoutMs);
```
{% endtab %}
{% endtabs %}

### Run Closed Loop Velocity Control

For this example velocity is set at 500 RPM

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
pidController.SetReference(500.0, rev::ControlType::kVelocity);
```
{% endtab %}

{% tab title="Phoenix Framework " %}
```java
"// Convert from 500 RPM to 'native units'
double VelocityinUnitsPer100ms  = 500.0 * 4096 / 600;
talonSRX->Set(ControlMode::Velocity, VelocityinUnitsPer100ms ); 
```
{% endtab %}
{% endtabs %}

### Read RPM of Motor

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
encoder.GetVelocity();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX->GetSelectedSensorVelocity(kPIDLoopIdx) * 600 / 4096;
```
{% endtab %}
{% endtabs %}

### Read Applied Output Percent

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
sparkMax.GetAppliedOutput();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX->GetMotorOutputPercent();
```
{% endtab %}
{% endtabs %}

### Run Closed Loop Position Control

This example runs a position control loop for 10 rotations.

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
pidController.SetReference(10.0, rev::ControlType::kPosition);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
targetPositionRotations = 10.0 * 4096;
talonSRX->Set(ControlMode::Position, targetPositionRotations);;
```
{% endtab %}
{% endtabs %}

### Change Units from 'rotations' to 'inches'

This example assumes a 4" wheel on a 15:1 reduction

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
encoder.SetPositionFactor( M_PI * 4 / 15 );
```
{% endtab %}

{% tab title="Phoenix Framwork" %}
```java
// No Equivellant
```
{% endtab %}
{% endtabs %}

### Run Closed Loop Position Control for a set distance

This example assumes a 4" wheel on a 15:1 reduction to move 2 feet (24 inches).

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
pidController.SetReference(24.0, rev::ControlType::kPosition);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
targetPositionRotations = (M_PI * 4 / 15 * 4096) * 24;
talonSRX->Set(ControlMode::Position, targetPositionRotations);
```
{% endtab %}
{% endtabs %}

### Save Parameters

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
// Run after all parameters are set in RobotInit()
sparkMax.BurnFlash();
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
//Automatic
```
{% endtab %}
{% endtabs %}

### Follow another device

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
sparkMax1.Follow(sparkMax2);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX1->Follow(*talon2);
```
{% endtab %}
{% endtabs %}

### Invert a device

{% tabs %}
{% tab title="REV SPARK MAX" %}
```cpp
sparkMax.SetInverted(true);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```cpp
talonSRX->SetInverted(true);
```
{% endtab %}
{% endtabs %}

### Configure a limit switch

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
rev::CANDigitalInput forwardLimit = sparkMax.GetForwardLimitSwitch(rev::CANDigitalInput::LimitSwitchPolarity::kNormallyOpen);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX->ConfigForwardLimitSwitchSource(
					LimitSwitchSource::LimitSwitchSource_FeedbackConnector,
					LimitSwitchNormal::LimitSwitchNormal_NormallyOpen,
					kTimeoutMs);
```
{% endtab %}
{% endtabs %}

### Disable a limit switch

{% tabs %}
{% tab title="REV SPARK MAX" %}
```java
forwardLimit.EnableLimitSwitch(false);
```
{% endtab %}

{% tab title="Phoenix Framework" %}
```java
talonSRX->OverrideLimitSwitchesEnable(true);
```
{% endtab %}
{% endtabs %}
