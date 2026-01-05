---
title: Breadboard Design and Verification
---

***Individual Assignment***

## Objectives

In this assignment, you will prototype and test your entire individual hardware design documented in your draft schematic. You must individually demonstrate proficiency in:

1.  Constructing your entire hardware design circuit on a breadboard

2.  Showing each of the sections of your circuit functioning correctly

**This is an individual homework assignment** but you may work with others to determine how to complete the assignment.

**Both a Canvas submission and a live demonstration are required.**

## Resources

-   Canvas Discussion Board

## Prior to Demonstration of Proficiency

1.  Using your hardware design schematic and datasheets for your components as a guide, build the **power supplies** on your breadboard and test them according to Table 1.

2.  Using your schematic and datasheets for your components as a guide, build and test (see Table 1) the remaining sections of your design on your breadboard **one at a time**. **Building the entire circuit without testing each section separately can make debugging significantly more time consuming.** The circuit you build must have circuit design work by you (not pre-made) in order to receive credit.

    1. Power supply

    1. Microcontroller

    1. Wireless module

    1. At least 1 of each type of actuator in your design

    1. At least 1 of each type of sensor in your design

*Table 1. Major Component Test Plan*

+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| **Major Component**                                                                                                              | **Test 1 (25%)**                                                      | **Test 2 (25%)**                                                                   | **Test 3 (50%)**                                                                          |
|                                                                                                                                  |                                                                       |                                                                                    |                                                                                           |
|                                                                                                                                  |                                                                       |                                                                                    | *Demo for full credit*                                                                    |
+==================================================================================================================================+=======================================================================+====================================================================================+===========================================================================================+
| Power Supply                                                                                                                     | Verify voltage at no load with a DMM                                  | Verify voltage with load (using power resistor or actuator)                        | Verify voltage with DMM both with and without load (using power resistor or actuator)     |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| **Microcontroller and Wifi Modules**                                                                                             |                                                                       |                                                                                    |                                                                                           |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Micro-                                                                                                                          | Demonstrate downloading code to the microcontroller                   | Demonstrate turning an LED (or other actuator) on and off with the microcontroller | Demonstrate controlling two LEDs (or other actuators) on and off with the microcontroller |
| controller                                                                                                                       |                                                                       |                                                                                    |                                                                                           |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| ESP32                                                                                                                            | Demonstrate flashing code to the ESP32                                | Demonstrate making an LED blink with the ESP32                                     | Demonstrate controlling an LED connected to the ESP32 from the web or phone app           |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| **Actuators**                                                                                                                    |                                                                       |                                                                                    |                                                                                           |
|                                                                                                                                  |                                                                       |                                                                                    |                                                                                           |
| If your actuator(s) have not arrived, demonstrate the output with a similar actuator, DMM, or oscilloscope                       |                                                                       |                                                                                    |                                                                                           |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Switched (0/1) Output Actuator                                                                                                   | Verify driver signal on/off from microcontroller or Particle with DMM | Verify low-current on/off signal from transistor with DMM                          | Verify high-current on/off signal from transistor with DMM                                |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| PWM Driven Actuator                                                                                                              | Verify duty cycle from microcontroller or Particle with DMM           | Demonstrate controlling an actuator via PWM                                        | Demonstrate controlling an actuator with a different PWM duty cycle                       |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Bidirectional Motor                                                                                                              | Demonstrate motor rotating in one direction                           | Demonstrate motor rotating in opposite direction                                   | Demonstrate motor alternating directions controlled by microcontroller or Particle        |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Stepper Motor                                                                                                                    | Demonstrate motor running at slow speed                               | Demonstrate motor running at fast speed                                            | Demonstrate motor going both directions                                                   |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Speaker                                                                                                                          | Verify analog signal output from DAC in microcontroller or Particle   | Verify analog signal output from amplifier                                         | Verify speaker outputs sound from microcontroller or Particle                             |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| **Major Component**                                                                                                              | **Test 1 (25%)**                                                      | **Test 2 (25%)**                                                                   | **Test 3 (50%)**                                                                          |
|                                                                                                                                  |                                                                       |                                                                                    |                                                                                           |
|                                                                                                                                  |                                                                       |                                                                                    | *Demo for full credit*                                                                    |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| **Sensors**                                                                                                                      |                                                                       |                                                                                    |                                                                                           |
|                                                                                                                                  |                                                                       |                                                                                    |                                                                                           |
| If your sensor(s) have not arrived, simulate each sensor output using a potentiometer or the Particle function generator instead |                                                                       |                                                                                    |                                                                                           |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Analog Sensor                                                                                                                    | Verify pre-amplified sensor signal with oscilloscope or DMM           | Verify post-amplified signal with oscilloscope or DMM                              | Verify microcontroller or Particle can read amplified signal                              |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Digital Sensor                                                                                                                   | Verify power going to sensor with a DMM                               | Verify signal coming out of the sensor with an oscilloscope                        | Verify microcontroller or Particle can read digital signal from the sensor                |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| **Other Major Components Not Listed Above**                                                                                      |                                                                       |                                                                                    |                                                                                           |
|                                                                                                                                  |                                                                       |                                                                                    |                                                                                           |
| Contact your professor prior to the deadline for clarification on an appropriate test plan.                                      |                                                                       |                                                                                    |                                                                                           |
+----------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------+------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+

