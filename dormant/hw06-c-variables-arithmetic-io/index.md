---
title: C Variables, Arithmetic, and I/O
---

***Individual Assignment***

## Objectives

To individually demonstrate proficiency in:

1.  Creating and using variables and macros

2.  Using arithmetic operators

3.  Reading data from the keyboard via UART communication on the Cypress PSoC 4 Pioneer Kit

4.  Manipulating character data

5.  Incorporating unit testing while designing software

**This is an individual homework assignment** but you may work with others to determine how to complete the assignment.

## Importance

Variables and arithmetic operations are used throughout embedded systems to process data and make decisions. The PSoC 4 does not have a monitor or display, so the UART is used instead to provide input and output capabilities.

## Resources

-   [USB-UART homework template project](https://www.dropbox.com/s/zl4cw2mw9yciovc/USB_UART.zip?dl=0)

-   [Configuring the UART on PSoC](http://esdresources.blogspot.com/2015/10/configuring-uart-on-psoc.html) page

-   C Programming Reference: <https://www.programiz.com/c-programming>

-   [sprintf statements - from tutorialspoint](http://www.tutorialspoint.com/c_standard_library/c_function_sprintf.htm)

-   *Note: See the example project below for the PSoC UART equivalent of scanf()*

-   *Note: See the example project below for the PSoC UART equivalents of getchar() and putchar()*

-   PSoC 4 Pioneer Kit Theory of Operation - [Pioneer Kit Guide](http://www.cypress.com/?docID=47035) / [BLE Pioneer Kit Guide](http://www.cypress.com/file/229211/download)

-   Serial and UARTs - Scherz & Monk, Section 13.5.5; [Society of Robots](http://www.societyofrobots.com/microcontroller_uart.shtml)

-   Canvas Discussion Board

## Prior to Demonstration of Proficiency

*Complete all of the steps below prior to the demonstration of proficiency.*

1.  Review the resources listed above.

2.  Write a C program (in any programming environment) to solve the following problem:

-   Taking user input for the value of the radius of a circle, calculate the area and circumference of the circle. You should store the value of pi using #define. Your program should prompt the user for the radius with a prompt such as: "Please enter the radius in centimeters". After reading the user input, and performing the calculations, display the radius, and the two calculated values as follows: "Radius = R cm, Area = A sq. cm, Circumference = C cm."

3.  Configure the PSoC 4 Pioneer Kit hardware for UART communication and open PuTTY (see configuration instructions on the [Configuring the UART on PSoC](http://esdresources.blogspot.com/2015/10/configuring-uart-on-psoc.html) page)

4.  Use the [USB-UART template](https://www.dropbox.com/s/zl4cw2mw9yciovc/USB_UART.zip?dl=0) as a starting point, and make the changes outlined in the FAQ below to get floating point numbers to output correctly. Save the project as hw6_1.

5.  Copy your solution to the C program that you wrote into main.c of hw6_1. Make appropriate modifications so that the number entered is the radius, and that the output is printed via the UART to a putty terminal window. Save this project as hw6_2.

Every compiler has slightly different programming syntax, even if they use the same programming language. There are some differences between the C statements used in the course text and the C statements used by the PSoC compiler (see Table 1, below)

*Table 1: Selected differences between C implementations*

+---------------------------+------------------------------------------------------------------------------+
| **C**                     | **PSoC Creator**                                                             |
+===========================+==============================================================================+
| #include <stdio.h>     | #include <project.h>                                                      |
|                           |                                                                              |
|                           | #include <stdio.h>                                                        |
|                           |                                                                              |
|                           | #include <stdlib.h>                                                       |
+---------------------------+------------------------------------------------------------------------------+
| printf("Hello, world!");  | //Start any device before using it                                           |
|                           |                                                                              |
|                           | UART_Start();//start device only once UART_UartPutString("Hello, world!"); |
+---------------------------+------------------------------------------------------------------------------+
| int i;                    | int i = 2;                                                                   |
|                           |                                                                              |
| i = 2;                    | char buffer[100];                                                          |
|                           |                                                                              |
| printf("Hello %d!", i); | sprintf(buffer,"Hello %d",i);                                              |
|                           |                                                                              |
|                           | UART_UartPutString(buffer);                                                  |
+---------------------------+------------------------------------------------------------------------------+
| char ch;                  | UART_Start();//start device only once                                        |
|                           |                                                                              |
| scanf("%c", &ch);       | char ch;                                                                     |
|                           |                                                                              |
|                           | ch = UART_UartGetChar();                                                     |
+---------------------------+------------------------------------------------------------------------------+

## Demonstration of Proficiency

*You must complete the demonstration individually in office hours (or in class if time permits).*

1.  Open putty and connect to the Pioneer Kit COM port. Compile and download your project hw6_1 to the Pioneer Kit. Demonstrate that floats are printed through the UART.

2.  Open project hw6_2 and demonstrate your solution by asking the TA to enter a number in putty and checking for correct output.

## Submission

Submit all of the PSoC Creator workspace and project solution files in a single ZIP archive to this assignment on Canvas by the deadline in the course calendar on Canvas. *Do not submit links to Google documents*.


## Grading

| **Demonstration Item** | **Points** |
|:-----------------------|:-----------|
| 1                      | 50         |
| 2                      | 250        |
| **Total**              | **300**    |

You must submit to Canvas **and** demonstrate your solution in order to receive credit. Late submissions and demonstrations will be graded per the policy in the syllabus, based on the last activity (Canvas submission or demonstration).


## Frequently Asked Questions

**Q:** What is the best way to complete this assignment?

**A:** First, download the template. There are two folders in the zip file, and yes- one is for the BLE version and once is for the Pioneer Kit (they are labeled as such). Next, I would recommend looking at some of the references under the "Resources" section on the assignment description, particularly if you aren't familiar with C programming. For this assignment you will need to understand variables, syntax, and have a basic understanding of UART. You will also need to download Putty or a similar terminal simulator program (see the ESD blog). Next, unzip the template folder and open work space using PSoC creator and take a look at the main.c file. Try to familiarize yourself with the code and understand what each block of the code is doing (pay attention to the comments for this part). Next you will need to modify this code to perform the desired calculations of circumference and area based on the user input of radius. In short, the template is taking an input from the user and converting it to a double, but does NOT perform any calculations before outputting the value. That is the part you need to add.

**Q:** When I open the template ZIP file, there are multiple files in it. Which one do I use?

**A:** For the Pioneer Kit, open the file named USB-UART-EGR-2.cywrk

**Q:** Where should the output for hw6_1 appear on my computer?

**A:** Output should appear in the UART window on your computer.

**Q:** Help! My computer won't connect properly to the PSoC. (insert one of several error messages here - KitProg version not expected, upgrade the firmware)

**A:** Try updating the firmware on the PSoC 4 Pioneer Kit.

1.  In Windows, open the PSoC Programmer application

2.  Plug the Pioneer Kit into your computer via USB. It should appear on the left hand side of the window under Port Selection.

3.  Select the programmer, click the Utilities tab, and click Upgrade Firmware

4.  Wait for it to complete and try to use it again.

**Q:** How do I fix "The selected debug target is not compatible with the projects selected device" error (or other errors indicating that the template does not match your PSoC)?

**A:** On your projects right click the active (**BOLD**) project. Choose Device Selector... from the contextual menu.

![](image5.png)![](image6.png)

Then, look on the PSoC BLE module and find the device ID printed in small white characters below the chip. It should look like CY8C424XXXXX-XXXXX, where the XXX's are specific to your PSoC BLE module. Then, find this device ID in the Device Selector list and select it.

![](image2.png)

**Q:** How do I enable floating point support in the PSoC compiler?

**A:** Follow these steps:

1.  In the Workspace Explorer, right-click on your open project and choose Build Settings...

2.  Click on ARM GCC -> Linker -> Command Line -> Custom Flags

3.  Enter -u _printf_float (make sure you have 1 dash and 2 underscores)

-   ![Enabling floating-point support in the PSoC compiler](image1.png)

4.  Next, increase the heap size to 0x0800. From the project.cydwr page, go to the System tab and change the Heap Size (bytes) to 0x0800.

![](image3.png)

**Q:** How do I print an integer (or other non-string variable) to the PSoC UART?

**A:** According to the [PSoC UART data sheet](http://www.cypress.com/?rID=48892), the UART only outputs strings and characters. Therefore, we need to convert the integer to a string first, and then output it using the UART. Solution: the [sprintf()](http://publications.gbdirect.co.uk/c_book/chapter9/formatted_io.html) function in stdio.h

The following C code uses printf() (which does not output to the UART):

int a; *// declare variable*
a = 5; *// initialize variable*
float b; *// declare variable*
b = 6.7; *// initialize variable*
printf("Value = %i,%fn", a,b); *// print to screen (not UART)*

The following C code uses sprintf() to create a string and outputs it using the UART):

#include <stdio.h> *// include the library with sprintf()*
int a = 5; *// declare and initialize variable*
float b = 6.7; *// declare and initialize variable*
char obuffer[100]; *// declare output buffer string*
UART_Start(); *// only need this once in the program*

*// print to string using a similar syntax to the printf statement*
sprintf( obuffer, "Value = %i,%fn", a, b );

UART_UartPutString( obuffer ); *// output the string to the UART*
