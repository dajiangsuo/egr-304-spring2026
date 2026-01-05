---
title: 304 ICC4 -- Analog I/O and UART (PSoC)
---

> This assignment is a ***paired in-class checkoff***. An **individual** live demonstration is required. You may work in pairs (**one** partner), but must individually demonstrate your working breadboard.

## Objectives

Many sensors have an analog output that must be digitized using an Analog to Digital Converter (ADC) in order to use them in a microcontroller. The PSoC's ADC subsystem is the peripheral used to read analog values and convert it into a digital number for use in your program. It can be configured in a variety of ways. In this assignment, you will create an ADC component and program your microcontroller to transmit the result of reading an analog voltage measured at an input pin, using the ADC component in one of its simplest configurations.

> This in-class checkoff requires advance work in order to complete it within one class period. Please read through the ICC, read all datasheets, and prepare your circuits as much as possible.

## Resources

* [Video Walkthrough](https://urldefense.com/v3/__https://www.youtube.com/watch?v=sWcAb_V-L3A__;!!IKRxdwAv5BmarQ!Y9G6h1U3pjUXWgyaRoH6UfeASxcu3k2RkcN1GX9E2Jo2CZ_2LvmtEqfcPTCDOcSy4R8zEeaTKi-DJ4nE7I-RAaiA_yo$)
* Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542
    * Analog input - Scherz & Monk, Section 13.5.2
- [PSoC 4100S Plus Datasheet](https://www.cypress.com/file/396611/download)
* [CY8CKIT-042 evaluation board main page](https://www.infineon.com/cms/en/product/evaluation-boards/cy8ckit-042/), which includes the Prototyping Kit Guide, Schematic, and Example Code Installer
* [CY8CKIT-042-BLE evaluation board main page](https://www.infineon.com/cms/en/product/evaluation-boards/cy8ckit-042-ble-a/), which includes the Prototyping Kit Guide, Schematic, and Example Code Installer
* [PSoC 4 Lab 4 - ADC - Lab Manual.pdf](https://www.dropbox.com/s/uch6vnjg1pdluot/PSoC%204%20Lab%204%20-%20ADC%20-%20Lab%20Manual.pdf?dl=0), which follows similar steps to those in this ICC.
* PuTTY [website](https://www.chiark.greenend.org.uk/~sgtatham/putty/)
* Canvas discussion board
* C Information
    * [GNU C Reference Manual](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html)
* Wikipedia articles on [RS-232](https://en.wikipedia.org/wiki/RS-232), and [UART](https://en.wikipedia.org/wiki/Universal_asynchronous_receiver-transmitter)
* [Video Tutorial on USB Serial](https://www.youtube.com/watch?v=vezklzw6PxM)
* The [Embedded Systems Design](https://embedded-systems-design.github.io) website

## Parts Needed

| **Item**                                                | **Quantity** | **Detail**           |
| :------------------------------------------------------ | :----------- | :------------------- |
| Voltage regulator circuit from HW1                      | 1            | See HW1              |
| Breadboard                                              | 1            |                      |
| Jumper wires                                            | many         |                      |
| CY8CKIT-042 (or CY8CKIT-042-BLE) PSoC 4 Prototyping Kit | 1            |                      |
| USB mini B cable                                        | 1            | included in PSoC kit |
| Resistors                                               | multiple     | various              |
| 10 k$\Omega$ Potentiometer                              | 1            | from kit             |

## Prior to Demonstration of Proficiency

*Complete all of the steps below prior to the demonstration of proficiency.*

1. Study the following critical information and concepts:

    | **Critical Information and Concepts**                                              | **Importance**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
    | :--------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | a. What is the syntax for a ```do-while``` loop in C, and when is it useful?         | You will be using a ```do-while``` loop to ensure that at least one character is read before jumping out of the loop. See [do...while loop in C from tutorialspoint.com](https://www.tutorialspoint.com/cprogramming/c_do_while_loop.htm).                                                                                                                                                                                                                                                              |
    | b. What is an ASCII character and how do I reference one in C?                     | ASCII is a way that computers store characters, and you will be reading and converting ASCII characters in this section. Learn more about ASCII conversions at [asciitable.com](https://www.asciitable.com). For example in C, you can represent the letter ```A``` as ```65``` (decimal integer), ```0x41``` (hexadecimal number), or ```'A'``` (character with single quotations around it).                                                                                                                             |
    | c. What is the syntax for a ```switch-case``` statement in C, and when is it useful? | You will be using a ```switch-case``` statement to more easily process user input to a multi-option menu. See [switch statement from tutorialspoint.com](https://www.tutorialspoint.com/cprogramming/switch_statement_in_c.htm).                                                                                                                                                                                                                                                                         |
    | d. What is an analog to digital converter (ADC)?                                   | You will be using an analog to digital converter in this section and in your semester project. Can be found in the [Analog to Digital Conversion Tutorial on Sparkfun.com](https://learn.sparkfun.com/tutorials/analog-to-digital-conversion/all) and in section 12.8.5 of [Scherz & Monk](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition).        |
    | e. What is a successive approximation register (SAR) ADC?                          | You will be using a SAR-type ADC built into the PSoC. [This article from Maxim Integrated explains how they work](https://www.maximintegrated.com/en/design/technical-documents/tutorials/1/1080.html). It is recommended that you skim the document.                                                                                                                                                                                                                                             |
    | f. What is a hexadecimal number and how do I interpret it?                         | Microcontrollers store data in binary format. Hexadecimal is an easier way to view binary data, and is needed to complete this section. Can be found in the [Hexadecimal Tutorial on Sparkfun.com](https://learn.sparkfun.com/tutorials/hexadecimal/all) and in Section 12.1.2 of [Scherz & Monk](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition). |

1. Watch the video [PROTOCOLS: UART - I2C - SPI - Serial Communications](https://www.youtube.com/watch?v=IyGwvGzrqp8) to learn about UART and RS-232 communications that you will be using in this assignment. What you learn in this video will help you understand later instructions (the PuTTY application in Windows and the UART component in PSoC Creator).
1. If you haven't already, download and install the [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/) terminal program (Windows only). This program will be used to display text sent over the USB port on the PSoC.

    ![](image5.png){style="max-height:200px;"}

    ***Figure 1:** Potentiometer in to PSoC Pin*

1. Construct the circuit above on a breadboard using a 10 kΩ potentiometer from your kit. Use a multimeter set to measure resistance to determine the pinout (specifically, which pin the wiper is connected to) of the potentiometer. Power connection VCC can be connected to a VDD pin on the CY8CKIT-042. The ground connection can be connected to a GND pin on the CY8CKIT-042. Determine a suitable analog input pin by referencing the Appendix of the [Prototyping Kit Guide appropriate for the microcontroller you are using](#resources).
    
    *Next, you will need to set up a code example to send data from the PSoC to a terminal program on your computer.*

### Creating a new PSoC project and top design

1. Open PSoC Creator, create a new workspace for ICC4 and a new project for the CY8CKIT-042. Create a blank project, and call it something descriptive like "ADC-to-UART".
1. Refer to page 23 of the CY8CKIT-042 PSoC 4 Pioneer Kit Guide and page 34 & 98 of the CY8CKIT-042-BLE-A Bluetooth Low Energy (BLE) Pioneer Kit Guide to get a sense of what you need to connect on your PSoC board to enable UART Rx and Tx. The back of your board also includes a summary of the connections required.
1. Go to the Top Design. Add a UART module. This will automatically create a digital input pin (```Rx_1```) and digital output pin (```Tx_1```) already connected to it.
1. In the Top Design, add a Sequencing SAR ADC module. Open the module to configure it further.
    1. In the General tab, set ```Vref``` select to ```VDDA```. This is the maximum voltage that the ADC can sample. ```VDDA``` corresponds with the voltage on the ```VDDA``` pin. Also set "Single ended negative input" to ```Vref```, and set the "Single ended result format" to Unsigned.
    1. In the Channels tab, set Sequenced channels to 1. You will only be using one ADC channel at this time. Make sure the mode for the remaining channel is Single-ended (not differential). Leave the INJ channel at Diff.
1. Add 1 Analog Pin to the Top Design, name it if you choose, and assign it to the port you connected the potentiometer to above. Create a wire from the Analog Pin to the input of the Sequencing SAR ADC module.
1. Go to the "Design Wide Resources → pins" page in your workspace and select the appropriate pin numbers based on your reading in step 4 above. Select a pin for reading an analog value into your ADC as well.
1. Compile your project to automatically generate source files for the UART and ADC modules you just added.

### Writing code to output your initials to PuTTY

1. In the "generated" source portion of your project, open up and read through ```UART_1.h``` and ```UART_1.c```. Identify the functions for initializing and starting the UART_1 subsystem, as well as the functions for sending both a single character and a string of information to the TX buffer. Identify the variables required to call the functions as well as the type of values returned by the functions, if applicable.
1. Add content to ```main.c```:
    1. Add ```#include "stdio.h"``` to the top of the file, which will add the ```stdio``` library for using functions like ```printf()``` and ```sprintf()``
    1. Add the ```UART_1``` start and initialization function identified above to the ```main.c``` before the main ```for(;;)``` loop is called.
    1. Inside the main ```for``` loop, add a function for sending one character over the Tx buffer. Call the function twice, sending the initials of your name. Call it two more times, sending the ```'\r'``` (carriage return) and ```'\n'``` (linefeed) characters.
    1. Compile and download your code to the PSoC
1. Open the device manager (Start → type "device..." and it will find device manager for you). Navigate to Ports (COM & LPT). Identify the port of the connected KitProg device.

    > *Hint:* [How to find the right serial port name](https://www.zaber.com/software/docs/motion-library/ascii/howtos/find_right_port/)

1. Open PuTTY and create a new serial session. Type in the com port of the connected KitProg device found previously (eg "COM2"); select the speed of the port to be the same as that found in the UART module of your Top Design, above. This value can be changed, but they both have to be changed to the same value. (9600 is a standard, slow transmission rate, for example). You should see your initials printed in the terminal.

    > *Hint:* [PuTTY Tutorial for Serial COM (step-by-step guide)](https://www.youtube.com/watch?v=dO-BMOzNKcI)

### Reading an analog value and outputting it to PuTTY

Open ```main.c``` and modify the existing code to do the following:

1. Create a variable of type ```uint16``` to hold the ADC result.
1. Initialize and start the software UART (can be found in the software UART component datasheet).
1. Initialize and start the ADC (can be found in the ADC component datasheet).
1. Call the ADC ```StartConvert()``` function to start the conversion process.
1. Set the ADC to wait for a conversion to complete before returning a value from the function call. Use the following function: ```ADC_IsEndConversion(ADC_WAIT_FOR_RESULT)``` (where ADC is the name of your ADC component in the top design)
1. Within the ```for(;;)```
    1. Output a data label to the software UART (e.g., "ADC Value:")
    1. Read ADC channel 0 and store the value in the variable you created for the ADC result

        > *Hint 1:* The function to read a 16-bit sample from the ADC is in the API section of the ADC datasheet.

        <p></p>

        > *Hint 2:* [How to call a function](https://www.tutorialspoint.com/cprogramming/c_functions.htm) from tutorialspoint.com

    1. Output the ADC value in two-byte hexadecimal format to the software UART. You can the ```sprintf()``` function along with a string you declare to format a string in a hexadecimal format.
    1. Output a carriage return and line feed to the software UART.

        > *Hint:* See the API section of the software UART datasheet.

    > *Note:* You may comment out any other code from the example that is not needed to achieve the above.

1. Compile, download, and run your code on the PSoC. When you connect to the PSoC with PuTTY, you should see the ADC values change in PuTTY when you turn the potentiometer. **Note the maximum (largest) value that can be read by the ADC. This will be needed in the future.**

## Individual Demonstration of Proficiency

In class, demonstrate the following **live** to a member of the Teaching Team by the end of class:

1. Walk through your breadboard with the Teaching Team member and explain how the potentiometer works. Then, connect the CY8CKIT-042 to your computer and launch PSoC Creator.

1. Compile, download, and demonstrate your solution to the "Reading an analog value and outputting it to PuTTY" section above, where you should see the ADC values change in PuTTY when you turn the potentiometer.

**A live demonstration by the end of class is required. No late demonstrations will be accepted.**

## Canvas Submission

**No Canvas submission is required.**

## Rubric

| **Item**        | **Points** |
| :-------------- | :--------- |
| Demonstration 1 | 10         |
| Demonstration 2 | 40         |
| **Total**       | **50**     |

## Devices

| ![](image8.jpg)    | ![](image4.jpg) | ![](image10.jpg) |
| ------------------ | --------------- | ---------------- |
| Digital Multimeter | Oscilloscope    | Power Supply     |
| (Not Used)         | (Used)          | (Used)           |

| ![](image6.jpg)    | ![](image1.jpg)    | ![](image7.jpg) |
| ------------------ | ------------------ | --------------- |
| Function Generator | Waveform Generator | Soldering Iron  |
| (Not Used)         | (Not Used)         | (Not Used)      |

### Probes

| ![](image9.jpg) | ![](image3.jpg)    | ![](image2.jpg) |
| --------------- | ------------------ | --------------- |
| Oscilloscope    | Digital Multimeter | Soldering Iron  |
| (Used)          | (Not Used)         | (Not Used)      |
