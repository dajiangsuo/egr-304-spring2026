---
title: 304 LAB 1 -- Power Supplies, Voltage Regulators, Benchtop Multimeters, & Power Supply Schematic Design 
---

> This assignment is a ***paired in-class checkoff***. An **individual** live demonstration is required. You may work in pairs (**one** partner), but must individually demonstrate your working breadboard.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Part 1: Power Supplies, Voltage Regulators, & Benchtop Multimeters
## Objectives

In this assignment, you will learn how to use benchtop power supplies and benchtop multimeters to measure voltage, as well as how to use a datasheet to properly design an adjustable linear voltage regulator circuit to output 5V. This voltage is one of the most common for embedded systems, and will be used in your upcoming assignments.

You must demonstrate with your partner proficiency in:

1. Designing voltage regulator circuits.
1. Using a benchtop multimeter to measure the no-load output voltage of a benchtop power supply.
1. Using a benchtop multimeter to measure the no-load output voltage of a regulator.
1. Using a benchtop multimeter to measure regulator output voltage under load.

> This in-class checkoff requires advance work in order to complete it within one class period. Please read through all datasheets and prepare your circuits as much as possible prior to class time.

## Resources

* Scherz & Monk, Chapter 7: Hands on Electronics
    * Section 7.3: Multimeters

* Scherz & Monk, Chapter 11: Voltage Regulators and Power Supplies

