---
title: 304 Lab 3 -- Using the PWM Subsystem
---

> **For this assignment, you may work as a team, but must individually demonstrate your working breadboard.

## Objectives

The goal for this homework is to learn how to control MOSFETs and H-bridges for driving high-current actuators and other outputs from the PSoC at different speeds. By the end of this homework you will be able to *individually* demonstrate proficiency in using a bench oscilloscope to measure duty cycle, and in programming the Cypress PSoC 4 Pioneer Kit or BLE Pioneer Kit to output a pulse-width modulation (PWM) signal with a specific duty cycle.

**An individual live demonstration of Parts 1 and 2 of this assignment is required.**

## Resources

* Video Walkthroughs of this Assignment (Thanks to Eric / Xianyao!)
    * [Walkthrough](https://www.youtube.com/watch?v=yOEXPbO044k&feature=youtu.be)
    * [Parts 1 & 2 Demonstration](https://www.youtube.com/watch?v=dv8FdsVaqOA)
    * [Part 3 Demonstration](https://www.youtube.com/watch?v=1mRKnL_nWZg)
* [CY8CKIT-042 evaluation board main page](https://www.infineon.com/cms/en/product/evaluation-boards/cy8ckit-042/), which includes the Prototyping Kit Guide, Schematic, and Example Code Installer
* [CY8CKIT-042-BLE evaluation board main page](https://www.infineon.com/cms/en/product/evaluation-boards/cy8ckit-042-ble-a/), which includes the Prototyping Kit Guide, Schematic, and Example Code Installer
* Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542
* Pulse Width Modulation (PWM)
    * Pulse-width modulation - Scherz & Monk, Sections 13.5.3 and 14.4
    * [PWM Tutorial from AfroTechMods.com](http://www.afrotechmods.com/groovy/PWM_tutorial/PWM_tutorial.htm)
* Oscilloscopes
    * Scherz & Monk, Chapter 7.4
    * [Agilent MSO-X 4024A Oscilloscope User's Guide, pages 35-42 (Auto Scale) and pages 256-264 (Time Measurements)](http://esdresources.blogspot.com/2016/01/peralta-103-resources.html) *-or-*
    * [Agilent MSO 7054A Oscilloscope User's Guide, page 177 (AutoScale) and pages 192-205 (Time Measurements)](http://esdresources.blogspot.com/2016/01/peralta-103-resources.html)
* Transistors
    * Scherz & Monk, Section 4.3.1 - Introduction
    * Scherz & Monk, Section 4.3.4 - MOSFETs
    [MOSFET as a Switch](https://www.electronics-tutorials.ws/transistor/tran_7.html)
* [Canvas](https://canvas.asu.edu) discussion board

## Parts Needed

| **Item**                                              | **Quantity** | **Detail**                                                                                                                                                                                                                                      |
| ----------------------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 5V Power Supply from ICC1 *(optional)*                | 1            |
| CY8CKIT-042 (Pioneer or BLE) PSoC 4 Evaluation Board | 1            |
| USB micro B cable                                     | 1            | Included in PSoC kit                                               |
| AOTF2618L MOSFET driver circuit from ICC3             | 1            | ([Digikey](https://www.digikey.com/product-detail/en/alpha-omega-semiconductor-inc/AOTF2618L/785-1442-5-ND/3603382)) ([datasheet](http://aosmd.com/res/data_sheets/AOTF2618L.pdf))                                                           |
| Benchtop Power Supply                                 | 1            | Available at lab workbenches                                       |
| Benchtop Multimeter                                   | 1            | Available at lab workbenches                                       |


## Prior to Demonstration of Proficiency

*Complete all of the steps below prior to the demonstration of proficiency.*

## Part 1: Using PWM to make an LED "Breathe"

In this section, you will wire and program an LED to "breathe" on and off ([example](https://www.youtube.com/watch?v=HC6_3h8Qfw8)). Follow this guide to complete this Part [PWM Tutorial 1 – Using PWM to make an LED “Breathe”](https://embedded-systems-design.github.io/pwm-tutorial-1/)

### Individual Demonstration of Proficiency Part 1
Show your project and Top Design for Part 1. Compile, download, and demonstrate your solution working with the modified AOTF2618L MOSFET driver circuit. Show the top design and ```main.c``` solution for causing the LED to "breathe" using the PWM component.

## Part 2: Using a Low-Pass Filter with a PWM Signal to Output an Analog Signal

In this part you will use a passive RC filter to convert a switched, digital PWM output to a usable analog signal

* Complete [PWM Tutorial 3 --  Using Low-Pass Filters with PWM Signals](https://embedded-systems-design.github.io/pwm-tutorial-3/)

### Individual Demonstration of Proficiency Part 2
1. Show your project and Top Design for Part 3. Compile, download, and demonstrate your solution working with the low-pass filter circuit shown above using a benchtop oscilloscope. Highlight the solution used in ```main.c``` to generate a signal. (The LED should still breathe and the motors should still move alongside your new solution).

## Part 3: Schematic

### Resources for Part 3

* KiCad$^1$ [Getting Started](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html) Pages on the KiCad$^1$ website:
    * Introduction to KiCad$^1$: [Download and Install](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#download-and-install-kicad)
    * [Basic Concepts and Workflow](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#basic_concepts_and_workflow)
    * [Tutorial 1: Project](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_1_project)
    * [Tutorial 2: Schematic](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_2_schematic)
* [KiCad$^1$](https://embedded-systems-design.github.io/kicad/kicad-schematic-design/) schematic posts:
    * [Symbol Creation](https://embedded-systems-design.github.io/kicad-symbol-creation/)
    * [Schematic Capture](https://embedded-systems-design.github.io/kicad-schematic-capture/)
    * [Common Pin Types and their Meanings](https://embedded-systems-design.github.io/kicad-common-pin-types/)
* [Cadence](https://embedded-systems-design.github.io/cadence/) posts
    * [Creating a custom library in Cadence](https://embedded-systems-design.github.io/creating-a-custom-library-in-cadence/)
    * [Creating a custom schematic symbol in Cadence](https://embedded-systems-design.github.io/creating-a-custom-schematic-symbol-in-cadence/)
    * [Creating a new project in Cadence](https://embedded-systems-design.github.io/creating-a-new-project-in-cadence/)
--------------------------------------------------------------------------------------------------------------------------------------------

1. Create ***both*** schematic used above, in ***one*** file. Following the resources for KiCad$^1$ or Cadence above.
    1. Create your own custom symbol for MOSFET that you are using to complete the assignment.
        * The symbol should include your initials in the symbol name *so that your **initials are visible** when the symbol is added to schematics.*
        * Save your new symbol in the custom library you created in Lab 1 and updated in Lab 2.
    1. Add all other components, including the voltage used, resistors and resistance values selected, etc.

    > *KiCad$^1$:* Wherever possible, use the "US" version of parts, including "R_US" instead of "R", "C_US" instead of "C", and "C_Polarized_US" instead of "C_Polarized", etc.

    <p></p>

    > *Kicad$^1$:* Like the US/International part symbol differences, make sure you use "earth" ground for the ground symbol rather than the default "GND" symbol.

1. Export your schematic to PDF and package your files for submission to Canvas.

    > *KiCad$^1$:* Follow the instructions for [Packaging KiCad$^1$ Files for Submission](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/)<BR>

    <p></p>

    > *Cadence:*Follow the instructions for [Packaging Cadence Files for Submission](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)

## Check that you did all the Individual Demonstration of Proficiency

You must complete the demonstration individually, either in office hours or in class if time permits. **Demonstrations can be done up to the last office hours on the due date noted in Canvas. This assignment can not be demonstrated on Zoom on Saturdays due to the need for an oscilloscope.**  **No late demonstrations will be accepted**

1. Show your project and Top Design for Part 1. Compile, download, and demonstrate your solution working with the modified AOTF2618L MOSFET driver circuit. Show the top design and ```main.c``` solution for causing the LED to "breathe" using the PWM component.
1. Show your project and Top Design for Part 3. Compile, download, and demonstrate your solution working with the low-pass filter circuit shown above using a benchtop oscilloscope. Highlight the solution used in ```main.c``` to generate a signal. (The LED should still breathe and the motors should still move alongside your new solution).

<p></p>

## Canvas Submission

Submit the items below to Canvas by the deadline given (in Canvas). **Do not submit screenshots.** *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted via Canvas.

### PSoC Creator Files

Submit your packaged PSoC Creator workspace (right-click on the Workspace, select "Archive Workspace/Project..." from the contextual menu, and select a Minimal archive) in ZIP format to this assignment on [Canvas](http://canvas.asu.edu) by the deadline in Canvas. Do not submit links to Google documents.

### Schematic Files

Follow the instructions for packaging your schematic ([KiCad$^1$](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/))([Cadence](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)) to create a PDF and ZIP archive (including all library files) for your project. Submit **both** the PDF and ZIP archive as separate documents to this assignment on [Canvas](https://canvas.asu.edu) by the deadline in Canvas.

## Grading

| **Item**                                                                                              | **Points** |
| ----------------------------------------------------------------------------------------------------- | ---------- |
| Demonstration 1: Part 1 (Breathing LED)                                                               | 50         |
| Demonstration 2: Part 2 (Analog Output)                                                               | 75         |
| Separate ZIP file of single PSoC Lab3 Workspace including both projects                               | 75         |
| Legible PDF of Schematic outside of ZIP FILE *(-5 points for each mistake)*                           | 50         |
| Separate ZIP file including updated library and new symbols *(-5 points for each mistake)*            | 50         |
| **Total**                                                                                             | **300**    |

You must submit to Canvas **and** demonstrate your solution in order to receive credit. Late submissions and demonstrations will be graded per the policy in the syllabus.

$^1$ KiCad is only permitted in EGR304
