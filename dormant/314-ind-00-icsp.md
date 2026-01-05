---
subtitle: Individual Assignment
title: In-Circuit Serial Programming (ICSP) for PIC
---

## Objectives

To demonstrate individual proficiency in:

1.  Programming your microcontroller in-system on a breadboard or custom PCB

2.  Debugging a program using the SNAP programmer/debugger in MPLabX

**This is an individual homework assignment. While you may talk with others about how to complete the assignment, you must individually design, write, and implement all code and circuitry by yourself. All cases of academic dishonesty (including sharing your or using others' code, circuits, or breadboards) will be reported to the Dean's office.**

## Resources

-   Microchip Snap Programmer/Debugger [Main Page](https://www.microchip.com/developmenttools/ProductDetails/PartNO/PG164100)

    -   [Hardware User Guide](https://ww1.microchip.com/downloads/en/DeviceDoc/50002787C.pdf)

    -   [3-D printable enclosure design](https://www.thingiverse.com/thing:3074301)

-   [PIC18F47Q10 Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf)

-   Canvas Discussion Board

## Prior to Demonstration of Proficiency

*Complete all of the steps below prior to the demonstration of proficiency.*

In this assignment, you must use the PIC18F47Q10 microcontroller IC (the X-pin DIP package is included with your kit). This IC may be mounted on a breadboard or on your individual PCB designed in Cadence and manufactured in Peralta.

**You may not use the Curiosity Nano evaluation board for this assignment.**


### 1. In-System Programming

1.  Study the following critical information and concepts:

| **Critical Information and Concepts**                                                                                                                        | **Importance**                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| a.  How In-Circuit Serial Programming works with the MPLAB Snap In-Circuit Debugger                                                                         | Needed to understand both the big picture and technical details of how to program a bare PIC IC without removing it from your circuit board. Can be found in the [MPLAB Snap In-Circuit Debugger User's Guide](https://ww1.microchip.com/downloads/en/DeviceDoc/50002787C.pdf). |
| b.  What circuitry is necessary to connect your PIC to the Snap                                                                                              |                                                                                                                                                                                                                                                                                   |
| c.  Pinout for the X-pin SIL (single in-line) programming connector used to connect your circuit to the Snap. Note that pin 1 is marked by a black triangle. |                                                                                                                                                                                                                                                                                   |
| d.  How In-Circuit Serial Programming works on your PIC                                                                                                      | Needed to understand the necessary connections that are specific to your PIC. Can be found in the *Pin Diagrams* and *ICSP* sections of the [PIC18F47Q10 Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf)                  |
| e.  Which pins on the PIC must be connected in order for ICSP to work                                                                                       |                                                                                                                                                                                                                                                                                   |
| f.  How to properly write a function in C                                                                                                                    | Needed to modularize your code so that the same code in multiple places and improve readability. See [Tutorial on functions](https://www.tutorialspoint.com/cprogramming/c_functions.htm) for more information.                                                                 |

2.  Wire up your breadboard (or PCB) to connect the Snap and your PIC according to the information above. Make sure to connect all of the VDD and VSS pins in addition to connecting your external 3.3V power supply. Whenever there is conflicting hardware configuration information between the Snap manual and the PIC datasheet, follow the PIC datasheet as every PIC is a bit different and the Snap works with a number of different PICs.
    > *Tip:* If you attach an X-pin (where X = the number of pins in the Snap header) male to male header to your breadboard (or PCB) then it makes it easier to quickly connect and disconnect the Snap from your circuit.

3.  Launch MPLabX and create a new project for your PIC IC. *Note: Please remember that this is an individual assignment. The only way to learn to code independently is to work through coding problems and figure them out.*

    1. Configure your system clock to use the HFINTOSC at 32MHz with a clock divider of 4.

    1. Configure a digital output for blinking a LED on and off once every second. Make sure the Package is set to match your DIP IC.

        1. Modify your circuit to add an LED and appropriate current-limiting resistor in series.

    1. Add an ADC (leave all settings at their defaults) and connect it to an I/O pin.

        1. Modify your circuit to add a potentiometer. Connect the wiper pin to the analog input pin that you chose. Connect the other two pins to 3.3V and ground, respectively.

    1. Write code to make a "software comparator" that reads in a value from the ADC, sends it to a function to compare against a threshold, and lights up an LED depending on whether the analog value is above or below the threshold.

        1. Write a function that takes in a 16-bit ADC value, shifts the value right by # bits so that the **top 8 bits of the X-bit ADC result are in the lower half of the 16-bit variable**, and then stores it in a uint8_t variable. It should then compare the resultant 8-bit ADC value to an 8-bit threshold and return true (1) if it is below the threshold or false (0) otherwise. The function should have the following prototype:

bool below8bitThreshold( uint16_t value, uint8_t threshold )

**You may not change the function prototype to return void instead of bool.**

ii. In main(), read an ADC value and pass it to below8bitThreshold() with a threshold of 64.

iii. If the result is below the threshold, turn on the LED. If it is above the threshold, turn off the LED. This code should be in main(), not in below8bitThreshold().

iv. Wait for 1 second before repeating

 

4.  Compile the project and fix any errors

5.  Connect the Snap and power supply to your circuit. Then, connect the Snap to your computer.

6.  Download your code to the microcontroller. The code should run and turn on the LED only when the potentiometer is turned below the threshold.

> *If this step doesn't work, debug by first checking all connections against the data sheet, looking for error messages in the IDE, and searching for the error messages on Google. If you're still stuck, see the teaching team for help.*

### 2. Debugging

1.  Now, instead of simply downloading the project, connect to the programmer in debug mode.

2.  Practice the following:

    1. Setting and clearing breakpoints within the while() loop.

    1. Learning the difference between "step into", "step over", and "run".

    1. Finding the current value of the variable storing the ADC result.

    1. Modifying the current value of the variable storing the ADC result and seeing it affect the LED state later in the code.

## Individual Demonstration of Proficiency

Complete your demonstrations by the deadline in the course calendar on [Canvas](https://canvas.asu.edu). Late demonstrations will be graded per the policy in the syllabus.

1.  Connect your breadboard (or PCB) to the Snap and power supply, and then connect the Snap to your computer. Launch MPLabX and load your project. Download your project to the DIP PIC18F47Q10 on your breadboard (or PCB) via ICSP.

2.  Demonstrate the code working correctly such that when the potentiometer is turned below the threshold, the LED turns on and when it is turned below the threshold, the LED turns off.

3.  Demonstrate setting a breakpoint on the line that reads the ADC.

4.  Demonstrate stepping line by line into below8bitThreshold()

5.  Demonstrate monitoring the value of the variable holding the ADC result

6.  Turn the potentiometer all the way to 0 (below the threshold). Demonstrate changing the value of the variable that holds the ADC result to be larger than the threshold such that when you continue stepping through the code, the LED turns on.

## Canvas Submission

Submit your packaged MPLabX project (right-click on the project and select "Package" from the contextual menu) in ZIP format to this assignment on [Canvas](https://canvas.asu.edu) by the deadline in Canvas. *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to Canvas, even if a demonstration was completed.

## Grading

| **Demonstration**                                                                                                          | **Points** |
| -------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 1.  Connect your circuit, programmer, and power supply. Load project. Build and download your project to the PIC via ICSP | 50         |
| 2.  Code turning the LED on when the potentiometer is below the threshold, and off when it is above the threshold.         | 50         |
| 3.  Setting a breakpoint on the line that reads the ADC                                                                    | 25         |
| 4.  Stepping line by line into below8bitThreshold()                                                                        | 25         |
| 5.  Monitoring the value of the variable holding the ADC result                                                            | 25         |
| 6.  Modifying the ADC result variable in the debugger so that it changes the state of the LED                              | 25         |
| **Total**                                                                                                                  | 200        |