* [BK Precision Triple-Output 30V, 5A Digital Display DC Power Supply (Model 1671)](https://www.bkprecision.com/products/power-supplies/1671A) ([manual](https://bkpmedia.s3.amazonaws.com/downloads/manuals/en-us/1671A_manual.pdf))
* [Agilent Digital Multimeter (Model 34461A)](https://www.keysight.com/us/en/support/34461A/digital-multimeter-6-5-digit-truevolt-dmm.html) ([manual](https://www.dropbox.com/s/futmq59a8ftekqs/Agilent_DMM_34461A.pdf?dl=0))

## Bill of Materials

| **Item**                                 | **Quantity** | **Value(s)**                                                                                                                                                                                                                                                                             |
| ---------------------------------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Breadboard                               | 1            | (from your kit)                                                                                                                                                                                                                                                                          |
| Jumper Wires                             | multiple     | (from your kit)                                                                                                                                                                                                                                                                          |
| LM317BT Variable Output Linear Regulator | 1            | ([DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/LM317BT/5308099)) ([Datasheet](https://www.st.com/content/ccc/resource/technical/document/datasheet/group1/a0/db/e6/9b/6f/9c/45/7b/CD00000455/files/CD00000455.pdf/jcr:content/translations/en.CD00000455.pdf)) |
| Ceramic Capacitor                        | 1            | 0.1 $\mu$F (100nF) ([labeling](https://www.wikihow.com/Read-a-Capacitor))                                                                                                                                                                                                 |
| Ceramic Capacitor                        | 1            | 10 $\mu$F polarized electrolytic                                                                                                                                                                                                                                          |
| 1/4 W Resistor                           | 1            | 2 k$\Omega$                                                                                                                                                                                                                                                               |
| Potentiometer                            | 1            | 10 k$\Omega$                                                                                                                                                                                                                                                              |
| Power Resistor                           | 1            | 5.1$\Omega$ 10W ([DigiKey](https://www.digikey.com/product-detail/en/nte-electronics-inc/10W5D1/2368-10W5D1-ND/11650045)) at workbench during checkoff                                                                                                                                   |
| Barrel (power) jack *(optional)*         | 1            | ([DigiKey](https://www.digikey.com/en/products/detail/cui-devices/PJ-102AH/408448)) ([Datasheet](https://www.cuidevices.com/product/resource/pj-102ah.pdf))                                                                                                                              |

## Prior to Demonstration of Proficiency

| **Critical Information and Concepts**                                                                                                                                                                                                                                                                                                 | **Importance**                                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Within the voltage regulator's datasheet, find the absolute maximum ratings and determine the maximum differential voltage $ V_{i}$ -$ V_{o}$ for the regulator. Given our desire for $ V_{o}$=5V, what is the **maximum** value allowed on $ V_{i}$?                                                                                 | Supplying an input voltage that is too high will damage the voltage regulator                                                                                                                                             |
| Within the datasheet, note the *dropout voltage* in Figure 4. Select the maximum dropout voltage (worst case situation for all current values given). From our desired $ V_{out}$=5V, calculate the minimum input voltage required to drive anything from 20mA to 1.5A.                                                               | Supplying an input voltage that is too low will prevent the regulator from achieving the desired voltage                                                                                                                  |
| Look at the datasheet and determine the minimum output current. Find the resistance between output and ground that achieves this minimum current at your selected voltage.<br>You will need to add a resistor between output and ground **no greater** than this calculated value to achieve the **minimum** required output current. | Some voltage regulators require a little bit of current in order to fully turn on. Without the stated minimum output current, your regulator is not fully operational and the measured output voltages **will** be wrong. |

1. Review [Power Supples 101](https://embedded-systems-design.github.io/power-supplies-101/) to learn what a voltage regulator is, and what types of voltage regulators exist. Discuss with your partner.
1. Open the voltage regulator datasheet and construct on a breadboard the circuit shown below. (This is an adaptation of the circuits shown in the datasheet's Figures 6 and 7).

    > Do not use the example resistances shown in the datasheet.

    ![](image4_9V.png)

    ***Figure 1:** Regulator Circuit adapted from the LM317BT datasheet*

1. Add an additional "minimum current" resistor (value calculated previously) between output and ground (resistor R3 in Figure 1 above). *This is not shown in the datasheet's application circuits.*

    > **Alert:** please make sure that the power supply is disconnected from your breadboard before turning on power. You don't know what the last person set the voltage or current limit to, and this could damage your circuit when you power it up.

1. Turn on the Agilent Digital Multimeter (DMM) and set it to read DC volts (see [page 57 of the manual](https://www.dropbox.com/s/futmq59a8ftekqs/Agilent_DMM_34461A.pdf?dl=0))
1. Turn the ***disconnected*** BK Precision DC power supply on and turn the current control knob all the way down, and then back up a little bit. Set the voltage to within the allowable range you found previously.

    > *The current control feature is helpful to control the amount of current going into a circuit (see [page 8 of the manual](https://bkpmedia.s3.amazonaws.com/downloads/manuals/en-us/1671A_manual.pdf)). Allowing too much current into an incorrect circuit can cause physical damage to PCBs and ICs.*

1. Connect the DMM probes to the power supply probes and confirm that the voltage read on the DMM matches the voltage on the power supply display. Note any discrepancies.
1. **Turn off the power supply.**
1. Now, connect the power supply to your breadboard along the selected power and ground rails.
1. You can now turn the power supply back on. Check the current and the over-current indicator. Is it in an over-current condition? Adjust the current dial until the over-current indicator turns off.

    > *The power supply itself should draw almost no current (less than 20mA). The resistors you have selected should also draw very little current.*

1. For the voltage regulator circuit constructed above, complete the following design and circuit verification steps:
    1. Measure the input voltage to the voltage regulator with the Agilent DMM.<br>*This reading confirms that the power supply is outputting the correct voltage.*
    1. Measure the small-load output voltage of the voltage regulator with the Agilent DMM. Adjust the variable resistor / potentiometer until you achieve the desired 5V output.
    1. **Turn off the power supply.**
    1. Connect a 5.1Ω power resistor from the output of the voltage regulator to ground, in parallel with the other resistor.
    1. **Turn on the power supply.**
    1. *Briefly* measure the voltage across the resistor with your multimeter. **Be careful, the components will get hot.**<br> *This reading tells you how well the voltage regulator works under load. Note how this voltage changes when you gently increase the current limit of the power supply.*
    1. **Turn off the power supply.**
    1. Review [pages 62-63 of the DMM manual](https://www.dropbox.com/s/futmq59a8ftekqs/Agilent_DMM_34461A.pdf?dl=0) to learn how to measure DC current. Then, turn the power supply back on and ***briefly*** measure the current going through the resistor with the DMM. **Be careful, the resistor and/or voltage regulator will get hot.**<br> *This reading confirms how much current the regulator can supply.*
    1. Measure the resistance across the two poles used in the potentiometer. This should be done by removing the potentiometer from the circuit before measuring it with the multimeter.  You can then replace it with an equivalent resistance using fixed resistors and re-test.

   > In Part 2, you will **replace** the potentiometer with a fixed resistor, so be sure to write down the value you obtained before the end of class.

## Individual Demonstration of Proficiency

In class, demonstrate the following **live** to a member of the teaching team by the end of class:

1. Your breadboard fully constructed with regulator circuit.
1. DMM measurement of the output voltage of the regulator circuit under no-load conditions.
1. DMM measurement of the output voltage of the regulator circuit under 5.1Ω load.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Part 2: Power Supply Schematic Design

## Introduction

In this Part, you will use ECAD design tools to draw your first circuits for EGR304.

You must individually demonstrate proficiency in:

1. Using ECAD (electronic computer-aided drafting) to design circuits.

You may use KiCad$^1$ or Cadence to complete this assignment. KiCad$^1$ is an open-source, cross-platform tool that is lighter-weight and a smaller download.

Cadence is a professional-level industry-standard tool that takes time to download (~15 GB), install (>1 hour), and learn. *Please plan accordingly*.



## Resources

* [Video Walkthrough of this Assignment](https://www.youtube.com/watch?v=Ecr9_7v3Qes) (Thanks to Tyler H!)

    > *Note on the video:* the voltage regulator part number is "LM317BT". Professor Aukes's initials are "DMA". Use ***your own initials*** when creating the symbol, not Professor Aukes's.

* The Embedded Systems Design website
    * [KiCad$^1$](https://embedded-systems-design.github.io/kicad/kicad-schematic-design/) schematic posts:
        * [Symbol Creation](https://embedded-systems-design.github.io/kicad-symbol-creation/)
        * [Schematic Capture](https://embedded-systems-design.github.io/kicad-schematic-capture/)
        * [Common Pin Types and their Meanings](https://embedded-systems-design.github.io/kicad-common-pin-types/)
    * [Cadence](https://embedded-systems-design.github.io/cadence/) posts
        * [Creating a custom library in Cadence](https://embedded-systems-design.github.io/creating-a-custom-library-in-cadence/)
        * [Creating a custom schematic symbol in Cadence](https://embedded-systems-design.github.io/creating-a-custom-schematic-symbol-in-cadence/)
        * [Creating a new project in Cadence](https://embedded-systems-design.github.io/creating-a-new-project-in-cadence/)
* KiCad$^1$ [Getting Started](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html) Pages on the KiCad$^1$ website:
    * Introduction to KiCad$^1$: [Download and Install](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#download-and-install-kicad)
    * [Basic Concepts and Workflow](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#basic_concepts_and_workflow)
    * [Tutorial 1: Project](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_1_project)
    * [Tutorial 2: Schematic](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_2_schematic)

* Canvas discussion board

## Bill of Materials

| **Item**                            | **Quantity** | **Details**              |
| :---------------------------------- | :----------- | :----------------------- |
| Voltage Regulator Circuit from ICC1 | 1            | (completed in class)     |
| 1N4007 Diodes                       | 2            | (found in your kit)      |
| 1 µF Tantalum Capacitor             | 1            | (found in your kit)      |

## Assignment

1. Follow the [instructions](https://embedded-systems-design.github.io/kicad-installation-and-setup/) on the Embedded Systems Design website to [install the fall software stack](https://embedded-systems-design.github.io/egr304-software-stack/). Please note that ***installing Cadence is optional*** for EGR304.
1. Learn about ECAD

    > *KiCad$^1$:* Read through the first four sections of the "[Getting started in KiCad$^1$](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html)" tutorials, including installation, concepts and workflow, project, and schematic (linked above).
    >
    > *Cadence:* What is Cadence Schematic Capture? See the [What is Cadence?](https://embedded-systems-design.github.io/what-is-cadence/) and [Cadence Schematic Tutorials](https://embedded-systems-design.github.io/cadence-schematic-tutorials/) pages for an overview of the software product and its features.

1. Update the voltage regulator circuit to include all the protection elements highlighted in the datasheet's Figure 7 (see Figure 1 below). Continue to use the resistance values calculated / identified in ICC1, and swap out the potentiometer for a fixed resistor (or equivalent resistor network) that establishes a fixed 5V output.
1. Create a schematic for your adjustable regulator circuit. Following the resources for KiCad$^1$ or Cadence above, duplicate the regulator circuit that you adapted from ICC1, using all the values of the ***actual resistors used***, *rather than the values given* in the datasheet.
    1. **Create your own custom symbol library** (review the resources above)

    > *KiCad$^1$*: make sure the library is created as a project library. You will need to . ***Put your initials** in the library's file name*.

    1. **Create your own custom symbol** for the adjustable regulator. The symbol should include your initials in the symbol name *so that your **initials are visible** when the symbol is added to schematics.*

    > *KiCad$^1$:* Wherever possible, use the "US" version of parts, including "R_US" instead of "R", "C_US" instead of "C", and "C_Polarized_US" instead of "C_Polarized", etc.
    >
    > *Kicad$^1$:* Like the US/International part symbol differences, make sure you use "earth" ground for the ground symbol rather than the default "GND" symbol.

    1. Review this [short schematic checklist](https://embedded-systems-design.github.io/schematic-checklist/) to ensure your design isn't missing any common mistakes

        ![](image2.png){style="max-height:200px;"}

        ***Figure 1:** Example Regulator Circuit adapted from the LM317BT datasheet, with custom symbol. Use your OWN initials.*

1. Export your schematic to pdf and package your files for submission to Canvas

    > *KiCad$^1$:* Follow the instructions for [Packaging KiCad$^1$ Files for Submission](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/)
    >
    > *Cadence:*Follow the instructions for [Packaging Cadence Files for Submission](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)

## Individual Demonstration of Proficiency

You must complete a live demonstration individually, either in office hours or in class if time permits. Demonstrations can be done up to the last office hours on the due date noted in Canvas.  **No late demonstrations will be accepted**

Demonstrate the following **live** to a member of the teaching team:

1. Your breadboard fully constructed with the updated regulator circuit.
1. DMM measurement of the output voltage of the regulator circuit under small-load conditions (500$\Omega$ ≥ Output load ≥ 100$\Omega$)

## Canvas Submission

Follow the instructions for packaging your schematic ([KiCad$^1$](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/))([Cadence](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)) to create a PDF and ZIP archive (including all library files) for your project. Submit **both** the PDF and ZIP archive as separate documents to this assignment on [Canvas](https://canvas.asu.edu) by the deadline in Canvas. **Do not submit screenshots.** *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to Canvas.

## Grading For PT.2

| **Item**                                                    | **Points** |
| ----------------------------------------------------------- | ---------- |
| Demonstration 1: Completed, updated breadboard              | 25         |
| Demonstration 2: 5V small-load output DMM measurement       | 50         |
| Custom global library file created and included in ZIP file | 25         |
| Custom voltage regulator symbol included in custom library  | 25         |
| Schematic accurately depicted (*-5 points for each error*)  | 150        |
| Legible PDF of schematic included in submission             | 25         |
| **Total**                                                   | **300**    |

You must submit to Canvas **and** demonstrate your solution in order to receive credit. Late submissions and demonstrations will be graded per the policy in the syllabus.


## Devices

| ![](image6.jpg)    | ![](image1.jpg) | ![](image3.jpg) |
| ------------------ | --------------- | --------------- |
| Digital Multimeter | Oscilloscope    | Power Supply    |
| (Used)             | (Not Used)      | (Used)          |

| ![](image8.jpg)    | ![](image2.jpg)    | ![](image11.jpg) |
| ------------------ | ------------------ | ---------------- |
| Function Generator | Waveform Generator | Soldering Iron   |
| (Not Used)         | (Not Used)         | (Not Used)       |

### Probes

| ![](image7.jpg) | ![](image5.jpg)    | ![](image10.jpg) |
| --------------- | ------------------ | ---------------- |
| Oscilloscope    | Digital Multimeter | Soldering Iron   |
| (Not Used)      | (Used)             | (Not Used)       |

<!--

Other content

Go to page six and find the equation for Vo, and the nominal values for IADJ and VREF.

Given a value for R2=2 kOhm, compute the nominal value for variable resistor R1. Verify that this value is less than the value of the potentiometers handed out in class.
-->
