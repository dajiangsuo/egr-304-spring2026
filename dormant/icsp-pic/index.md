---
title: "Lab: In-Circuit Serial Programming (ICSP) for PIC"
---

> This assignment is a ***paired in-class checkoff***. An **individual** live demonstration is required. You may work in pairs (**one** partner), but must individually demonstrate your working breadboard.

## Objectives

In this assignment, you will learn how to program a PIC using in-circuit serial programming with the MPLAB Snap debugger/programmer. This will be critical for your semester project as you will be working with a surface mount microcontroller that cannot be easily removed for offboard programming and does not have a USB port.

With your partner, you must demonstrate proficiency in:

1. Programming a microcontroller in-system on a breadboard using the Snap.
2. Adapting existing code for the Curiosity board to a breadboard.

<!-- *An individual live demonstration is required. You may work within pairs (**one** partner), but should individually demonstrate your ICSP.* -->

Thanks to Christian for the following walkthrough video!

<iframe width="560" height="315" src="https://www.youtube.com/embed/nKF-3WFuefQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Bill of Materials

| **Item**                                   | **Value(s)**                                                                                                                                       |
| ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Breadboard                                 |                                                                                                                                                    |
| Jumper wires                               |                                                                                                                                                    |
| Male to male header                        |                                                                                                                                                    |
| In-circuit debugger/programmer             | [MPLAB Snap](https://www.microchip.com/en-us/development-tool/PG164100)<br>([3-D printable enclosure](https://www.thingiverse.com/thing:3074301)) |
| Micro USB cable                            |                                                                                                                                                    |
| PIC 18F47Q10 microcontroller (DIP version) | [Part Website][part-website] ([datasheet][pic-datasheet])                                                                                          |

## Resources

- [PIC18F47Q10 Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf)
    - Figure 2-1. Recommended Minimum Connections
- [MPLAB Snap In-Circuit Debugger User's Guide](https://ww1.microchip.com/downloads/en/DeviceDoc/50002787C.pdf)
    - Figure 3-4 has connections detailed plus pullup resistor specified
    - Figure 3-6 identifies specific improper components
    - Figure 10-2 shows the SNAP header pinout
- [BK Precision Triple-Output 30V, 5A Digital Display DC Power Supply (Model 1671)](https://www.bkprecision.com/products/power-supplies/1671A-triple-output-30v-5a-digital-display-dc-power-supply.html) ([manual](https://bkpmedia.s3.amazonaws.com/downloads/manuals/en-us/1671A_manual.pdf))

## Prior to Demonstration of Proficiency

1. Read and search the [MPLAB Snap In-Circuit Debugger User's Guide](https://ww1.microchip.com/downloads/en/DeviceDoc/50002787C.pdf) to find answers to the following questions:
    1. How does In-Circuit Serial Programming work with the MPLAB Snap In-Circuit Debugger?
    1. What circuitry is necessary to connect a PIC to the Snap?
    1. What is the pinout for the 8-pin SIL (single in-line) programming connector used to connect your circuit to the Snap? Note that pin 1 is marked by a black triangle.
1. Read and search the *Pin Diagrams* and *ICSP* sections of the [PIC18F47Q10 Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf) to find answers to the following questions:
    1. How does In-Circuit Serial Programming work on the PIC18F47Q10?
    1. Which pins on the PIC18F47Q10-I/P must be connected in order for ICSP to work?
1. Set the BK Precision DC power supply to output 3.3V. Then, turn off the power supply before connecting it to your circuit.
1. Wire up your breadboard to connect the Snap and the PIC18F47Q10-I/P according to what you learned above. **Make sure to connect all of the VDD and VSS pins in addition to the external 3.3V power supply.** Whenever there is conflicting hardware configuration information between the Snap manual and the PIC18F47Q10 datasheet, follow the PIC datasheet as every PIC is a bit different and the Snap works with a number of different PICs.

    > *Tip:* If you attach an 8-pin male to male header to your breadboard (or PCB) then it makes it easier to quickly connect and disconnect the Snap from your circuit. |

1. Launch MPLabX and create a new project.  Set it up for use with the PIC18F47Q10 DIP version
1. Open the MCC Pin Manager and configure a pin as a digital output to a LED. Then, modify your breadboard to add a series resistor and LED to this pin.
1. Open main.c and comment out the printf() line. The Snap does not support UART communications back to the computer, so printf() will not work.
1. Compile the project and fix any errors.
1. **Turn on the external power supply and connect the Snap to your computer.**
1. Download your code to the microcontroller. You should see the LED blinking on and off. *If this step doesn't work, debug by first checking all connections against the data sheet, looking for error messages in the IDE, and searching for the error messages on Google. Also see the [MPLAB Snap Troubleshooting Guide](https://microchipdeveloper.com/snap:troubleshooting) for more information.*

## Part 2. Demonstration of Proficiency in Pairs

In class, demonstrate the following **live** to a member of the Teaching Team by the end of class:

1. Your fully-constructed breadboard with the LED and resistor, external power supply, and Snap programmer connected.
2. Successfully downloading code to the PIC with the Snap programmer.
3. Showing an LED connected to the PIC18F47Q10-I/P blinking.

**A live demonstration by the end of class is required. No late demonstrations will be accepted.**

## Canvas Submission

**No Canvas submission is required.**

## Grading

| **Demonstration**                   | **Points** |
| ----------------------------------- | ---------- |
| 1.  Breadboard                      | 30         |
| 2.  Successful Snap programming     | 60         |
| 3.  Blinking LED on PIC18F47Q10-I/P | 60         |
| **Total**                           | **150**    |

[part-website]: https://www.microchip.com/en-us/product/PIC18F47Q10
[pic-datasheet]: https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf