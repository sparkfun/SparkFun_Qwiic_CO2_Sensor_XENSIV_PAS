---
icon: material/tools
---

Now that we're familiar with the PAS CO2 sensor and other hardware on this breakout, it's time to assemble it into a circuit.

## Qwiic Assembly

SparkFun's Qwiic system makes assembling a circuit a breeze. Simply plug the breakout into your chosen microcontroller with a Qwiic cable. After assembling your circuit, it should look similar to the photo below:



## Soldered Assembly

Those who prefer to use either the UART or PWM interfaces or the other pins broken out on this board should solder wires or header pins to the PTH pins on the side of the board. If you're not familiar with through-hole soldering or would like a refresher, take a look at our Through-Hole Soldering Tutorial:

<div class="grid cards" markdown align="center">

-   <a href="https://learn.sparkfun.com/tutorials/5">
    <figure markdown>
    ![How to Solder: Through-Hole Soldering](https://cdn.sparkfun.com/c/264-148/assets/e/3/9/9/4/51d9fbe1ce395f7a2a000000.jpg)
    </figure>
    </a>
    <a href="https://learn.sparkfun.com/tutorials/5">**How to Solder: Through-Hole Soldering**
    </a>

</div>

### Boost Regulator Interrupt Assembly

The second example in the Examples section demonstrates how to use the PAS CO2's Interrupt pin as an early measurement signal to control the boost regulator's power during measurement periods. If you want to follow along with that example you'll need to tie the INT PTH pin and EN PTH pin together using a jumper like the one shown below or through some other method (wire, breadboard, etc.). The assembly below also includes a PTH LED and resistor as a visual indicator but is not necessary for normal applications.



## Installation Recommendations

For ideal measurements, Infineon has several recommendations for installing the sensor in the final application found in this [application note](). The list below outlines most of them but for complete information, refer to the app note linked above.

* Allow space above the sensor at least 12mm tall with a minimum opening size of 14mm x 14mm.
* Avoid direct airflow in front of the sensor.
* Isolate the sensor from ambient heat sources.
* Isolate the sensor from vibration sources.
* Avoid placing the sensor in direct sunlight.
* Prevent any condensation/water contact with the sensor.