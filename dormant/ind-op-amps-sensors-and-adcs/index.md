---
title: Op Amps and Sensors
---

***Individual Assignment***

## Objectives

Infrared (IR) emitters and detectors come as a pair of devices; one is a light source, and the other is a light sensor. They are tuned to emit and detect the same wavelength of light. They can be useful for sending light-based digital messages, detecting objects, or measuring distances. Because they are in the infrared portion of the light spectrum, they are invisible and less likely to be corrupted by visible light sources. See Scherz & Monk Section 5.7.1 for a complete explanation of how phototransistors work.

Operational amplifiers (Op-Amps), on the other hand, are an important part of analog signal processing. They are a fundamental component of many circuits, and knowing how to work with them will make it possible to work with and condition a wide array of non-ideal sensor signals

The goal for this lab is to get to know the basics of op-amps and how to use them in order to properly condition and amplify small signals from sensors such as IR emitter-detector pairs. This will be important as you learn about the often non-ideal behavior of simple passive and active sensors.

At the end of this lab you will be able to demonstrate knowledge of:

1.  The basic rules governing ideal op-amps.

2.  What happens when op-amps are connected with negative feedback in a non-inverting configuration.

3.  How to drive infrared (IR) emitters and read IR detectors.

**This is an individual homework assignment** but you may work with others to determine how to complete the assignment. **A live demonstration of proficiency is required.**


## Resources

-   Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542

    -   Chapter 8 (Op Amps)

        -   Section 8.3: Theory

        -   Section 8.4: Negative Feedback

        -   Section 8.7: Op-Amp Specifications

        -   Section 8.12 Comparators

        -   Section 8.14 Using Single Supply Comparators

    -   Chapter 5 (Optoelectronics)

        -   Section 5.3 Light Emitting Diodes

        -   Section 5.4 Photoresistors

        -   Section 5.5 Photodiodes

        -   Section 5.7 Phototransistors

    -   Chapter 6 (Sensors)

        -   Section 6.4.1 Passive Infrared Sensors

    -   Chapter 7

        -   Section 7.3 Multimeters

        -   Section 7.4 Oscilloscopes

-   Canvas Discussion Board

