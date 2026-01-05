---
title: Team PCB Design Draft
---

***Team Assignment***

## Objectives

To document the combined hardware design for your team's project.

## Resources

-   Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542 (many circuit design resources)

-   [Cadence posts](https://embedded-systems-design.github.io/cadence/) on the Embedded Systems Design Resources blog

-   [Ordering Resources](https://www.dropbox.com/sh/0pu5curaf0s2bs8/AAC_PwZxVOF_R2ny7IMxwVjea?dl=0) folder

-   [Example Schematic](https://www.dropbox.com/s/ixg2uu3bmf9254d/GameControllerV2.pdf?dl=0)

-   [Bill of Materials example](https://www.dropbox.com/s/urnlk2rn0xu6hih/Bill%20of%20Materials%20Example.xlsx?dl=0)

-   Canvas Discussion Board

## Instructions

Document the hardware design of your product in *all* of the following ways. *Complete all of the steps below prior to submitting your assignment to Canvas.*

1.  **Full (complete) draft schematic, power budget, performance specifications, and rationale & plan.** Bring to class on the date noted on the calendar in [Canvas](https://canvas.asu.edu) for an in-class feedback activity. You do not need to bring a draft Bill of Materials to the draft review. **Your draft must be stored in your team's Google Drive at the beginning of class in order to be considered for credit.**

2.  **Schematic design.** Cadence drawing that includes all electronic components and connectors on your printed circuit board. The design must:

    1. Be labeled with team number and name, team members, project name, and version number

    1. Cover all items on the [Schematic Checklist page on the ESD blog](https://embedded-systems-design.github.io/schematic-checklist/)

    1. Be a combined version of the individual schematics created in the subsystem assignment. Instead of having 4 different PCBs, merge the schematics into a single diagram. Each subsystem should be labeled with the designer's name. Your design must include the following:

        1. ***(304 only)*** A custom schematic symbol for the Cypress PSoC CY8CKIT-149 plug-in module. You can find a pinout for the module on the manufacturer's website. See instructions in the [Creating a Custom Schematic Symbol in Cadence](https://embedded-systems-design.github.io/creating-a-custom-schematic-symbol-in-cadence/) blog entry.

        1. ***(314 only)*** A custom schematic symbol for your team's microcontroller *IC **(not the Curiosity Nano Board)***. You can find the pinout for the microcontroller on the manufacturer's website. See instructions in the [Creating a Custom Schematic Symbol in Cadence](https://embedded-systems-design.github.io/creating-a-custom-schematic-symbol-in-cadence/) blog entry.

        1. ***(314 only)*** A custom schematic symbol for the ESP32 plug-in wifi module. You can find the pinout for the wifi module on the manufacturer's website.

        1. Custom schematic symbols for any other components that are not in preexisting libraries. Components can be custom-built (most common), or sometimes found in the built-in libraries or on [UltraLibrarian](https://www.ultralibrarian.com) (see the [Cadence Schematic Tutorials](https://embedded-systems-design.github.io/cadence-schematic-tutorials/) page).

        1. Connectors or headers for power and all other signals coming into and leaving the board (e.g., HEADER parts from the Connector library). This includes connectors for switches, sensors, and actuators that will not be mounted directly to your PCB.

        1. 0.1 µF non-polarized capacitors to bypass the power supply for digital ICs (see [Bypass Capacitor Basics page](https://embedded-systems-design.github.io/bypass-capacitor-basics/)).

        1. All necessary discrete components (e.g., resistors, capacitors, inductors) (see datasheets for your major components).

        1. At least one fuse and fuse receptacle for limiting the damage due to shorts.

        1. A short text label describing each section of the circuit, in addition to a label block with your team number and name, your name, project name, and version number.

        1.  4 - 8 LEDs (and current-limiting resistors) on unused I/O pins for debugging indicators.

        1. Additional requirements listed on the [Schematic Checklist](https://embedded-systems-design.github.io/schematic-checklist/) page.

    1. **Verify your schematic against the [Most Common Mistakes](#kix.pmwakq9hyxc0) below**

3.  **Bill of materials** (BOM) - A "shopping list" spreadsheet of **all** the parts (including headers) required to build your project. It is typically created by engineers and used by a non-technical purchasing department to buy parts.

    1. After completing the schematic, export a BOM from Cadence (Tools menu > Bill of Materials...) and load it into Excel or Sheets.

    1. Modify the Bill of Materials spreadsheet (see example in Resources above) with the following columns:

        1. **Part Name/Description.** (e.g., "8-stage shift-and-store bus register"). Be specific.

        1. **Unit Quantity.** Quantity of each component needed in a single unit of the project

        1. **Unit Prototype Cost.** Low-volume cost per part. From manufacturer or distributor (see [Suppliers](https://embedded-systems-design.github.io/search/?s=suppliers))

        1. **Total Prototype Cost** = Unit Quantity x Unit Prototype Cost

        1. **Unit Production Cost.** High-volume (based on expected sales of the product) cost per part. From manufacturer or distributor (see [Suppliers](https://embedded-systems-design.github.io/search/?s=suppliers)).

        1. **Total Production Cost** = Unit Quantity x Unit Production Cost

        1. **Manufacturer.** What company makes the part? (see [Suppliers](https://embedded-systems-design.github.io/search/?s=suppliers))

        1. **Manufacturer Part #.** Found on the data sheet for the part

        1. **Supplier**. From where will you buy the part? This is often different than the manufacturer

        1.  **Supplier Part #.** Sometimes different than manufacturer part #.

        1. **# Ordered.** Quantity of each part ordered from a supplier.

        1. **Date Ordered.** Date that each part was ordered from the supplier.

        1. **# Received.** Quantity of each part in possession by the team.

        1. **Surplus** = # Received - Unit Quantity. Make sure to order extras of each part (particularly the inexpensive parts).

        1. **Schematic Reference Designators.** (e.g., U1, R1, R3, R5) Output from ECAD software (you may not have this information yet)

        1. *Note 1: Mechanical parts may not use all of the above columns* component order and arrival dates

        1. *Note 2:* Components acquired for free from Peralta must still be sourced from a distributor with all of the information above (including prototype and production costs).

    1. Label the spreadsheet with team number and name, your name, project name, and version number

    1. Add any parts required for your project which have not made it into your schematic. This includes extra part counts, parts in your system which are not on your board (power supply, programmers, offboard wifi modules, other networked components, etc.)

4.  **Updated power budget.** Must be updated based on feedback from other students, the teaching team, and a deeper individual understanding of circuitry. For more information on the power budget, see the Major Component Selection Rationale assignment.

5.  Make a copy of your team's performance specifications table and rationale and plan paragraphs from the Problem Definition assignment. Update the performance specifications table to complete the "Actual Value" column, and the rationale and plan paragraphs to match your team's current design. See examples below.

*Table 1: Example performance specifications*

| **Metric #** | **Metric**        | **Unit**           | **Marginal Value** | **Ideal Value** | **Actual Value** |
|:--------------|:------------------|:-------------------|:-------------------|:----------------|:-----------------|
| 1             | Waterproofing     | depth for one hour | $>$ 1 meter        | 5 meters        | 4 meters         |
| 2             | Upper Noise Limit | dB                 | $<$ 120            | $<$ 100         | 80 dB            |
| 3             | Lower Noise Limit | db                 | > 40              | > 60           | 50 dB            |
| 4             | Startup Time      | ms                 | $<$ 500            | $<$ 200         | TBD              |
| 5             | Clock Deviation   | ms/day             | $<$ 100            | $<$ 25          | 50 ms / day      |

**Example Rationale & Plan**

**Specification 1:** Device may be submerged in water during normal operation, therefore it is necessary to identify the depth at which it will fail. 1m represents a water depth not easily found within the home; 5m ensures that the product will continue to work even if submerged in a typical swimming pool.

Testing will consist of dunking the final enclosure at a depth of 5m for one hour, with a water-absorbing substance. We will test to see if any water was absorbed when it is retrieved, dried and opened.

**Specification 2:** Without noise protection, the product is unsafe to users' ears. We will use a cell-phone based volume meter, calibrated against common indoor sounds as well as a standardized source (if possible), to measure the relative device volume. Additionally, the piezo buzzer volume will be limited in software by changing the duty cycle of the PWM signal driving it.

**Specification 3:** Without enough volume, the device cannot be heard during operation. This limits the ability of the user to interpret what the device is doing. The same tests mentioned above will be used to measure the volume. Additionally, the piezo buzzer volume will be increased in software by changing the duty cycle of the PWM signal driving it.

**Specification 4:** Market research indicates that consumers are willing to wait up to 500 ms for this device to start up; we can impress customers with a faster startup time of 200 ms. We will measure the startup time by monitoring an I/O pin on the microcontroller with an oscilloscope.

**Specification 5:** Interviews reveal users would prefer to change the clock once a year or less. a 25 ms clock error every day would result in less than 10 minutes of error over a full year, which we have determined meets our users' needs. We will test the device by letting it run over a 48 hour period (weekend), and measuring the deviation against a standardized source. We intend to use the ESP32 to connect to an atomic clock and periodically send the current time back to the PIC via a UART connection. The PIC will then update the real-time clock to match the atomic clock time.

6.  **Source Parts:** Order *at least* 1-2 sets of any additional parts needed for each team member (minding your course budget) to build all of the circuits. See the Ordering Resources folder linked above for more information. **Each team will be building 1 - 2 copies of their team's hardware design.**

## No Canvas Submission

Bring your **complete** draft to class on the date noted on the calendar in [Canvas](https://canvas.asu.edu) to be checked off and receive feedback. **Your draft must be stored in your team's Google Drive in order to receive credit.** No late check offs will be accepted. **No Canvas submission is necessary for the draft. Your final design will be submitted and graded as part of the Design Review.**


## Grading

| **Item**                                                                              | **Points** |
|:--------------------------------------------------------------------------------------|:-----------|
| Complete draft schematic brought to class                                             | 50         |
| Complete draft performance specifications table and rationale + plan brought to class | 50         |
| **Total**                                                                             | **100**    |

## Example Schematic

![](image2.png)

## Most Common Mistakes

**Make sure...**

-   All BJTs have base resistors and are wired correctly

-   All components have a part number (e.g., LM7805) or component value (e.g., 0.1 uF, 100k) in the "Value" field

-   All components have a reference designator (e.g., R1, C2, U5)

-   All fuses have current ratings

-   All ICs have bypass capacitors on each power pin

-   All voltage regulators have a ground pin connected to ground, along with both input and output bypass capacitors as specified in the voltage regulator datasheet

-   Net names are not used instead of proper power and ground symbols

-   No components are shorted out (e.g., a wire between both pins of a capacitor)

-   No fuses are in series with a motor

-   The circuit has a power input connector (even if the power supply is not your responsibility)

-   Inductive actuators (e.g., motors, solenoids) have a back EMF flyback diode for each coil

## Frequently Asked Questions

**Q:** I need help with Cadence! When are office hours?

**A:** See Canvas for up-to-date information on office hours.

**Q:** It is difficult to create a schematic without crossing wires. Is it OK if wires cross as long as they do not connect?

**A:** Wires can cross in a schematic, but there are best practices for making schematics look professional. See the [Keeping a Schematic Tidy](https://embedded-systems-design.github.io/keeping-a-schematic-tidy/) blog entry and/or stop by office hours.

**Q:** When pulling up libraries when first starting to create a custom schematic symbol, custom library is not coming up as an option. How do I get my custom library to come up?

**A:** You can create a custom library folder by choosing "File > New > Library". This will create a new library with a default name under Design Resources in the project.

![](image5.png)

Once you have the custom library created, right-click on the library and choose "New Part".

**Q:** I get this error, how do I fix it?

> *Duplicate Pin Name "DRAIN" found on Package IRF520 , Q1 Pin Number 4: SCHEMATIC1, PAGE1 (4.90, 2.30). Please renumber one of these.*

**A:** Select the part, then right click on it and select "Edit Part". If you double click on each of the top two pins, you will see that they both have the name set to "DRAIN". Change the names so that they do not match. For example, "DRAIN1" and "DRAIN2":![](image1.png)![](image3.png)

Close the part editor tab and when it asks if you want to update the part, select "Update All" then "Yes". Save the file and try netlisting again.

**Q:** How do you increase the size of the toolbar in Cadence?

**A:** Experiment with the compatibility settings in Windows. Right click on Orcad Capture Lite, select "Open file location". The program directory will pop up. Right click on the icon for Orcad Capture light, and select "properties"(1). Go to the compatibility tab and select "DPI settings"(2). Try playing with settings (3) and (4).

![](image6.png)
