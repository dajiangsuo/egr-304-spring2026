---
title: Simulating OpAmps in PSPICE
---

***Paired In-Class Checkoff***

## Objectives

The purpose of this assignment is to understand how Op-Amps can be used to amplify the current change in a device and output it as a voltage. This circuit, called a "trans-impedance" or "trans-impedance" circuit, is especially useful when working with *current*-based devices like BJT transistors, photodiodes, and phototransistors. In these devices, their activity is often *"linear"* in the current they output, but highly *"nonlinear"* in the voltage they output. trans-impedance circuits convert current to voltage using an op-amp, and maintain linearity so that your signal stays well-conditioned.

**You may work in pairs (2 people) for this in-class checkoff assignment.**

## Resources

-   Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542 *(**many** circuit design resources)*

-   [Cadence posts](https://embedded-systems-design.github.io/cadence/) on the Embedded Systems Design Resources blog

 

-   Canvas Discussion Board

-   trans-impedance / Trans-impedance Amplfiers

    -   [Wikipedia](https://en.wikipedia.org/wiki/Transimpedance_amplifier)

    -   [What's All This Transimpedance Amplifier Stuff, Anyhow?](https://www.electronicdesign.com/technologies/analog/article/21801223/whats-all-this-transimpedance-amplifier-stuff-anyhow-part-1)

    -   [The Linear and Digital Integrated Circuits Design Primer: TRANSRESISTANCE AMPLIFIER AND TRANSCONDUCTANCE AMPLIFIER](https://www.globalspec.com/reference/67831/203279/4-6-transresistance-amplifier-and-transconductance-amplifier)

-   Videos:

    -   [trans-impedance circuits](https://www.youtube.com/watch?v=PKCmLpazmCc)

    -   [OrCAD How-To: PSpice Simulation Types Tutorial](https://www.youtube.com/watch?v=qhkVgKYoo04)

    -   [PSPICE ORCAD Tutorial Part II: Op-Amps](https://www.youtube.com/watch?v=CD-zpguXuKs)


## Prior to Demonstration of Proficiency

1.  Start "Capture CIS 17.4"

> ![](image15.png)

2.  Create a new project

> ![](image31.png)

3.  Give the project a name and ensure that you have selected "Enable PSpice Simulation"

> ![](image35.png)

4.  In the next dialog box, select "Create a Blank Project"

> ![](image12.png)

5.  In the schematic view that opens select "place part" from the icon tray (often on the right side of your screen)

> ![](image6.png)

6.  In the part window that opens, select "add library"

> ![](image22.png)

7.  Select the "microchip_opamp.olb"

![](image11.png)

8.  From the microchip op-amp library, select the MCP6001. This is the same basic device as the op-amp in your kit, but with only a single op-amp per package

![](image16.png)

9.  Place a "PSpice Ground" element on the schematic. for copying and using with every component that needs it.

![](image7.png)

10. Place a "pulse" ***current source*** on the schematic. *This will be used to simulate the current change in IR phototransistor as, for example, you sweep an IR beam over it.*

![](image32.png)

11. Fill in the following values to the parameters on the screen to create a 2.5mA amplitude, 10Hz, symmetric triangular wave:

+----------------------------------------------------------------------------------------------------------------------------+------------------------+
| ![](image5.png) | I1 (current 1) = 0mA   |
|                                                                                                                            |                        |
|                                                                                                                            | I2 (current 2) = 2.5mA |
|                                                                                                                            |                        |
|                                                                                                                            | TD (time delay) = 20ms |
|                                                                                                                            |                        |
|                                                                                                                            | TR (rise time) = 50ms  |
|                                                                                                                            |                        |
|                                                                                                                            | TF (fall time) = 50ms  |
|                                                                                                                            |                        |
|                                                                                                                            | PW (pulse width) = 0ms |
|                                                                                                                            |                        |
|                                                                                                                            | PER (period) = 100ms   |
+----------------------------------------------------------------------------------------------------------------------------+------------------------+

12. Add a 3.3VDC ***Voltage*** source to your schematic:

![](image21.png)

13. Arrange the rest of your circuit as follows:

![](image5.png)

14. In the simulation icon bar in the top right corner of the screen, select "new simulation profile"

![](image33.png)

15. In the settings window that opens, change the running time from 1000ns to 1000ms

![](image4.png)

16. From the simulation icon bar in the top right corner of the screen, select "voltage/level marker"

![](image5.png)

17. Place two voltage probes on your circuit, one at the output of the op-amp, and one at the v+ input.

![](image9.png)

18. From the simulation icon bar in the top right corner of the screen, select "Run PSpice"

![](image9.png)

19. View the output window that pops up. It should look similar to the plot below:

![](image18.png)

20. Change the resistance of "R3" and re-run the simulation until the output is not "chopped off". *Hint: Use the references listed at the top to understand the relationship between component selection and gain for a trans-impedance circuit*

21. Change the value of I2 for the ***pulse current source*** from 2.5mA to 1.5mA. This is to simulate when your light source is *dimmer* or *further away*. Adjust the resistance of "R3" and re-run the simulation until the output reaches over 3V at its peak but is not "chopped off".

## Demonstration of Proficiency in Pairs

In class, demonstrate the following **live** to a member of the Teaching Team by the end of class:

1.  Working Simulation from Step 18

2.  Properly scaled output from Step 19.

3.  Properly scaled output from Step 20, when I2=1.5mA

**A live demonstration by the end of class is required. No late demonstrations will be accepted.**

## Canvas Submission

**No Canvas submission is required.**

## Grading

+---------------------+------------+
| **Demonstration**   | **Points** |
+=====================+============+
| 1.  Demonstration 1 | 15         |
+---------------------+------------+
| 2.  Demonstration 2 | 5          |
+---------------------+------------+
| 3.  Demonstration 3 | 5          |
+---------------------+------------+
| **Total**           | **25**     |
+---------------------+------------+


### Devices

+------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
| ![](image17.jpg) | ![](image2.jpg)  | ![](image20.jpg) |
|                                                                                                                              |                                                                                                                              |                                                                                                                              |
| Digital Multimeter                                                                                                           | Oscilloscope                                                                                                                 | Power Supply                                                                                                                 |
|                                                                                                                              |                                                                                                                              |                                                                                                                              |
| (Not Used)                                                                                                                   | (Not Used)                                                                                                                   | (Not Used)                                                                                                                   |
+==============================================================================================================================+==============================================================================================================================+==============================================================================================================================+
| ![](image8.jpg)  | ![](image14.jpg) | ![](image13.jpg) |
|                                                                                                                              |                                                                                                                              |                                                                                                                              |
| Function Generator                                                                                                           | Waveform Generator                                                                                                           | Soldering Iron                                                                                                               |
|                                                                                                                              |                                                                                                                              |                                                                                                                              |
| (Not Used)                                                                                                                   | (Not Used)                                                                                                                   | (Not Used)                                                                                                                   |
+------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+

### Probes

+-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
| ![](image1.jpg) | ![](image3.jpg) | ![](image34.jpg) |
|                                                                                                                             |                                                                                                                             |                                                                                                                              |
| Oscilloscope                                                                                                                | Digital Multimeter                                                                                                          | Soldering Iron                                                                                                               |
|                                                                                                                             |                                                                                                                             |                                                                                                                              |
| (Not Used)                                                                                                                  | (Not Used)                                                                                                                  | (Not Used)                                                                                                                   |
+-----------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
