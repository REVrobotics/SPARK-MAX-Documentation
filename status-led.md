# Status LED Patterns

SPARK MAX will indicate important status information on its multi-colored STATUS LED located on the top of its case. The following tables shows each state and the corresponding LED color pattern.

### Standard Operation

| **Operating Mode** | Idle Mode | State | Color/Pattern | Graphic |
| :--- | :--- | :--- | :--- | :--- |
| Brushed     | Brake  | No Signal | Blue Blink  | ![brushed-no-signal-brake.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/brushed-no-signal-brake.gif) |
|  |  | Valid Signal | Blue Solid  | ![blue.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/blue.png) |
|  |  |  |  |  |
|  | Coast  | No Signal | Yellow Blink  | ![brushed-no-signal-coast.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/brushed-no-signal-coast.gif) |
|  |  | Valid Signal | Yellow Solid  | ![yellow.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/yellow.png) |
|  |  |  |  |  |
| Brushless     | Brake  | No Signal | Cyan Blink  | ![brushless-no-signal-brake.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/brushless-no-signal-brake.gif) |
|  |  | Valid Signal  | Cyan Solid  | ![cyan.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/cyan.png) |
|  |  |  |  |  |
|  | Coast  | No Signal  | Magenta Blink  | ![brushless-no-signal-coast.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/brushless-no-signal-coast.gif) |
|  |  | Valid Signal  | Magenta Solid  | ![magenta.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/magenta.png) |
|  |  |  |  |  |
| Partial Forward |  |  | Green Blink | ![forward-proportional.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/forward-proportional.gif) |
| Full Forward  |  |  | Green Solid  | ![green.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/green.png) |
|  |  |  |  |  |
| Partial Reverse |  |  | Red Blink  | ![reverse-proportional.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/reverse-proportional.gif) |
| Full Reverse  |  |  | Red Solid | ![red.png](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/red.png) |
|  |  |  |  |  |
| Forward Limit  |  |  | Green/White Blink | ![forward-limit-triggered.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/forward-limit-triggered.gif) |
| Reverse Limit  |  |  | Red/White Blink  | ![reverse-limit-triggered.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/reverse-limit-triggered.gif) |

###  **Identification, Updating, and Recovery**

| Mode | Color/Pattern | Graphic |
| :--- | :--- | :--- |
| Device Identify | White/Magenta Fast Blink | ![mode-identify.gif](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/mode-identify.gif) |
| CAN Bootloader Firmware Updating | White/Yellow Blink \(v1.5.0\) Green/Magenta Blink \(v1.4.0\) | ![mode-can-bootloader.gif](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/mode-can-bootloader.gif) |
| CAN Bootloader Firmware Retry | White/Blue Blink | ![mode-can-bootloader-retry.gif](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/mode-can-bootloader-retry.gif) |
| USB DFU \(Device Firmware Update\) | Dark \(LED off\) | ![Dark LED](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/off.png) |
| [Recovery Mode](operating-modes/recovery-mode.md) | Dark \(LED off\) | ![Dark LED](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/off.png) |

### Fault Conditions

| **Fault Conditions** | Condition | Color/Pattern | Graphic |
| :--- | :--- | :--- | :--- |
| 12V Missing | The motor will not drive if powered only by USB. This blink code warns the user of this condition. | Orange/Blue Slow Blink | ![fault-no-12v.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/fault-no-12v.gif) |
| Sensor Fault | This fault is only shown when using a brushless motor. This can occur if the sensor type is misconfigured, the sensor cable is not plugged in or damaged, or if a sensor other than the motor sensor is plugged in. | Orange/Magenta Slow Blink  | ![fault-encoder.gif](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/fault-encoder.gif) |
| Gate Driver Fault | A fault reported by the core internal electronic circuitry. If this code persists after power cycling the controller, contact REV. | Orange/Cyan Slow Blink | ![fault-gate-driver.gif](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/fault-gate-driver.gif) |
| CAN Fault | The CAN fault will be shown after the first time the device is plugged into the CAN port and a fault later occurs. Check your CAN wiring if you see this fault. | Orange/Yellow Slow Blink | ![fault-can.gif](https://cdn11.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/fault-can.gif) |
| Corrupt Firmware \(recover using [Recovery Mode](operating-modes/recovery-mode.md)\) | Firmware failed to load. | Dark \(LED off\) | ![Dark LED](https://cdn8.bigcommerce.com/s-t3eo8vwp22/product_images/uploaded_images/off.png) |