3.  Update your block diagram and hardware design (including schematic) to match any changes made as a result of verifying the design on a breadboard. *All documents must be up-to-date, easy to read, and consistent with each other.*

## Individual Demonstration of Proficiency

*You must complete the demonstration individually, either in virtual office hours or in virtual class if time permits. Recorded video demonstrations are not permitted.*

1.  Open and share your updated block diagram and schematic. *All documents must be up-to-date, easy to read, and consistent with each other.*

2.  Power up your breadboard(s) and follow the test plan in Table 1 to demonstrate functionality of each section of your design. Demonstrate Test 3 first to automatically receive credit for Tests 1 and 2. Or, demonstrate Tests 1 and/or 2 for partial credit.

## Canvas Submission

**Both a Canvas submission and a live demonstration are required.**

Your final Canvas submission should include:

-   1 PDF of your team's final block diagram

-   1 PDF of your final schematic (see [Packaging a Cadence Schematic Project for Submission to Canvas](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/))

-   1 ZIP file of the schematic project

Additionally, documents submitted to this assignment will be used to update your grade on the [Hardware Design](#) assignment. If you corrected mistakes in your Bill of Materials, Power Budget, or Performance Specifications, please resubmit those as well.

**Your block diagram & schematic must be legible in order to be graded. Rasterized (pixelated) images will receive a 0 if they are illegible. Do not submit screenshots.**

*Do not submit links to Google documents.* It is your responsibility to ensure that your submission to [Canvas](https://canvas.asu.edu) was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to Canvas.


## Grading

+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| **Item**                                                                       |            | **Points** |            |         |
+================================================================================+============+============+============+=========+
| Updated final team block diagram in PDF format only                            | 25         |            |            |         |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| Updated final legible schematic in PDF format only *(required for grading)*    | 50         |            |            |         |
|                                                                                |            |            |            |         |
| *-5 points per schematic mistake up to the maximum, or 0 points if illegible.* |            |            |            |         |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| All completed Cadence schematic files (including OLB) in a single ZIP file     | 25         |            |            |         |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| **Item**                                                                       | **Test 1** | **Test 2** | **Test 3** |         |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| Power Supply                                                                   | 15         | 15         | 30         | 60      |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| ESP32                                                                          | 15         | 15         | 30         | 60      |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| PSoC                                                                           | 15         | 15         | 30         | 60      |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| Sensor                                                                         | 15         | 15         | 30         | 60      |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| Actuator                                                                       | 15         | 15         | 30         | 60      |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+
| **Total**                                                                      |            |            |            | **200** |
+--------------------------------------------------------------------------------+------------+------------+------------+---------+

-   ***Reminder: If you demo Test 3, you automatically receive credit for Tests 1 and 2.***

-   ***The block diagram and schematic must match what is demonstrated in order to receive credit for any part of the assignment.***

## Frequently Asked Questions

**Q:** What if I don't have my parts yet?

**A:** You will need to come up with an alternative to demonstrate the concepts using components in your kit, components you can acquire elsewhere, etc. If you need help figuring out how to "simulate" a particular sensor or actuator in your design, please see a teaching team member during office hours or post a message on the canvas discussion board.

**Q:** For the analog sensor checkoff, tests 2 and 3 are very similar. How do they differ?

**A:** They are basically the same. Test 2 is intended to be reading with an oscilloscope, while Test 3 is intended to be with your own application code. However we will accept reading with the PSoC or ESP32 oscilloscope for both Test 2 and Test 3.
