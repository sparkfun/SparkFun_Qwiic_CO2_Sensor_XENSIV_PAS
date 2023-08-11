---
icon: material/cog
---

Let's take a closer look at the XENSIV™ PAS CO<sub>2</sub> sensor and other hardware present on this Qwiic breakout.

## XENSIV PAS CO2 Sensor

The XENSIV PAS CO2 sensor from Infineon utilizes a photoacoustic spectroscopy gas measurement system to accurately measure CO<sub>2</sub> concentration in a very stable sensing environment. 


Photoacoustic spectroscopy uses a combination of narrow-band filtered IR light and MEMS microphone to measure CO<sub>2</sub> molecule concentration with high accuracy. The PAS CO<sub>2</sub> package includes an on-board microcontroller that parses the data recorded and converts it into direct parts per million (ppm) output to either UART, I<sup>2</sup>C, or pulse width modulation (PWM). For a complete overview of the PAS CO2, refer to the [datasheet]().

You may be wondering what photoacoustic spectroscopy means. Photoacoustic measuring uses light (photo) and sound/vibrations (acoustic) in tandem to measure the the photoacoustic effect when energy is absorbed by particles. The sensor shines a specific frequency of IR light that CO<sub>2</sub> molecules absorb causing them to heat up, expand and release a pressure wave (sound) wave that the MEMS microphone picks up. This data is then processed and output in human-readable concentrations in PPM. This is just a quick and basic explanation of photoacoustic spectroscopy used in the PAS CO2 sensor. For detailed information, refer to Invensense' [product brief](https://www.infineon.com/cms/en/product/sensor/co2-sensors/#!?fileId=5546d4626b2d8e69016b69ba27c958c1) for the sensor.

<table>
    <tr>
        <th>Parameter</th>
        <th>Units</th>
        <th>Min</th>
        <th>Typ</th>
        <th>Max</th>
        <th>Notes</th>
    </tr>
    <tr>
        <td>CO<sub>2</sub> Output Range</td>
        <td>ppm</td>
        <td>0</td>
        <td>-</td>
        <td>32,000</td>
        <td></td>
    </tr>
    <tr>
        <td>CO<sub>2</sub> Measurement Accuracy</td>
        <td>ppm</td>
        <td>-</td>
        <td>&plusmn;(30 + 3%)</td>
        <td>-</td>
        <td>Accuracy when measuring between 400ppm and 5,000ppm.</td>
    </tr>
</table>

## Power & Boost Circuit

The PAS CO2 uses two input voltages, <b>12V</b> for the IR emitter and <b>3.3V</b> for the microcontroller and other components. This breakout has a boost circuit to step up <b>3.3V</b> from the Qwiic connectors to <b>12V</b> along with a series of decoupling capacitors to ensure the IR emitter gets a clean supply voltage. The breakout also has PTH pins for both supply voltage if users prefer to power the sensor from a dedicated power supply. If you select this option, ensure both voltages fall within the supply range for each input (VDD3.3: <b>3V</b>-<b>3.6V</b> and VDD12: <b>10.8V</b>-<b>13.2V</b>).

## Communication Interfaces & Pinout

We designed this board to set the PAS CO2 to communicate by I<sup>2</sup>C by default but have included PTH pins for both the UART and PWM interfaces along with solder jumpers to enable/disable all three options.

### Qwiic/I<sup>2</sup>C

The board routes the PAS CO2's I<sup>2</sup>C interface to a pair of Qwiic connectors as well as 0.1"-spaced plated through-hole (PTH) headers. This header also includes the Interrupt and Enable pins as well as connections to <b>3.3V</b> and <b>GND</b>. The PAS CO2's unshifted 7-bit I<sup>2</sup>C address is <b>0x28</b>.

### UART

The board routes the TX and RX pins to one side of the board along with a Ground PTH for voltage reference if needed. This interface is disabled by default and requires adjusting the PSEL jumper on the back of the board. Read on to the Solder Jumpers section for more information about enabling UART. 

### PWM

The PAS CO2's PWM interface is routed to the oppposite side of the board from the UART and also includes a Ground PTH for voltage reference. This interface is also disabled by default and can be enabled by adjusting the PWM jumper on the back of the board. Read on to the Solder Jumpers section for more information on enabling PWM output.

## Power LED

The lone LED on this board labeled <b>PWR</b> indicates when the <b>3.3V</b> circuit is powered.

## Solder Jumpers

The breakout has four solder jumpers labeled <b>PWR</b>, <b>PSEL</b>, <b>PWM</b>, and <b>I<sup>2</sup>C</b>.

* <b>PWR</b>: The PWR jumper completes the Power LED circuit. Open it to turn off the power LED to reduce the current draw of the board. 
* <b>PSEL</b>: The PSEL jumper is a three-way jumper that sets whether the PAS CO2 outputs over I<sup>2</sup>C (Default) or UART (Alternate). By default, the jumper pulls the PSEL line to Ground and enables the I<sup>2</sup>C interface indicated by the small "I" on the jumper. Severing the trace between the "I" pad and center pad and then connecting the center pad to the "U" pad switches the PAS CO2 to communicate over UART.
* <b>PWM</b>: The PWM jumper controls the PWM output through the PWM disable input pin.

## Board Dimensions

This breakout measures in a bit larger than the Qwiic 1"x1" standard to accomidate the boost circuit for the IR emitter. The board measures 1"x1.6"(25.4mm x 40.64mm) with four mounting holes that fit a [4-40 screw](https://www.sparkfun.com/products/10453).