-   The [Embedded Systems Design](https://embedded-systems-design.github.io/) website

-   Op Amp Links

    -   [Differencing Amplifier](https://www.electronics-tutorials.ws/opamp/opamp_5.html)

-   Supporting Videos:

    -   [Introduction to the Op Amp](https://youtu.be/Q3RMFpGGcZM)

    -   [Non-Inverting Op Amp Circuit](https://youtu.be/_CFR2gViJqo)

    -   [trans-impedance circuits](https://www.youtube.com/watch?v=PKCmLpazmCc)

## Prior to Demonstration of Proficiency

**You will need the following equipment and major components:**

| **Item**                                                                                                                                                                                                                                                                                                                                   | **Quantity / Value** |
|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------------|
| Benchtop Oscilloscope                                                                                                                                                                                                                                                                                                                      | 1                    |
| Benchtop Power Supply                                                                                                                                                                                                                                                                                                                      | (3.3V and 5V)        |
| MCP6002-I/P Op Amp ([datasheet](http://www.microchip.com/mymicrochip/filehandler.aspx?ddocname=en011705)) ([digikey](https://www.digikey.com/product-detail/en/microchip-technology/MCP6002-I-P/MCP6002-I-P-ND/500875))                                                                                                                | 1                    |
| Pushbutton Switch                                                                                                                                                                                                                                                                                                                          | 1                    |
| Capacitor                                                                                                                                                                                                                                                                                                                                  | Various              |
| Emitter/Detector Pair (Amazon [link](https://www.amazon.com/dp/B01MFCFLA7/ref=sspa_dk_detail_0?psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFIMTJJQVdIS0VDSEYmZW5jcnlwdGVkSWQ9QTAzMzkyMjIxQ1dUT0hPWjFLRzJHJmVuY3J5cHRlZEFkSWQ9QTAxNzg1OTMzSDVCMjM4SlVMUFcmd2lkZ2V0TmFtZT1zcF9kZXRhaWwyJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ==)) | 1                    |
| Potentiometer                                                                                                                                                                                                                                                                                                                              | 10 kΩ, 100 kΩ        |

1.  First, read the textbook sections and watch the videos indicated in the Resources section above. **This step is critical for understanding the circuitry you will be designing below.**

![](image2.png)

*Figure 1: A trans-impedance circuit*

2.  Create the infrared emitter/detector circuit shown above, using one of the two op-amps in the MCP6002.

+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ***Tips and Tricks***                                                                                                                                                                                                                             |
|                                                                                                                                                                                                                                                   |
| -   *Make sure to point the emitter (clear) and detector (dark) towards each other in order to transmit more infrared light from the LED to the IR phototransistor.*                                                                              |
|                                                                                                                                                                                                                                                   |
| -   *The V+ and V- pins (4 & 8, on the left of Figure 1) are the power pins for the MCP6002. For this symbol they are drawn and included separately on this schematic. Other symbols may handle common pins differently.*                         |
|                                                                                                                                                                                                                                                   |
| -   *You can use a potentiometer as a **variable resistor** by connecting to the middle wiper pin and **either** of the other two pins (not both).*                                                                                               |
|                                                                                                                                                                                                                                                   |
| -   *You can use a potentiometer as a **voltage divider** by connecting one of the outer pins to ground and the other outer pin to power. The middle wiper pin is then an adjustable, variable voltage that you can adjust from ground to power.* |
|                                                                                                                                                                                                                                                   |
| -   *Try both a 10k and 100kOhm potentiometer at R2 to identify a good gain, or **use your simulation from ICC3** to model this circuit.*                                                                                                         |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

3.  Attach an oscilloscope probe to the Vout1 pin (the output of the op-amp). Ensure that the ground clip is firmly attached to your breadboard's ground using a wire.

4.  In the gap between the emitter and detector, slide something opaque (like a piece of cardboard) between them. How does the voltage at the op-amp's output change?

5.  Using the oscilloscope, identify the minimum and maximum voltage of your signal when the card is inserted and removed. What gain would be required to boost that voltage range to 0-3.3V? What is the minimum voltage you ever see on Vout1? Why does the circuit never go below this minimum value?
    > (***Hint:** Look at Vref*)

![](image2.png)

*Figure 2: A separate "special" amplification stage added after the first stage.*

6.  Remove the emitter and solder two 1-meter (~3ft) wires to the emitter's leads.

7.  Construct the above circuit. This adds a second stage to the original circuit, with a "special" function

> ***Note:** The function of this circuit is discussed in Section 8.4 (Figure 8.14) of Scherz & Monk. Why was this type of amplifier selected?*

8.  Extend the emitter to its full length and shine it towards and away from the IR detector. Now what is the voltage swing? Reduce the value of R2 to achieve a 0V to 3.3V swing (without overly saturating the sensor).

9.  Once selected, measure the output of the constructed circuit with your oscilloscope. How does the signal change as you obstruct the signal and shine the IR beam directly on the detector?

10. Then, using your breadboard wired in HW2, wire Vout2 (the output of the second op-amp) to the Curiosity Nano's analog input pin, *disconnecting the wire from the potentiometer formerly used in HW2.* Connect to the Curiosity Nano over USB with Putty and read the changing analog values in decimal format as you shine your IR emitter at the IR detector.

## Individual Demonstration of Proficiency

*You must complete the demonstration individually, either in office hours or in class if time permits. **Demonstrations can be done up to the last office hours on the due date noted in Canvas.***

1.  Use an oscilloscope to measure the voltage change at Vout1 as you transmit and attenuate light transmission.

2.  Use an oscilloscope to measure the output signal from the infrared emitter-detector circuit at Vout2. The signal should be relatively linear and between 0 and 3.3V when you aim the emitter at the detector from a distance of approximately 1 meter.

3.  Read the voltage output from Vout2 with the Curiosity Nano and display it in decimal form in PuTTY.

## Canvas Submission

No Canvas submission is necessary. Complete your demonstrations by the deadline in the course calendar on [Canvas](https://canvas.asu.edu/). Late demonstrations will be graded per the policy in the syllabus.

## Grading

+-----------------------------------------------------------+------------+
| **Demonstration**                                         | **Points** |
+===========================================================+============+
| 1.  Measure Vout1 and show that it changes with light     | 125        |
+-----------------------------------------------------------+------------+
| 2.  Measure Vout2 and show that it is linear and 0 - 3.3V | 150        |
+-----------------------------------------------------------+------------+
| 3.  Display Vout2 changing in PuTTY                       | 25         |
+-----------------------------------------------------------+------------+
| **Total**                                                 | **300**    |
+-----------------------------------------------------------+------------+
