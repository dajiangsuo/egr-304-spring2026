---
title: 304 Lab 4 -- Analog I/O and UART (PSoC)
---

# This assignment has 2 parts 

# Objectives For Part 1

Many sensors have an analog output that must be digitized using an Analog to Digital Converter (ADC) in order to use them in a microcontroller. The PSoC's ADC subsystem is the peripheral used to read analog values and convert it into a digital number for use in your program. It can be configured in a variety of ways. In this assignment, you will create an ADC component and program your microcontroller to transmit the result of reading an analog voltage measured at an input pin, using the ADC component in one of its simplest configurations.

> This in-class checkoff requires advance work in order to complete it. Please read through the Lab, read all datasheets, and prepare your circuits as much as possible.

## Resources For Part 1

* [Video Walkthrough For RT and TX Set up (using old board so you will need to use different pins)](https://urldefense.com/v3/__https://www.youtube.com/watch?v=sWcAb_V-L3A__;!!IKRxdwAv5BmarQ!Y9G6h1U3pjUXWgyaRoH6UfeASxcu3k2RkcN1GX9E2Jo2CZ_2LvmtEqfcPTCDOcSy4R8zEeaTKi-DJ4nE7I-RAaiA_yo$)
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
| Voltage regulator circuit from Lab.1 Part 2             | 1            | See Lab.1 Part 2     |
| Breadboard                                              | 1            |                      |
| Jumper wires                                            | many         |                      |
| CY8CKIT-042 (or CY8CKIT-042-BLE) PSoC 4 Prototyping Kit | 1            |                      |
| USB mini B cable                                        | 1            | included in PSoC kit |
| Resistors                                               | multiple     | various              |
| 10 k$\Omega$ Potentiometer                              | 1            | from kit             |

## Prior to Demonstration of Proficiency

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

1. Open PSoC Creator, create a new workspace for LAB 3 and a new project for the CY8CKIT-042. Create a blank project, and call it something descriptive like "ADC-to-UART".
1. Refer to page 23 of the CY8CKIT-042 PSoC 4 Pioneer Kit Guide and page 34 & 98 of the CY8CKIT-042-BLE-A Bluetooth Low Energy (BLE) Pioneer Kit Guide to get a sense of what you need to connect on your PSoC board to enable UART Rx and Tx. <The back of your board also includes a summary of the connections required.>
1. Go to the Top Design. Add a UART module (v2.50). This will automatically create a digital input pin (```Rx_1```) and digital output pin (```Tx_1```) already connected to it.
1. In the Top Design, add a Sequencing SAR ADC module. Open the module to configure it further.
    1. In the General tab, set ```Vref``` select to ```VDDA```. This is the maximum voltage that the ADC can sample. ```VDDA``` corresponds with the voltage on the ```VDDA``` pin. Also set "Single ended negative input" to ```Vref```, and set the "Single ended result format" to Unsigned.
    1. In the Channels tab, set Sequenced channels to 1. You will only be using one ADC channel at this time. Make sure the mode for the channel 0 is Single-ended (not differential). Leave the INJ channel at Diff. Hit OK.
1. Add 1 Analog Pin to the Top Design, name it if you choose, and  create a wire from the Analog Pin to the input of the Sequencing SAR ADC module. Assign it to the port you connected the potentiometer to above (look at Figure 1).
1. Go to the "Design Wide Resources → pins" page in your workspace and select the appropriate pin numbers based on your reading in step 4 above. Select a pin for reading an analog value into your ADC as well.
1. Build your project to automatically generate source files for the UART and ADC modules you just added.

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

## Individual Demonstration of Proficiency for part 1

In class, demonstrate the following **live** to a member of the Teaching Team by the end of class:

1. Walk through your breadboard with the Teaching Team member and explain how the potentiometer works. Then, connect the CY8CKIT-042 to your computer and launch PSoC Creator.

1. Compile, download, and demonstrate your solution to the "Reading an analog value and outputting it to PuTTY" section above, where you should see the ADC values change in PuTTY when you turn the potentiometer.

**A live demonstration by the end of class is required. No late demonstrations will be accepted.**

# Objectives For Part 2

The purpose of this assignment is to understand how Op-Amps can be used to amplify the current change in a device and output it as a voltage. We will be building two circuits: an inverting amplifier, and a noninverting amplifier, and learning about the differences. The signal you read will be derived from Lab 3's PWM Output

**An individual live demonstration of Parts 3, 4, & 5 (which includes Parts 1 and 2) of this assignment is required.**

## Walkthrough Video (Thanks Milan!)

<iframe width="560" height="315" src="https://www.youtube.com/watch?v=sMMXunHu-to&feature=youtu.be" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Resources For Part 2

* [Enable floating point support](https://embedded-systems-design.github.io/enable-floating-point-support/) in PSoC Creator
* Videos
    * Oscilloscope output: [https://youtu.be/JBDF59Gd5ks](https://youtu.be/JBDF59Gd5ks)
* Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542 *(**many** circuit design resources)*
    * Chapter 8: Operational Amplifiers
* **Oscilloscopes**
    * Scherz & Monk, Chapter 7.4
    * [Agilent MSO-X 4024A Oscilloscope User's Guide, pages 35-42 (Auto Scale) and pages 256-264 (Time Measurements)](http://esdresources.blogspot.com/2016/01/peralta-103-resources.html) *-or-*
    * [Agilent MSO 7054A Oscilloscope User's Guide, page 177 (AutoScale) and pages 192-205 (Time Measurements)](http://esdresources.blogspot.com/2016/01/peralta-103-resources.html)
* Canvas discussion board
* CY8CKIT-042 evaluation board ([main page](https://www.infineon.com/cms/en/product/evaluation-boards/cy8ckit-042/)) ([kit guide](https://www.infineon.com/dgdl/Infineon-CY8CKIT-042_PSoC_4_Pioneer_Kit_Guide-UserManual-v01_00-EN.pdf?fileId=8ac78c8c7d0d8da4017d0eeec6a57e1e))
* CY8CKIT-042-BLE evaluation board ([main page](https://www.infineon.com/cms/en/product/evaluation-boards/cy8ckit-042-ble-a/) / [kit guide](https://www.infineon.com/dgdl/Infineon-CY8CKIT-042-BLE-A_Bluetooth_Low_Energy_Pioneer_Kit_Guide-UserManual-v01_00-EN.pdf?fileId=8ac78c8c7d0d8da4017d0efc8fdb12b6))

## Parts & Tools Needed

| **Item**                                        | **Quantity** | **Detail**                                                                                                                                                                                                       |
| :---------------------------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LM324N                                          | 1            | ([Digikey](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627) / [datasheet](https://www.ti.com/lit/ds/symlink/lm224.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1664291051389) ) |
| DAC low-pass filter circuit from Lab 3 Part 2     | 1            | See Lab 3                                                                                                                                                                                                          |
| Voltage Regulator circuit from Lab 1 *(optional)* | 1            | See Lab 1                                                                                                                                                                                                          |
| Resistors                                       | multiple     | 2 x 10 kΩ and 2 x 1 kΩ                                                                                                                                                                                           |
| Potentiometers                                  | 2            | 10 kΩ                                                                                                                                                                                                            |
| Breadboard                                      | 1            |                                                                                                                                                                                                                  |
| Jumper wire                                     | many         |                                                                                                                                                                                                                  |
| Benchtop Oscilloscope                           | 1            |                                                                                                                                                                                                                  |
| Benchtop Power Supply                           | 1            |                                                                                                                                                                                                                  |

## Prior to Verification

### PSoC Preparation

> **Before you Start:** Confirm that your pioneer board power jumper is set to 5V to ensure full 0-5V operation.
>
> CY8CKIT-042: See Section 4.3.3 of the kit guide, along with Figures 4-1 and 4-4
>
> CY8CKIT-042-BLE: See Section 5.1.2 of the kit guide, along with Figures 1-2 and 5-1.


1. Copy the lab 3 "PWMAnalog" project into a new workspace named "Lab 4" (you will be using the low-pass filter setup for this part)
1. [Modify the project](https://embedded-systems-design.github.io/enable-floating-point-support/) to enable floating point number printing support in PSoC Creator.
1. Open ```main.c```. Replace the contents with the following lines, then compile and download:

        #include "project.h"
        #include "math.h"

        #define PI 3.141592

        float frequency = 10; //Hz
        float offset = 2.8; //Volts
        float amplitude = .25; //Voltage

        long time_milli = 0;
        float voltage = 0;
        int out = 0;
        int DAC_max = 0xff;
        float V_max = 5.0;

        int main(void)
        {
            CyGlobalIntEnable;
            PWM_1_Init();
            PWM_1_Start();

            for(;;)
            {
                time_milli+=1;
                voltage = (amplitude*sin(2.0*PI*frequency*time_milli/1000))+offset;
                out = (int)(voltage/V_max*DAC_max);
                PWM_1_WriteCompare(out);
                CyDelay(1);
            }
        }

### Circuit Preparation

 ![](image2.png){style="max-height:200px;"}

 ***Figure 1:** Inverting and noninverting circuits*

1. Construct the circuit in Figure 1 above.
1. Connect the output of the low-pass filter on your breadboard from HW3 to the positive input to the op-amp's "A" circuit. ("V_low_pass_in" connected to U1A's pin 3, see Figure 1 above).

### Oscilloscope Setup

1. Turn on the oscilloscope
    1. Turn on channel 1, 2, and 3; turn off all other channels.
    1. Set the Gain for all channels to 2 V/div
    1. Set the offset for all channels to zero.
1. Connect the channel 1 oscilloscope probe to the "V_low_pass_in" signal on your breadboard.
1. Connect the grounded alligator clip of the channel 1 oscilloscope probe to the ground rail of your breadboard.
1. Using the oscilloscope's measurement tool, add a measurement to measure the peak-to-peak voltage, average voltage, and frequency on channel 1.
1. Verify that the settings are correct using the oscilloscope. Adjust the time window until you see multiple waveforms on channel 1.

### Inverting Op-Amp Circuit

1. Connect the signal coming from Vout1 to the channel 2 oscilloscope probe, as noted.
1. Connect the grounded alligator clip of the channel 2 oscilloscope probe to the ground rail of your breadboard.
1. Using the measurement tool, add a measurement to measure the peak-to-peak voltage, average voltage, and frequency on channel 2
1. Adjust the (RV1) potentiometer and the "offset" variable in your code until you achieve the maximum gain without cutting off the output signal read on channel 2 of the oscilloscope.
1. Compare the output and measurements of channel 1 and 2. How do they differ?

### Non-inverting Op-Amp Circuit

1. Code changes: Update the existing line in your code to support voltage conversion:

 ```float offset = .75;```

1. Compile and download your changes to the PSoC
1. Connect the signal coming from Vout2 above (in Figure 1 above) to the channel 3 oscilloscope probe.
1. Connect the grounded alligator clip of the channel 3 oscilloscope probe to the ground rail of your breadboard.
1. Using the measurement tool, add a measurement to measure the peak-to-peak voltage, average voltage, and frequency on channel 3
1. Adjust the potentiometer and the "offset" variable in your code until you achieve the maximum gain without cutting off the output signal read on channel 2 of the oscilloscope.
1. Compare the output and measurements of channel 1 and 3. How do they differ?

## Individual Demonstration of Proficiency

You must complete the demonstration individually, either in office hours or in class if time permits. **Demonstrations can be done up to the last office hours on the due date noted in Canvas. This assignment can not be demonstrated on Zoom on Saturdays due to the need for an oscilloscope.**  **No late demonstrations will be accepted**

1. Properly set oscilloscope display settings on channels 1, 2, and 3.
1. Properly set oscilloscope measurement settings on channels 1, 2, and 3.
1. Properly controlled sinusoidal analog signal on channel 1, verified by oscilloscope.
1. Inverting op-amp: Properly amplified output signal on channel 2, verified by oscilloscope.
1. Non-Inverting op-amp: Properly amplified output signal on channel 3, verified by oscilloscope.

**Successful demonstration of Parts 3, 4, and 5 is sufficient for demonstrating all five parts.**

## Schematic

### Resources

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

1. Create a schematic for both of the circuits used above. Following the resources for KiCad$^1$ or Cadence above, duplicate the op-amp circuits that you built.
    1. You may use the LM324 op-amp included in the KiCad$^1$ symbol library.
    1. Add all other components, including the voltage used, resistors and resistance values selected, etc.

 > *KiCad$^1$:* Wherever possible, use the "US" version of parts, including "R_US" instead of "R", "C_US" instead of "C", and "C_Polarized_US" instead of "C_Polarized", etc.
 >
 > *Kicad$^1$:* Like the US/International part symbol differences, make sure you use "earth" ground for the ground symbol rather than the default "GND" symbol.

1. Export your schematic to PDF

 > *KiCad$^1$:* Follow the instructions for [Packaging KiCad$^1$ Files for Submission](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/)
 >
 > *Cadence:*Follow the instructions for [Packaging Cadence Files for Submission](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)

1. Package your files for submission to Canvas

## Canvas Submission

Submit the items below to Canvas by the deadline given (in Canvas). **Do not submit screenshots.** *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted via Canvas.

### PSoC Creator Files

Submit your packaged PSoC Creator workspace (right-click on the Workspace, select "Archive Workspace/Project..." from the contextual menu, and select a Minimal archive) in ZIP format to this assignment on [Canvas](http://canvas.asu.edu) by the deadline in Canvas. Do not submit links to Google documents.

### Schematic Files

Follow the instructions for packaging your schematic ([KiCad$^1$](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/))([Cadence](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)) to create a PDF and ZIP archive (including all library files) for your project. Submit **both** the PDF and ZIP archive as separate documents to this assignment on [Canvas](https://canvas.asu.edu) by the deadline in Canvas.

## Grading

| **Item**                                                                                   | **Points** |
| ------------------------------------------------------------------------------------------ | ---------- |
| Demonstration Part 1: Oscillocope Display Settings                                         | 15         |
| Demonstration Part 2: Oscilloscope Measurement Settings                                    | 15         |
| Demonstration Part 3: Sinusoidal Analog Signal                                             | 40         |
| Demonstration Part 4: Amplified Inverted Output Signal                                     | 40         |
| Demonstration Part 5: Amplified Non-Inverted Output Signal                                 | 40         |
| Separate ZIP file of single PSoC HW4 Workspace including all projects                     | 50         |
| Legible PDF of Schematic *(-5 points for each mistake)*                                    | 50         |
| Separate ZIP file including updated library and new symbols *(-5 points for each mistake)* | 50         |
| **Total**                                                                                  | **300**    |

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
