# Closed Loop Control

{% hint style="info" %}
**We're Updating our Documentation!** For the most up-to-date information about the SPARK MAX and other ION Motor Controllers please check out the following new documentation pages:&#x20;

* [REV ION Brushless ](https://docs.revrobotics.com/brushless)
  * [SPARK MAX Resources](https://docs.revrobotics.com/brushless/links#spark-max-links)
  * [REVLib for SPARK MAX](https://docs.revrobotics.com/brushless/spark-max/revlib)
* [REV Hardware Client Documentation](https://docs.revrobotics.com/rev-hardware-client/)
{% endhint %}

SPARK MAX can operate in several closed-loop control modes, using sensor input to tightly control the motor velocity, position or current. The internal control loop follows a standard PID algorithm with a feed-forward (F) term to compensate for known system offsets.

Additionally, an arbitrary feedforward signal is added to the output of the control loop after _all_ calculations are done. The units for this signal can be selected as either _voltage_ or _duty cycle._ This feature allows more advanced feedforward calculations to be performed by the controller. More details about the types of feedforward calculations can be found on the [WPILib documentation](https://docs.wpilib.org/en/stable/docs/software/advanced-control/controllers/feedforward.html). Using the _voltage_ units for arbitrary feedforward allows the user to send the calculated feedforward voltage from the WPILib API directly to the control loop.

Below is a diagram and the firmware implementation of the internal SPARK MAX PIDF.

![](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product\_images/uploaded\_images/pidfdiagram2.png)

```c
// Synchronous PID, called at 1kHz.
// The output is always in normalized units (i.e. 1 = full forward, -1 = full reverse).
// The setpoint below is always in native units for the corresponding control method (e.g. rotations, RPM, Amps, Volts),
// after any conversion factors have been applied to the setpoint passed to setReference().
// As a result, the constants have the following units:
//   kP, kF: normalized/native
//   kI: normalized/(native*ms)
//   kD: normalized/(native/ms)
//   kMinOutput, kMaxOutput: normalized
//   iZone: native
float pid_run(pid_instance_t* pid, float setpoint, float pv,
        const pid_constants_t* constants)
{
    float error = setpoint - pv;

    float p = error * constants->kP;

    if(fabsf(error) <= constants->iZone || constants->iZone == 0.0f) {
        pid->iState = pid->iState + (error * constants->kI);
    } else {
        pid->iState = 0;
    }

    float d = (error - pid->prev_err);
    pid->prev_err = error;
    d *= constants->kD;

    float f = setpoint * constants->kF;

    float output = p + pid->iState + d + f;
    pid->output = fminf(fmaxf(output,constants->kMinOutput),constants->kMaxOutput);

    return output;
}
```

For more information on utilizing the built-in closed-loop control modes, please take a look at our [SPARK MAX Code Examples](../software-resources/spark-max-code-examples.md).
