# Calibration for MAXSwerve

Before using the MAXSwerve Java or C++ Templates, be sure to calibrate your swerve modules using the [REV Hardware Client](../rev-hardware-client/getting-started-with-the-rev-hardware-client/).

{% embed url="https://www.youtube.com/watch?v=4-uZfALV470" %}

## Calibration Steps

1. Verify you have completely assembled your [MAXSwerve Module](https://docs.revrobotics.com/ion-build-system/build-guides/3in-maxswerve-module) and have the Steering Motor’s (NEO 550) SPARK MAX connected to the MAXSwerve’s Through Bore Encoder with an Absolute Encoder Adapter.

<figure><img src="../.gitbook/assets/maxswerve-complete.png" alt="Fully assembled MAXSwerve Module showing that the absolute encoder adapter is mounted correctly and the through bore encoder is plugged in"><figcaption></figcaption></figure>

2. Install and Open the Latest version of the [REV Hardware Client](../rev-hardware-client/getting-started-with-the-rev-hardware-client/) onto a Windows computer
3. Connect the Steering Motor’s (NEO 550) SPARK MAX directly to your computer via the included USB-C to USB-A cable
4. Select the Steering SPARK MAX and navigate to the **Update Tab** to verify your SPARK MAX has the latest SPARK MAX Firmware (the latest version may be different than what is shown in the image below)

<figure><img src="https://lh4.googleusercontent.com/MUbirXMsUD8MoGZrsHqigB7P83LyGZCaLCqtO3rgkR6jNGVKcGGPBIygUWXGcWOchbuCRB-pOiUwyOjTfY3dwY3LaVlHXScC9DrAu6fg98ddagtML7cIOqNeWt6uW0xRjZDWyosDVc_UK4QTRMAvSJI" alt="REV Hardware Client update tab shown, highlighting where to select the latest version and where to see if the device is up to date"><figcaption></figcaption></figure>

5. Select The Steering SPARK MAX in the sidebar, and select the **AbsoluteEncoder** Tab

{% hint style="info" %}
Steps 6-9 are also included in the REV Hardware Client **AbsoluteEncoder Tab** under the “MAXSwerve Module Calibration” drop-down shown below
{% endhint %}

<figure><img src="https://lh3.googleusercontent.com/EwJu7FuMugaAuTicd4ZKo4-L9JbvmPInU457ENXf8nUEqPirYGV9IK_uP8vwZu0nJaDPHjPePVESDZq8mpaG-SptwpV1lYFw5Gflv02Lbe4XWqIh2VK7T7POTmDAG4Nj76YNFO8yf25VQH3BJmC8K2Y" alt="Absolute Encoder tab in REV Hardware client, the MAXSwerve Module Calibration drop-down is highlighted"><figcaption></figcaption></figure>

6. Put the Calibration Tool on the MAXSwerve module.
   * The Calibration Tool needs to be placed on the MAXSwerve module with the lip facing the module.
   * The MAXSwerve Wheel will only fit in one orientation because of the placement of the wheel's bevel gear. The Calibration tool is not symmetrical, so you will need to align the bevel gear with the side of the cutout indicated with the orange dot in this image.&#x20;

<div>

<figure><img src="../.gitbook/assets/IMG_9306.jpg" alt="MAXSwerve Calibration tool with an orange dot indicating the side of the cutout that the bevel gear slots into. This part of the cutout is a more complex shape with more corners and curves than the other half of the cutout. "><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/IMG_9307.jpg" alt="MAXSwerve Calibration tool correctly mounted to a MAXSwerve Module"><figcaption></figcaption></figure>

</div>

7. Rotate the wheel along with the Calibration Tool until the tool's lip firmly drops into place around the MAXSwerve module's edges. Once this happens, the wheel and Calibration Tool will be unable to rotate freely until the tool's lip has been lifted above the edges of the module.
8. Ensure that the Direction parameter is set to  Inverted in the Duty Cycle Absolute Encoder Settings section above.
9. Click the Set Zero Offset button to calibrate the zero-position of the absolute encoder to this position.

<figure><img src="https://lh6.googleusercontent.com/QF7oltPhOIbpDBacONpEnGPJ5y5vxUle8Fo_nvYOHcnJ3O1Zr7jcdPsV7vn_GoOmbVkN_eOuXVay-pOn-LYLQCZ8pR6bwsTOdatCYr0QqJWqzRbH4s2NAr2iYuAiNzbU-QAUKa_ZmJ2LDPD6WCy4Ucc" alt="Zero Offset button in the REV Hardware Client&#x27;s Absolute Encoder tab is highlighted"><figcaption></figcaption></figure>

## What's Next?

Start driving your MAXSwerve Modules by loading our code templates onto your robot!

### [MAXSwerve Java Template](https://github.com/REVrobotics/MAXSwerve-Java-Template)

### [MAXSwerve C++ Template](https://github.com/REVrobotics/MAXSwerve-Cpp-Template)
