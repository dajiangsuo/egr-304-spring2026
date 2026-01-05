---
title: Project Checkpoint 3 - Final Design Review
---

***Team Assignment***

> **No late assignments will be accepted.**

## Objectives

Project documentation is a common industry process by which a design process is documented so that future engineers may learn about the steps that your team have followed. In this third checkpoint assignment, your team will finalize the documentation for your design via a living report document, updated versions of the files created this semester, and individual reflections contributed by each team member on the design and what each of you have learned. Your checkpoint will be disseminated in the following ways:

* Documents will be shared in your team's virtual collaboration space.
* A static version of the report will also be uploaded to Canvas.
* Your work up to this point will be presented in the form of an in-class presentation.

## Resources

* [Checkpoint 1 Assignment](/304/304-team-06-checkpoint-1/)
* [Checkpoint 2 Assignment](/304/304-team-11-checkpoint-2/)
* Adobe Acrobat (part of Adobe Creative Cloud) available for free from [https://uto.asu.edu/adobe-creative-cloud](https://uto.asu.edu/adobe-creative-cloud) (request early, as it takes a few days for requests to be approved).
* Canvas discussion board
* Powerpoint
    * [How to record your presentation](https://www.youtube.com/watch?v=bP9VJ03s8Gw)

## Assignment

Prepare the following deliverables prior to your presentation day:

### Presentation

1. Create a presentation (roughly 5 minutes but no more):
   1. Team #, name, and team members (15 sec)
   2. 30-second summary of your problem definition (needfinding & specifications)
   3. **Figure of current product concept(1 min)**
      1. Provide a figure/rendering of your product in its current form. Highlight features that satisfy user needs, with labels and arrows. You may update or re-work one of the images from design ideation, or start from scratch if you prefer.
   4. Block Diagram of your Product (1 min)
      1. Discuss each teammate's updated subsystem and how they together achieve project requirements.
   5. Hardware Implementation (1 min)
      1. View of Schematic and PCB Design
   6. Software Implementation (1 min)
      1. Present and discuss the final software layout
   7. A 30-second video of your system working in its final form.
2. Practice your presentation to ensure you are not cut off early.
3. You will then record your presentation. See the resources above for tutorials.

> **Do not use google slides to record your presentation.** The audio files are stored in google drive **even after downloading or converting to .pptx**, which can cause accessibility issues when presenting and dead links when archiving.

### Team Folder Structure

#### Setup

Please refer to the [Team Repository assignment](/304/304-team-00-team-repository/) for complete instructions on setting up your team folder.

#### Content

1. Add the following folders to your ```assignments``` folder:
    * **13-hardware-implementation**
    * **14-software-implementation**
    * **15-system-verification**

2. Add/organize all contents to each folder, including...
    * ```01-team-organization``
        * Team Organization & Charter assignment document
    * ```02-interviews``
        * Stakeholder discovery interview protocol
        * Stakeholder discovery interview raw notes
        * Stakeholder tour and interview insights assignment document
    * ```03-user-needs``
        * User needs assignment document
        * images/whiteboards/slides from generation process
    * ```04-product-requirements-document``
        * Product requirements assignment document
    * ```05-design-ideation``
        * Design ideation assignment document
        * images/whiteboards/slides from generation process
        * Vector-based source files for each design concept
    * ```07-block-diagram``
        * Block diagram assignment document
        * Source file for block diagram
    * ```08-component-selection``
        * Component selection assignment document
        * Power budget spreadsheet (XLSX)
    * ```09-software-proposal``
        * Software proposal assignment document
        * UML activity and/or statechart diagrams
    * ```10-hardware-proposal``
        * Hardware proposal assignment document
        * PDFs of schematics submitted for this assignment
        * ZIP of the KiCad or Cadence project submitted for this assignment
        * Bill of materials spreadsheet (XLSX)
        * Data sheets for all selected electronic components in a subfolder
    * ```13-hardware-implementation``
        1. **Hardware implementation assignment submission**
        1. **PDFs submitted for this assignment**
        1. **ZIP of the ECAD project submitted for this assignment**
        1. **ZIP of the gerber files submitted for this assignment**
        1. **DRC printout**
        1. **Manufacturing confirmation**
    * ```14-software-implementation``
        1. **Aoftware implementation assignment submission**
        1. **Updated UML activity and/or statechart diagrams**
        1. **Updated block diagram submitted for this assignment**
        1. **PSoC Creator workspace ZIP file submitted for this assignment**
    * ```15-system-verification``
        1. **Add your final, up-to-date system verification spreadsheet, as well as a link to the copy made by the teaching team and reshared with you.**
3. Add checkpoint 1 and 2 presentation files to the ```presentations``` folder, using the naming convention from the [Team Repository assignment](/304/304-team-00-team-repository/)
4. Add any images, videos, CAD, or code you have generated to their respective folders, according to the naming conventions outlined in the [Team Repository assignment](/304/304-team-00-team-repository/)
    * ```ecad``` -  ZIP snapshots of your team's pcb design as it evolved.
    * ```mcad``` - add any solidworks or Fusion360 CAD files to this folder
    * ```psoc-code``` - add the many versions of your team's project code.
    * ```videos``` - add at least one video of your system working
    * ```images``` - Include a gallery of at least five different views of your final device (top, front,side, isometric, ...)
5. Move any unsorted files to their proper folders.

### Report

Update your team's project report document in the report folder

#### Formatting

We will be grading for format consistency through the use of styles. Please follow the [report formatting instructions](https://embedded-systems-design.github.io/report-formatting-instructions/) found on the embedded systems design website.

#### Content

The purpose of this report is to consolidate all your team's individual assignments into one complete and comprehensive report. ***If you cut homework material from the report in checkpoint 1, you should add it back.*** If the content negatively impacts the flow of the document, feel free to put it in an appendix, but make sure you **refer and link** to the appendix from the body of the report.

| **Assignment**                           | **Updates Required**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Title Page                               | Project name, team number, team members, external designer name, submission date, university, class, professor, link to your team folder                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Front Matter                             | Add a table of contents (TOC) & table of figures.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|                                          | *Show only the first two heading levels in your TOC to minimize the space required for the TOC.*                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Introduction                             | Add an introduction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                                          | *Consider moving and updating the introduction from your product requirements document to the front of the report*                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Team Organization                        | Use formatting to highlight the mission statement and charter from the surrounding paragraphs so we can identify it easily.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                                          | **Update** based on feedback received both from the initial submission and checkpoint 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Stakeholder Interviews                   | Make any updates requested during Project Checkpoint 1 grading.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|                                          | *Make sure you refer to the appendix in the body of the report, indicating there is more content elsewhere*                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| User Needs and Benchmarking              | **Update** to reflect any new knowledge you have gained in user needs, other competitive products, or changes in your project direction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|                                          | **Update** based on feedback received both from the initial submission and checkpoint 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Product Requirements                     | **Update** the product requirements section of your report to match your team's current design. Eliminate aspects that no longer apply, and create new design aspects as needed to match the current direction you are working in. We will be looking for consistency with your block diagram, components selected, schematic, power budget, and software proposal.                                                                                                                                                                                                                                                                                                                   |
|                                          | **Update** based on feedback received both from the initial submission and checkpoint 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|                                          | **Provide answers to** the open questions previously listed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Design Ideation                          | **Update** based on feedback received both from the initial submission and checkpoint 1. No specific action items are required, but continue to add detail based on feedback received                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Final** Selected Design                | **Update for your final design**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|                                          | Include a short summary of the decision-making process your team used to pick one of the team's design concepts. Did you further combine good ideas from your design ideation? Did you select the best? How was the decision made?                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                          | If the selected design deviates significantly from the design ideation section, please explain                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Final** Block Diagram                  | -   Update your block diagram as needed to reflect changes to your current design, making sure you address any feedback received, whether in person or in writing.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                          | -   Explain your decision making process for how you developed this and explain how your block diagram meets your product requirements.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Final** Component Selection            | -   Provide a summary table of final major components selected for the project in the main body of the report. Do not include passive components, pushbuttons, etc. Move the originalUpdate component selection table to the appendix, adding new components added or switched to since the last submission.. Take into account suggestions made by the teaching team and based on the evolution of your project.                                                                                                                                                                                                                                                                     |
|                                          | -   Explain your decision making process for creating this section and discuss how your selected components meet your product requirements                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|                                          | -   **Power Budget: Update your team's power budget to reflect your current design**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                                          | -   Update your explanation for how you used the power budget to estimate power needs and any conclusions you have come to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Hardware Proposal**                    | > Eliminate, but see below                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Final Hardware Implementation**        | -   Include an *image* of the team's **final** schematics as a figure in the report. you may use landscape mode on this page to better fit the format of the schematic.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|                                          | -   Discuss how the functionality of this schematic satisfies user needs and product requirements though an in depth discussion of function.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|                                          | -   Discuss your team's design and decision making process related to this section                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                          | -   **Include the team's bill of materials in the appendix**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|                                          | -   **Include front and back screenshots of the team's final PCB design.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|                                          | -   **Include front and back photos of the team's final PCB design.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                          | -   **If you were to create a "Version 2.0" of your hardware design, discuss what could be improved in the hardware design and why it should be improved. Use the schematic above to support the discussion. (½ page minimum)**                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Software Proposal**                    | > Eliminate, but see below                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Final Software Implementation**        | -   Include an **updated** *image* of the team's **final** UML activity and/or statechart diagrams as a figure in the report. you may use landscape mode on this page to better fit the format of the schematic if desired.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                                          | -   Ensure your **diagram** matches your **code.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                          | -   Discuss how the functionality of this software diagram satisfies user needs and product requirements though an in depth discussion of function                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                          | -   Discuss your team's design and decision making process related to this section                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                          | -   **Numbered list of the top 5 biggest changes to your software design since the software proposal. Include several sentences for each change describing the issue and how you resolved it. Use the UML diagrams above to support the discussion.**                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                                          | -   **If you were to create a "Version 2.0" of your software design, discuss *what* could be improved in the software design and *why* it should be improved. Use the UML diagrams above to support the discussion. Consider using a graphical representation of the flow that your updated software would take. What functions would you create? How would you divide up your code? How would you improve its debuggability? What peripherals or system features would you like to use or set up to make your system more reliable, stable, functional, or robust? How would you simplify, improve, or update your protocol design to support this in software? (½ page *minimum*)** |
|                                          | -   ***(EGR 304 only)*** Final **screenshots of your Top Design and Pins** pages , along with all **C/C++ code** that your team has written or modified. (in appendix)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|                                          | -   ***(EGR 314 only)*** Final **MQTT topic table** and all **C/C++ code** that your team has written or modified, and screenshots of your MCC configuration. (in appendix)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **System Verification**                  | **Include the team's final completed system verification matrix**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Lessons Learned**                      | **What are the top 10 most important things that your team learned from working on this project? You may use feedback received from the design review and content you discussed in status reports to address this section. (use full sentences, ½ page minimum)**                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Recommendations for future students.** | **Create a numbered list with the top five recommendations for future students of what they should learn or do to prepare themselves for taking this class. Each item must be at least one complete sentence long.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## Submission

No late assignments will be accepted.

### Canvas

#### Google Drive Folder

Unless you have changed folders or failed to share your folder according to the instructions in checkpoint 1, you do not need to re-share with the teaching team.

#### Report

Combine the above report sections into a single PDF (required for grading) named ```team-123-report.pdf``` where ```123``` is your team number and submit to Canvas by the deadline in the course calendar. *Do not just submit a link to your folder.* No credit will be awarded for assignments not submitted to Canvas.

#### Presentation File

Submit a .pptx or .pdf version of your presentation to canvas. Please refrain from embedding videos for space reasons. Any linked videos must link to a YouTube video rather than google drive (to prevent permission errors). Test the presentation on a separate computer prior to submission to ensure it works.

#### Final Presentation Video

Please upload your final presentation video to YouTube and share the link in Canvas. Set the link to "unlisted".

## Grading

| **Item**                                                | **Points** |
| ------------------------------------------------------- | ---------- |
| Google Drive Folder Structure*(each mistake -5 points)* | 50         |
| Presentation Recording\*                                | 200        |
| Presentation Files                                      | 50         |
| Report                                                  |            |
| Front Matter                                            | 25         |
| Introduction                                            | 25         |
| Team Organization                                       | 25         |
| Stakeholder Interviews                                  | 50         |
| User Needs and Benchmarking                             | 50         |
| Product Requirements                                    | 50         |
| Design Ideation                                         | 50         |
| Final Selected Design                                   | 50         |
| Final Block Diagram                                     | 100        |
| Final Component Selection                               | 100        |
| Final Hardware Implementation                           | 100        |
| Final Software Implementation                           | 100        |
| System Verification                                     | 25         |
| Lessons Learned                                         | 75         |
| Recommendations for Future Students                     | 75         |
| **Total**                                               | **1200**   |

Sections will be evaluated for general formatting, layout, organization, and legibility, and to ensure feedback-based updates were applied to all sections. Sections will be graded based on the following scale:

* 100% Exceeds Expectations
* 85% Above Expectations
* 70% Meets Expectations
* 55% Below Expectations
* 40% Does Not Meet Expectations
* 0 Missing

## Frequently Asked Questions

**Q:** In the final report, what code do we need to include in the Appendix? Do we need to copy the entire ```main.c``` file into the report?

**A:** Please only include code that has been written by members of your team.

**Q:** How do I merge multiple PDFs into a single PDF?

**A:** Adobe Acrobat can do it, as can a number of other web-based tools.
