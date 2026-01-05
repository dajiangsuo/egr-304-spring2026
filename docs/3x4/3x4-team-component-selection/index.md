---
title: Component Selection
---

***Team Assignment***

## Objectives

To identify, compare, and contrast multiple solutions for every major subsystem in your design.

## Resources

* Previous team assignments
* [Example Power Budget](https://www.dropbox.com/s/wyeqisp0uzyiics/Power%20Budget%20Example.xlsx?dl=0)
* [Ordering Resources](https://www.dropbox.com/sh/0pu5curaf0s2bs8/AAC_PwZxVOF_R2ny7IMxwVjea?dl=0) folder
* [Sources pages](https://embedded-systems-design.github.io/tags/sources/) on the Embedded Systems Design Resources blog
* Canvas discussion board

## Assignment

In this written report, your team must identify, compare, and contrast multiple solutions for every major component in your team's design. Major components include every block in your electrical block diagram, and any major mechanical parts.

Your assignment should consist of the following parts:

1. **Major component selections** - For each block in your block diagram and major mechanical components, you must research the following (except for the microcontroller and wifi module, which are required):
    * Off-the-shelf electrical and/or mechanical solutions (e.g., a motor with an optical shaft encoder built in to provide position feedback)
    * Custom electrical and/or mechanical solutions (e.g., build a [low-pass filter](http://www.electronics-tutorials.ws/filter/filter_2.html) from scratch to [de-bounce a switch](http://www.labbookpages.co.uk/electronics/debounce.html))

    Create *separate* tables (see [example](#3dy6vkm) later in this document) describing *at least* **3 potential solutions** for each major component in the design *(minimum 1 acceptable subsystem per team member)*, describing **multiple** pros and cons of each solution. You should also consider your project specifications when writing pros and cons.

    > **EGR 314:** All components (except for headers and connectors) must be surface mount. For resistors and capacitors, size 0805 or larger is recommended. Exceptions allowed with prior approval from your professor.

    Each commercial option *must include a photo and a link* to the product, along with unit cost. *Do not paste a plain hyperlink*. Instead, create a link with short descriptive text (like [this link](https://en.wikipedia.org/wiki/Hyperlink)).

    ***Notes:*** The embedded systems design website has a number of recommended [sources for components](https://embedded-systems-design.github.io/tags/sources/). **Do not select parts from Amazon** unless they come with datasheets or at a very minimum detailed specifications (required for proper design).

    Then, choose the optimal solution for your design and provide rationale for why your choice is optimal. Your rationale should be strong (e.g., avoid rationale such as "we chose this part because it's the first one on Google that met our specifications"). See [example in Table 1](#3dy6vkm) below.

    **Also, label in bold which component selections are associated with individual subsystems.**

2. **Power budget (optional for initial submission, required for checkpoint 2 presentation and report).** This spreadsheet will help ensure that your power source and regulator selections will sufficiently power your entire system. **Use this [example power budget](https://www.dropbox.com/s/wyeqisp0uzyiics/Power%20Budget%20Example.xlsx?dl=0) as a template. [Also see this walkthrough of a similar power budget](https://www.youtube.com/watch?v=5fUES8H1pTI) (but please use the current template above).**

    1. **In Section A, list ALL of the major components** from part 5 above that need power, along with the *absolute maximum* current that each component could use (see the data sheet). Do not list power sources or regulators at this point. Major components include the microcontroller, wifi board, active devices, integrated circuits, etc. Resistors and capacitors are not considered major components and should not be listed unless they are dissipating large amounts of power.

        > *Pro Tip:* Motor drivers are like switches to turn a motor on and off. If a motor driver can drive a 1A motor, the driver itself does not consume 1A of current from the power supply - the *motor itself* consumes 1A.

    1. **In Section B, assign each major component to ONE power rail.** Try to minimize the number of power rails in a system to 1 or 2 (e.g., 5V for logic and 12V for electromechanical actuators). Add a 25% safety margin onto the current needed to operate the system.
    1. **In Section C, for each power rail, select a specific voltage regulator** if you are not using a regulated power supply**.** If you are using a regulated power supply, then list it instead of the regulator. Modify your Major Component Selection document from Part 3 above to create a selection table for each voltage regulator, describing *at least* **2 potential solutions** for each in the design and describing **multiple** pros and cons of each solution. Choose a final solution for both the power source and the regulator, and describe the rationale for the choices (see example, Table 1). Then, enter the final selection for each rail next to "Regulator or Source Choice" in the power budget.
    1. **In Section D, select a specific external power source.** Typically a wall supply or battery, confirm that it can supply all of the regulators for all of the power rails simultaneously. If you need multiple power sources, list each separately and indicate which regulators will be connected to each supply. Confirm that the Total Remaining Current Available on each external power source is not negative.
    1. **In Section E, calculate battery life**. If your design uses a battery, calculate the worst-case life of the battery (assuming all subsystems are running simultaneously) in hours.

3. **Source Parts:** You will be building 2 - 3 iterations of your design: individual subsystem boards and a final team board. Therefore, you need to order **at least** 2 sets of parts to build all of the circuits in your design, plus extras in case parts get damaged during prototyping. See the Ordering Resources folder linked above for more information.

## Submission Instructions

This work will be used in multiple ways. It will be reviewed for feedback in class on the date given in Canvas, so please be prepared to discuss it with a member of the teaching team.

### Canvas Submission

Submit your completed report in Office or PDF format to this assignment on Canvas by the deadline in Canvas. *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to Canvas.

## Subsequent Uses of This Document

### Classtime

This document should be made available during classtime for review by the teaching team on the due date. We will provide feedback, which will be your responsibility to integrate and address in subsequent submissions.

### Report

This document will also be added to your team's report and maintained throughout the semester. It will be graded for additional feedback in upcoming project checkpoints.

### Checkpoints

This document will be summarized in your checkpoint 2 presentation.

## Grading

| **Item**                                                       | **Points** |
| :------------------------------------------------------------- | :--------- |
| Full (complete) draft submitted to Canvas and brought to class | 50         |
| **Total**                                                      | **50**     |

### Most Common Mistakes

* Block Diagram not updated

* Need at least one subsystem for each team member

* Selection Rationale missing pros/cons

## Examples

*Table 1: Example component selection*

**External Clock Module**

| **Solution**                                                                                                                                                                      | **Pros**                                                                                      | **Cons**                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| ![](image1.png)<br>Option 1.<br> XC1259TR-ND surface mount crystal<br>$1/each<br>[link to product](http://www.digikey.com/product-detail/en/ECS-40.3-S-5PX-TR/XC1259TR-ND/827366) | \* Inexpensive[^1]<br>\* Compatible with PSoC<br>\* Meets surface mount constraint of project | \* Requires external components and support circuitry for interface<br>\* Needs special PCB layout. |

| **Solution**                                                                                                                                                                                      | **Pros**                                                                                                                                    | **Cons**                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| ![](image3.png)<br>\* Option 2. <br>\* CTX936TR-ND surface mount oscillator <br>\* $1/each <br>\* [Link to product](http://www.digikey.com/product-detail/en/636L3I001M84320/CTX936TR-ND/2292940) | \* Outputs a square wave <br>\* Stable over operating temperature <br> \* Direct interface with PSoC (no external circuitry required) range | * More expensive <br>\* Slow shipping speed |

**Choice:** Option 2: CTX936TR-ND surface mount oscillator

**Rationale:** A clock oscillator is easier to work with because it requires no external circuitry in order to interface with the PSoC. This is particularly important because we are not sure of the electrical characteristics of the PCB, which could affect the oscillation of a crystal. While the shipping speed is slow, according to the website if we order this week it will arrive within 3 weeks.

[^1]: Avoid the word "cheap". "Cheap" means poor quality, while "inexpensive" means affordable.

## Most Common Mistakes

*Major Component Selection*

Do not...

1. Choose components or modules without data sheets. In most cases, trying to design with a component that doesn't have a data sheet is excruciatingly difficult and may significantly increase the time to complete a project.

2. Choose components that are too small to solder easily. Use QFN and smaller IC packages (common for accelerometers) at your own risk.

3. Only list 1 pro or con for a particular device. The goal is to thoroughly research all of the pros and cons of a device so that you can make an informed decision.

4. Use only 1 word to describe each pro/con.

5. Select a USB power pack as your power source.

*Power Budget*

1. Incorrectly listing the current consumption of a transistor or other IC as the amount of current it can pass. For example, if a transistor is rated at 5A this does NOT mean that it consumes 5A of current. The amount of current necessary to turn a transistor on and off is generally negligible (so small that it doesn't need to appear on the power budget). See [this link](https://www.dropbox.com/s/6s7bbjd0oe8agww/Quiescent%20Current.pdf?dl=0) for more information on "quiescent current".

2. Putting electromechanical switches on the power budget. A purely electromechanical (non-lighted) switch has a voltage and current rating (e.g., 12V @ 15A), but this represents the amount of voltage and current that the switch can handle, **not** how much it consumes. Electromechanical switches consume a negligible amount of power and can be ignored on the Power Budget.

3. If you are using an opamp with both a positive and negative rail, then both rails must be in the power budget.

4. (*EGR 304 only*) Listing an incorrect Absolute Maximum Current for the PSoC. This value should be based on the maximum amount of power that the PSoC package can dissipate.

## Frequently Asked Questions

*Major Component Selection*

**Q:** Should we create selection tables for specific components (e.g., a specific microcontroller part number or specific wifi module)?

**A:** No.

**Q:** Can we use USB power packs?

**A:** In general, no. Your system requires the use of a linear voltage regulator and USB power packs are already regulated to 5V. If you have multiple systems in your design (e.g., a wrist band and a separate device elsewhere) you could potentially use a USB power pack for one of them and still meet the course requirements. See your professor to discuss options.

**Q:** Does the power supply count as a subsystem? Who should be responsible for the power supply?

**A:** The power supply does not count as a subsystem, but should be included in the responsibilities of the person who is working on the microcontroller subsystem.

*Power Budget*

**Q:** If I have two separate parts to my system that are powered separately (e.g., a main PCB and a remote sensor, both with their own microcontrollers and/or wireless boards), should I put them on one power budget or two?

**A:** They should be on two separate power budgets since they are two separately powered systems in physically different locations.

*Top Design* **(EGR 304 only)**

**Q:** How do we add BLE to our Top Design?

**A:** The Bluetooth functionality is in its own EZ-BLE module on the PSoC board, and is connected to the PSoC via UART (see [Figure 3-5 in the Prototyping Kit Guide](https://www.cypress.com/file/396956/download)). Therefore, your Top Design should have a UART component connected to the ports shown in Figure 3-5 that allow it to connect with the EZ-BLE module.
