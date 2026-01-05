---
title: C Decision Making and Looping
---

***Individual Assignment***

## Objectives

To individually demonstrate proficiency in:

1.  Using if-elseif-else statements

2.  Using compound relational tests

3.  Using switch statements

4.  Using while loops

5.  Using do-while loops

6.  Using for loops

**This is an individual homework assignment** but you may work with others to determine how to complete the assignment.

## Importance

Decision making is used throughout embedded systems programs to check inputs (e.g., sensors or variables) and execute behaviors based on the inputs. For example, an if statement might be used to check if a button is pressed, after which an LED could be turned on. Loops are the most common way to execute repetitive behaviors (e.g., scanning for a button press, waiting for a serial message to come in via a UART) in an embedded system. In addition, infinite while loops are used in many main programs to keep the system running as long as the power is on.

## Resources

-   [USB-UART homework template project](https://www.dropbox.com/s/zl4cw2mw9yciovc/USB_UART.zip?dl=0)

-   [Configuring the UART on PSoC](http://esdresources.blogspot.com/2015/10/configuring-uart-on-psoc.html) page

-   C Programming Reference: <https://www.programiz.com/c-programming>

-   [sprintf statements - from tutorialspoint](http://www.tutorialspoint.com/c_standard_library/c_function_sprintf.htm)

-   PSoC 4 Pioneer Kit Theory of Operation - [Pioneer Kit Guide](http://www.cypress.com/?docID=47035) / [BLE Pioneer Kit Guide](http://www.cypress.com/file/229211/download)

-   Canvas Discussion Board

## Prior to Demonstration of Proficiency

*Complete all of the steps below prior to the demonstration of proficiency.* The following problems are similar in concept to functions you might encounter in an embedded system: doing mathematical calculations based on sensor data. You may use the [USB-UART template](https://www.dropbox.com/s/zl4cw2mw9yciovc/USB_UART.zip?dl=0) as a starting point for each problem.

1.  Review the resources listed above.

2.  Write a program that (1) keeps taking inputs from a user until the user enters the character 'Z'. Then, (2) the program should then prompt the user to enter any character ("Please enter a character: "). If the user enters a number at the prompt, the program should echo that number, meaning that it should print the number entered by the user to the terminal window. If the user enters a letter, the output should be based on the following table. For all characters not listed in the table, there should be no additional output besides "Please enter a character" to prompt for the next character. Note that the switch-case-break is a good way to implement this, as you have some specific actions associated with a set of inputs.

+---------------+----------------+
| -   **Input** | -   **Output** |
+===============+================+
| -   a         | -   air        |
+---------------+----------------+
| -   b         | -   water      |
+---------------+----------------+
| -   c         | -   ground     |
+---------------+----------------+
| -   A         | -   Airforce   |
+---------------+----------------+
| -   B         | -   Navy       |
+---------------+----------------+
| -   C         | -   Army       |
+---------------+----------------+

3.  Configure the PSoC 4 Pioneer Kit hardware for UART communication and open PuTTY (see configuration instructions on the [Configuring the UART on PSoC](http://esdresources.blogspot.com/2015/10/configuring-uart-on-psoc.html) page)

4.  Use the [USB-UART template](https://www.dropbox.com/s/zl4cw2mw9yciovc/USB_UART.zip?dl=0) or your HW06 solution as a starting point, copy your C program from #2 and make appropriate modifications so that the input and output is done through the UART. Save this project as hw7.

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

1.  Open your project hw7. Open putty and connect to the Pioneer Kit COM port. Compile and download your project to the Pioneer Kit. Demonstrate your solution by asking the TA to enter input in putty and checking for correct output. Show the TA the code to verify the use of switch-case-break.

## Submission

Submit all of the PSoC Creator workspace and project solution files in a single ZIP archive to this assignment on Canvas by the deadline in the course calendar on Canvas. *Do not submit links to Google documents.*


## Grading

| **Demonstration Item** | **Points** |
|:-----------------------|:-----------|
| 1                      | 300        |
| **Total**              | **300**    |

You must submit to Canvas **and** demonstrate your solution in order to receive credit. Late submissions and demonstrations will be graded per the policy in the syllabus, based on the last activity (Canvas submission or demonstration).


## Frequently Asked Questions

**Q:** How do I enable floating point support in the PSoC compiler?

**A:** Follow these steps:

1.  In the Workspace Explorer, right-click on your open project and choose Build Settings...

2.  Click on ARM GCC -> Linker -> Command Line -> Custom Flags

3.  Enter -u _printf_float (make sure you have 1 dash and 2 underscores)

-   ![Enabling floating-point support in the PSoC compiler](image2.png)

4.  Next, increase the heap size to 0x0800. From the project.cydwr page, go to the System tab and change the Heap Size (bytes) to 0x0800.

![](image1.png)
