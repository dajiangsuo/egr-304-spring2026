---
title: 304 HW1 -- Power Supply Schematic Design
---

> **This is an individual homework assignment** but you may work with others to determine how to complete the assignment.  All work demonstrated in checkoff must be completed by you on your own board.

## Introduction

In this assignment, you will use ECAD design tools to draw your first circuits for EGR304.

You must individually demonstrate proficiency in:

1. Using ECAD (electronic computer-aided drafting) to design circuits.

You may use KiCad$^1$ or Cadence to complete this assignment. KiCad$^1$ is an open-source, cross-platform tool that is lighter-weight and a smaller download.

Cadence is a professional-level industry-standard tool that takes time to download (~15 GB), install (>1 hour), and learn. *Please plan accordingly*.



## Resources

* [Video Walkthrough of this Assignment](https://www.youtube.com/watch?v=Ecr9_7v3Qes) (Thanks to Tyler H!)

    > *Note on the video:* the voltage regulator part number is "LM317BT". Professor Aukes's initials are "DMA". Use ***your own initials*** when creating the symbol, not Professor Aukes's.

* The Embedded Systems Design website
    * [KiCad$^1$](https://embedded-systems-design.github.io/kicad/kicad-schematic-design/) schematic posts:
        * [Symbol Creation](https://embedded-systems-design.github.io/kicad-symbol-creation/)
        * [Schematic Capture](https://embedded-systems-design.github.io/kicad-schematic-capture/)
        * [Common Pin Types and their Meanings](https://embedded-systems-design.github.io/kicad-common-pin-types/)
    * [Cadence](https://embedded-systems-design.github.io/cadence/) posts
        * [Creating a custom library in Cadence](https://embedded-systems-design.github.io/creating-a-custom-library-in-cadence/)
        * [Creating a custom schematic symbol in Cadence](https://embedded-systems-design.github.io/creating-a-custom-schematic-symbol-in-cadence/)
        * [Creating a new project in Cadence](https://embedded-systems-design.github.io/creating-a-new-project-in-cadence/)
* KiCad$^1$ [Getting Started](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html) Pages on the KiCad$^1$ website:
    * Introduction to KiCad$^1$: [Download and Install](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#download-and-install-kicad)
    * [Basic Concepts and Workflow](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#basic_concepts_and_workflow)
    * [Tutorial 1: Project](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_1_project)
    * [Tutorial 2: Schematic](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html#tutorial_part_2_schematic)

* Canvas discussion board

## Bill of Materials

| **Item**                            | **Quantity** | **Details**              |
| :---------------------------------- | :----------- | :----------------------- |
| Voltage Regulator Circuit from ICC1 | 1            | (completed in class)     |
| 1N4007 Diodes                       | 2            | (found in your kit)      |
| 1 µF Tantalum Capacitor             | 1            | (found in your kit)      |

## Assignment

1. Follow the [instructions](https://embedded-systems-design.github.io/kicad-installation-and-setup/) on the Embedded Systems Design website to [install the fall software stack](https://embedded-systems-design.github.io/egr304-software-stack/). Please note that ***installing Cadence is optional*** for EGR304.
1. Learn about ECAD

    > *KiCad$^1$:* Read through the first four sections of the "[Getting started in KiCad$^1$](https://docs.kicad.org/6.0/en/getting_started_in_kicad/getting_started_in_kicad.html)" tutorials, including installation, concepts and workflow, project, and schematic (linked above).
    >
    > *Cadence:* What is Cadence Schematic Capture? See the [What is Cadence?](https://embedded-systems-design.github.io/what-is-cadence/) and [Cadence Schematic Tutorials](https://embedded-systems-design.github.io/cadence-schematic-tutorials/) pages for an overview of the software product and its features.

1. Update the voltage regulator circuit to include all the protection elements highlighted in the datasheet's Figure 7 (see Figure 1 below). Continue to use the resistance values calculated / identified in ICC1, and swap out the potentiometer for a fixed resistor (or equivalent resistor network) that establishes a fixed 5V output.
1. Create a schematic for your adjustable regulator circuit. Following the resources for KiCad$^1$ or Cadence above, duplicate the regulator circuit that you adapted from ICC1, using all the values of the ***actual resistors used***, *rather than the values given* in the datasheet.
    1. **Create your own custom symbol library** (review the resources above)

    > *KiCad$^1$*: make sure the library is created as a project library. You will need to . ***Put your initials** in the library's file name*.

    1. **Create your own custom symbol** for the adjustable regulator. The symbol should include your initials in the symbol name *so that your **initials are visible** when the symbol is added to schematics.*

    > *KiCad$^1$:* Wherever possible, use the "US" version of parts, including "R_US" instead of "R", "C_US" instead of "C", and "C_Polarized_US" instead of "C_Polarized", etc.
    >
    > *Kicad$^1$:* Like the US/International part symbol differences, make sure you use "earth" ground for the ground symbol rather than the default "GND" symbol.

    1. Review this [short schematic checklist](https://embedded-systems-design.github.io/schematic-checklist/) to ensure your design isn't missing any common mistakes

        ![](image2.png){style="max-height:200px;"}

        ***Figure 1:** Example Regulator Circuit adapted from the LM317BT datasheet, with custom symbol. Use your OWN initials.*

1. Export your schematic to pdf and package your files for submission to Canvas

    > *KiCad$^1$:* Follow the instructions for [Packaging KiCad$^1$ Files for Submission](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/)
    >
    > *Cadence:*Follow the instructions for [Packaging Cadence Files for Submission](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)

## Part 2. Individual Demonstration of Proficiency

You must complete a live demonstration individually, either in office hours or in class if time permits. Demonstrations can be done up to the last office hours on the due date noted in Canvas.  **No late demonstrations will be accepted**

Demonstrate the following **live** to a member of the teaching team:

1. Your breadboard fully constructed with the updated regulator circuit.
1. DMM measurement of the output voltage of the regulator circuit under small-load conditions (500$\Omega$ ≥ Output load ≥ 100$\Omega$)

## Canvas Submission

Follow the instructions for packaging your schematic ([KiCad$^1$](https://embedded-systems-design.github.io/packaging-kicad-files-for-submission/))([Cadence](https://embedded-systems-design.github.io/packaging-cadence-files-for-submission/)) to create a PDF and ZIP archive (including all library files) for your project. Submit **both** the PDF and ZIP archive as separate documents to this assignment on [Canvas](https://canvas.asu.edu) by the deadline in Canvas. **Do not submit screenshots.** *Do not submit links to Google documents.* It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to Canvas.

## Grading

| **Item**                                                    | **Points** |
| ----------------------------------------------------------- | ---------- |
| Demonstration 1: Completed, updated breadboard              | 25         |
| Demonstration 2: 5V small-load output DMM measurement       | 50         |
| Custom global library file created and included in ZIP file | 25         |
| Custom voltage regulator symbol included in custom library  | 25         |
| Schematic accurately depicted (*-5 points for each error*)  | 150        |
| Legible PDF of schematic included in submission             | 25         |
| **Total**                                                   | **300**    |

You must submit to Canvas **and** demonstrate your solution in order to receive credit. Late submissions and demonstrations will be graded per the policy in the syllabus.

$^1$ KiCad is only permitted in EGR304
