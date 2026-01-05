---
title: "Individual Subsystem Part 3: Hardware and Software Verification"
---

***Individual Assignment***

> *Testing can show the presence of errors, but not their absence*
>
> *-Edsger Dijkstra, computer scientist (1930-2002)*

## Objectives

In this assignment, you will test a PCB layout for the individual subsystem(s) assigned to you on the block diagram for your team project. You must individually demonstrate proficiency in:

1.  Powering up your board and circuit

2.  Showing your circuit functioning in the way it is intended

**This is an individual assignment** but you may work with others to determine how to complete the assignment. You must individually demonstrate proficiency.

## Resources

-   [PCB Fabrication Process](http://esdresources.blogspot.com/2017/09/asu-pcb-fabrication-process.html) on the Embedded Systems Design Resources Blog

-   [Peralta 103 Resources](http://esdresources.blogspot.com/2016/01/peralta-103-resources.html) on the Embedded Systems Design Resources Blog (includes links to manuals for the oscilloscopes and function generators in PRLTA 103)

-   [Soldering and Desoldering Tips and Tricks](http://esdresources.blogspot.com/2016/02/soldering-and-desoldering-tips-and.html) on the Embedded Systems Design Resources Blog

-   [The "Soldering Is Easy" Complete Comic Book](https://mightyohm.com/blog/2011/04/soldering-is-easy-comic-book/)

-   [Soldering Tutorial for Beginners Five Easy Steps](https://www.youtube.com/watch?v=8lq85feAiLM) video


## Prior to Demonstration of Proficiency

*Complete all of the steps below prior to the demonstration of proficiency.*

***Note:* You must complete this assignment using your custom PCB from the Individual Subsystem Part 2 assignment. You may not use a breadboard, evaluation board, or your team's full PCB.**

1.  Update your schematic and board design to match any changes which occurred prior to or after board manufacturing. *All documents must be up-to-date, easy to read, and must be consistent with each other.*

2.  Solder all headers and connectors to your subsystem PCB

3.  If your subsystem PCB includes a voltage regulator, solder the voltage regulator and associated components (e.g., bypass capacitors) to your PCB

4.  Connect power to the PCB and verify the following using a multimeter (handheld or benchtop)

    1. Correct voltage is coming into the PCB as expected

    1. If your PCB includes a voltage regulator, the correct voltage is coming out of the regulator

    1. Looking at your schematic, confirm that the supply voltage is going to all of the correct pins on the PCB

    1. If any mistakes are discovered, modify the PCB by cutting traces and soldering jumper wires until the design is correct. Update the schematic and/or PCB design in Cadence accordingly to account for these issues.

5.  Solder one set of subsystem components to the PCB. If you have multiple subsystems on a single PCB, pick one to start with

6.  Verify the functionality of a subsystem. See demonstration of proficiency below for the tests you must run to confirm functionality of each subsystem.

7.  If your board doesn't have your name etched in the copper, write your name in Sharpie somewhere in a blank area of your board. **This is required for verification.**

8.  Repeat steps 5 and 6 for each subsystem on your PCB

## Individual Demonstration of Proficiency

*You must complete the demonstration individually, either in virtual office hours or in virtual class if time permits.*

***Note:* You must complete this assignment using your custom PCB from the Individual Subsystem Part 2 assignment. You may not use a breadboard or evaluation board.**

1.  Open and share the block diagram and schematic for your subsystem PCB *All documents must be up-to-date, easy to read, and must be consistent with each other.*

2.  Show in the block diagram which subsystems have your name on them. These are the subsystems that you are responsible for.

3.  Power up your physical subsystem PCB and show with a multimeter that the correct regulated voltage is connected to **all** of the correct pins (e.g., all of the VCC pins on the microcontroller) on the PCB

4.  Demonstrate that your board has your name on it.

5.  Demonstrate the correct functionality of at least one subsystem on your PCB. (If you have multiple subsystems on your PCB, you only need to demonstrate one besides the power supply)

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Type of Subsystem**   **Test 1**                                                                                                                   **Test 2**                                                                                                       **Test 3**
  ----------------------- ---------------------------------------------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------
  Power Supply            Verify voltage at no load with a DMM                                                                                         Confirm microcontroller can be powered                                                                           Verify voltage with load (using power resistor or actuator)

  Micro-                 Demonstrate ICSP on your main microcontroller (when soldered to PCB) making an output change state                           Demonstrate web-based programming on your Photon to make the onboard LED blink                                   Demonstrate bi-directional EUSART communication between your main microcontroller and Photon (via the PCB)
  controllers[^1]                                                                                                                                                                                                                                                       

  Analog Sensor           Verify pre-amplified sensor signal with oscilloscope or DMM                                                                  Verify post-amplified signal with oscilloscope or DMM                                                            Verify microcontroller is reading amplified signal

  Bidirectional Motor     Demonstrate motor rotating in one direction                                                                                  Demonstrate motor rotating in opposite direction                                                                 Demonstrate motor alternating directions based on sensor reading

  Stepper Motor           Demonstrate motor running at slow speed                                                                                      Demonstrate motor running at fast speed                                                                          Demonstrate motor going both directions

  Switching Output        Verify driver signal from microcontroller with DMM                                                                           Verify low-current signal from transistor with DMM                                                               Verify high-current signal from transistor with DMM

  PWM Output              Verify duty cycle from microcontroller with DMM                                                                              Verify different duty cycle from microcontroller with DMM                                                        Demonstrate subsystem that uses PWM functioning as a result of the signal

  SD Card (read/write)    Write file from computer. Read file info from microcontroller to some output. Demonstrate on at least two different files.   Write file from microcontroller. Read file info on computer. Demonstrate writing at least two different files.   Read and write file from microcontroller. Demonstrate on at least two different files.

  Speaker                 Verify analog signal output from DAC in microcontroller                                                                      Verify analog signal output from amplifier                                                                       Verify speaker outputs sound

  Voice Recorder IC       Verify power going to IC                                                                                                     Verify recording works                                                                                           Verify playback works

  ...                    ...                                                                                                                         ...                                                                                                             ...

  Other                   Develop a custom plan with Instructors                                                                                                                                                                                                        
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Canvas Submission

Please submit your ***final*** updated subsystem design based on prior checkpoints, including schematic and board layout. Your final submission should include 2 PDF files (one of the schematic and another of the PCB layout), 2 ZIP files (the schematic project/PCB Editor project, and Gerber files). *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to [Canvas](https://canvas.asu.edu) was successful. Late [Canvas](https://canvas.asu.edu) submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to [Canvas](https://canvas.asu.edu).

**Your schematic and PCB PDFs must be legible in order to be graded. Rasterized (pixelated) images will receive a 0 if they are illegible. Do not submit screenshots.**

### 1. Legible Schematic and Board Layout PDF

Follow the [Packaging a Cadence Schematic Project for Submission to Canvas](http://esdresources.blogspot.com/2017/09/packaging-cadence-files-for-submission.html) instructions to create PDFs of both your schematic and your PCB layout. You do not need to submit ZIP files of your Cadence project. **Do not submit screenshots.**

### 2. MPLabX Project ZIP

You must submit the code used in your subsystem PCB demonstration. In MPLabX, right-click on your project name in the Projects window and select "Package". Submit the resultant ZIP file.

### 3. Subsystem Testing

Demonstrations may be made through the date noted in Canvas. Your grade will be documented in a spreadsheet and later uploaded to the Canvas gradebook. Late demonstrations will be graded per the policy in the syllabus.


## Grading

+------------------------------------------------------------------------------------------------------------------+------------+
| **Item**                                                                                                         | **Points** |
+==================================================================================================================+============+
| 1. Completed legible schematic **and** completed legible PCB design in PDF format only *(required for grading)* | 100        |
|                                                                                                                  |            |
| *-10 points per mistake up to -100 points, or 0 points if either PDF is illegible.*                              |            |
+------------------------------------------------------------------------------------------------------------------+------------+
| 2. MPLabX Project ZIP                                                                                         | 50         |
+------------------------------------------------------------------------------------------------------------------+------------+
| Test 1 successfully demonstrated                                                                                 | 175        |
+------------------------------------------------------------------------------------------------------------------+------------+
| Test 2 successfully demonstrated                                                                                 | 175        |
+------------------------------------------------------------------------------------------------------------------+------------+
| Test 3 successfully demonstrated                                                                                 | 300        |
+------------------------------------------------------------------------------------------------------------------+------------+
| **Total**                                                                                                        | **800**    |
+------------------------------------------------------------------------------------------------------------------+------------+

-   ***This checkpoint depends on successful completion of all prior checkpoints of the Individual Subsystem assignment to receive credit for this part.***

-   ***The schematic and board design must match what is manufactured and tested to receive credit for any part of the assignment***


## Frequently Asked Questions

**Q:** I discovered an error in my PCB. May I re-spin (re-manufacture) it?

**A:** Generally, no. Most mistakes can be fixed by cutting traces and soldering wires onto your existing board. Please see the professors or TAs for help in reworking your PCB. Also, it is recommended that you still fix your design in Cadence so that it is ready for the Full PCB assignment later in the semester.

**Q:** Do we have to fabricate separate PCBs for each team member? Or could we submit a single PCB since they will be located in the exact same place and be connected together (with other team members schematics/blocks) anyways?

**A:** Each team member needs to submit their own subsystem on a separate PCB. This is to ensure that every student has this skill (a learning outcome of the course). Breaking the board into subsystems also assists in the debugging process. You will combine your debugged subsystems into one final board for your team project.

**Q:** Is it possible to submit a video demonstration of our subsystem to canvas?

**A:** We require live video demonstrations in order to confirm your proficiency with the entire process.

**Q:** As I was testing and putting the board together I found that somewhere, the voltage input was in contact with ground. I have made several big manual fixes to the board including drilling out a hole to make room for a connector. But just from what I can actually see, there are no solder bridges there. How do I fix this?

**A:** Unfortunately PCBs are tough to debug without seeing live (or virtually). I highly recommend taking advantage of office hours. Having said that, places where you've manually modified the board after manufacturing are a common place where continuity problems occur. Using the continuity tester isn't helpful for locating shorts, so I'd recommend using the ohmmeter and look for a spot with lower resistance to get an idea of where the issue might be.

**Q:** Will taking a knife and manually isolating the pads work to fix continuity problems?

**A:** Yes, you can use an exacto knife to isolate the pads, but I would only do that once you've eliminated other possibilities. A TA should be able to help more in office hours.

**Q:** I have soldered all my components and am now having a continuity problem. Now what?

**A:** The best way to eliminate continuity problems is to test your before you have soldered on components, and then to test continuity after adding each component so you can trace the problem to your most recent action. Otherwise you will have to methodically desolder components from the board until the short goes away.

PS Sometimes incorrect footprints will cause shorts through the PSoC. To protect your PSoC and PCB, attach your PSoC without power and check for shorts between power and ground. Only then should you power up the board.

[^1]: Including 1) a Photon and 2) the main microcontroller selected by your team
