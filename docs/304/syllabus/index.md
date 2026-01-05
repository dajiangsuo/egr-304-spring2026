---
subtitle: Fall 2023 Syllabus
title: Embedded Systems Design Project I
course_num: EGR304
mainfont: Open Sans
sansfont: Open Sans
font_size: 12pt
#pagestyle: headings
pagestyle: plain
colorlinks: true
#linkcolor: 0x0000ff
#hyperrefoptions:
#- colorlinks=true
#- linkcolor=blue
#- urlcolor=blue
##  - citecolor: blue
#- anchorcolor=blue
#- bookmarks=true
#number-sections: true
#secnumdepth: 3
geometry:
- top=1in
- bottom=1in
- left=1in
- right=1in
papersize: letter
toc: false
toc-depth: 2
author-meta: Daniel M. Aukes and Kevin Nichols
---
# Embedded Systems Design Project I (EGR 304) Syllabus

## EGR 304 Course Catalog Description

Design, implement and debug an embedded electromechanical system through an in-depth design project. Develops professional and engineering skills in this project setting.

## Course Information

### Sections

| Section \# |       Times       |          Name           |       Email        |   Office    |                Photo                |
| :--------: | :---------------: | :---------------------: | :----------------: | :---------: | :---------------------------------: |
|   68188    | M/W 10:30-11:45AM |   [Dr. Dan Aukes][da]   | <danaukes@asu.edu> |  TECH 152   | ![](Danial-Aukes.png){width="100"}  |
|   64345    |  M/W 1:30-2:45PM  | [Dr. Kevin Nichols][kn] | <kwnicho@asu.edu>  | PRLTA 330-L | ![](Nichols-Kevin.png){width="100"} |

**Physical Location:** ASU Polytechnic Campus, Peralta Hall, Room 103 (PRLTA 103)  
**Number of Units:** 3  
**No Class or Office Hours on ASU Holidays:**

* *Labor Day Observed*: Monday, September 2, 2024
* *Fall Break*: October 12 - 15, 2024
* *Veteran`s Day Observed*: Monday, November 11, 2024
* *Thanksgiving Holiday Observed*: November 28 - 29, 2024

### Instructional Team

| Name             | email                      | role                |      section       |
| ---------------- | -------------------------- | ------------------- | :----------------: |
| Dan Aukes        | <danaukes@asu.edu>         | faculty             |  10:30am section   |
| Kevin Nichols    | <kwnicho@asu.edu>          | faculty             |   1:30pm section   |
| Shubham Mungekar | <smungeka@asu.edu>         | TA                  | 10:30am/1:30pm 304 |
| Asrith Pandreka  | <apandrek@asu.edu>         | Grader              | 10:30am/1:30pm 304 |
| Zeel Bhanderi    | <zbhander@asu.edu>         | Grader (in process) | 10:30am/1:30pm 304 |
| Ean Potter       | <ehpotter@asu.edu>         | UGTA                |    10:30am 304     |
| Justin Hanson    | <jthanso6@asu.edu>         | UGTA                |    10:30am 304     |
| Jillian Brooke   | <jlbrooke@asu.edu>         | UGTA                |     1:30am 304     |
| Alex Gutierrez   | <maguti43@asu.edu>         | UGTA                |     1:30am 304     |
| Manual Garcia    | <mgarci84@asu.edu>         | UGTA                |     4:30pm 314     |
| Scott Bainbridge | <Scott.Bainbridge@asu.edu> | Peralta Lab Manager |         -          |
<!-- Save for reference on future setup
| UGTA         | Richard Kovalcik<br><rrkovalc@asu.edu>                   | Cadence, KiCad, C/C++                                     | ![](Kovalcik.png)  |
| UGTA         | Bela (Salsabil) Abdelhamid Soliman<br><smsolima@asu.edu> | Cadence, KiCad, C, schematics                             | ![](Soliman.png)   |
-->

**Instructional Team office hours <!--#TODO: Fill in--> will be held in person (M - F) or on Zoom (Sa).**

#### Questions

* Post all questions to the **Canvas discussion board** to reach the professor, Student Instructional Team, and other members of the class. **Do not send emails through Canvas.**
* Any other communication tool such as Discord, Slack, etc, should only be used for communication within teams.

## 304 Prerequisites

* EGR 202, EGR 216, and EGR 219 with C or better

## Project Information

Please see the following two documents for more detailed information on the design project and requirements:

* [EGR 304 Project Description](/304/project-description/)
* [EGR 304/314 Course Sequence Requirements](/3x4/course-sequence-requirements/)

## Webpages

* Canvas (includes calendar, discussions, assignments): [http://canvas.asu.edu](http://canvas.asu.edu)
* Embedded Systems Design Resources: [https://embedded-systems-design.github.io](https://embedded-systems-design.github.io)
* Peralta Engineering Studios Information: [http://links.asu.edu/peralta](http://links.asu.edu/peralta)

## Textbook

* Scherz, P., & Monk, S. (2016). [Practical electronics for inventors, fourth edition.](https://www.amazon.com/Practical-Electronics-Inventors-Fourth-Scherz/dp/1259587541/ref=sr_1_1?s=books&ie=UTF8&qid=1470699914&sr=1-1&keywords=practical+electronics+for+inventors+4th+edition) New York: McGraw Hill. ISBN: 978-1259587542 ***(Required).* E-book available**
<!-- - Ulrich, K., Eppinger, S., Yang, M. [Product Design and Development, 7th Edition](https://www.amazon.com/Product-Design-Development-Karl-Ulrich/dp/1260566439/ref=sr_1_1?keywords=product+design+and+development+7th+edition&qid=1660414604&s=books&sprefix=product+design+and+development+7th+%2Cstripbooks%2C143&sr=1-1). McGraw-Hill Education. ISBN-13:‎ 978-1260566437 *(suggested)* **E-book available.** -->

## Classroom Safety

Approved personal protection equipment (PPE) is required when working in any ASU laboratory. Since Peralta 103 is an integrated classroom-laboratory workspace, <strong>close-toe shoes</strong> are <strong><ins>mandatory at all times</ins></strong>, and food / drink should not be consumed. When you do solder, remember it is required to turn on fume hoods and to wear safety glasses while soldering. Additionally, Peralta 103 and 109 are a non-lead solder work area due to the number of soldering stations that can possibly be in use at different points in time, so you are asked to <strong>refrain</strong> from bringing any lead percentage version of solder into these areas.

## Computer and Network Recommendations

* For KiCad:
    * PC or Mac with at least 5 GB free hard drive space, 8Gb RAM, Intel i5 or better.
* For Cadence:
    * PC or Mac (via Boot Camp/Parallels/etc.) with at least 25 GB free hard drive space, running Windows 10 (64-bit) Professional (not Starter or Home Basic) or higher
    * Recommended: Intel CoreTM i7 4.30 GHz or AMD Ryzen 7 4.30 GHz with at least 4 cores, 16 GB RAM, 50 GB free disk space, 1920 x 1200 display resolution. Full list of recommended specifications.
* Reliable broadband Internet connection (e.g., 3G, 4G, Cable, DSL, wifi)

## Course Learning Outcomes

Upon successful completion of this course, you should be able to:

### Engineering Problem Solving (ABET 1)

1. Design with and use a microcontroller
2. Design, build, test, and debug a printed circuit board
3. Design, program in C/C++, test, and debug embedded software
4. Interface with an embedded system wirelessly

### User Centered Design (ABET 2)

5. Develop design concepts based on specifications
6. Critique the design of an embedded system

### Communication (ABET 3)

7. Demonstrate the ability to present technical material orally
8. Demonstrate the ability to present technical material in writing

### Professional Context (ABET 4)

9. Describe the impact of embedded system on society

### Multidisciplinary Teamwork (ABET 5)

10. Demonstrate the ability to function in a team
11. Use collaboration technology to work in a team
12. Create a block diagram of an embedded system

### Critical Thinking & Decision Making (ABET 6)

13. Select and use sensors and actuators in an embedded system

### Strategic Learning (ABET 7)

14. Identify and find information necessary to design an embedded system

## Workspaces

It is your responsibility to maintain a clean and orderly classroom and lab space. Our resources are finite and your ability to complete your work may be impacted by the actions of others. If you see someone disrespecting the space, please reach out to the instructors and *CC* [Scott Bainbridge](mailto:sbainbr1@asu.edu@asu.edu). *Failure to respect the lab space may result in loss of lab privileges.*

If you see a workstation where tools, probes, or material are non-functioning, please email [Scott Bainbridge](mailto:sbainbr1@asu.edu@asu.edu) and *CC* the instructors.

* [Peralta Hall](https://maps.asu.edu/?id=120&mrkIid=62709), Room 103 ([Peralta Engineering Studios](http://links.asu.edu/peralta)) is our primary workspace with electronic components and test equipment. It is available for use while other classes are in session <ins> with permission from the instructor</ins>.

    > <strong>Note</strong>:
    > Closed-toe shoes are mandatory in Peralta Studios at all times. Do not wear flip-flops or sandals to class. You are also required to wear safety glasses when operating specific tools such as soldering irons.

    **Lab Manager:** [Scott Bainbridge](mailto:sbainbr1@asu.edu@asu.edu).

* [Peralta Hall](https://maps.asu.edu/?id=120&mrkIid=62709), Room 109 ([Peralta Engineering Studios](http://links.asu.edu/peralta))([Hours](https://peraltastudios.engineering.asu.edu)) has a printed circuit board manufacturing line. It is available during the day and selected evenings and weekends.

    **Lab Manager:** [Scott Bainbridge](mailto:sbainbr1@asu.edu@asu.edu).

* The [Innovation Hub](https://poly.engineering.asu.edu/research/innovationhub/) ([Technology Center](https://maps.asu.edu/?id=120&mrkIid=62734), Room 199, [hours](https://poly.engineering.asu.edu/research/innovationhub/)) has a variety of prototyping equipment, including a Shop Bot (2-D wood router), laser cutter and engraver, 3D printer, 3D scanner, vinyl cutter, sewing machines, vacuum former (useful for creating project enclosures), and more.

    **Lab Manager:** [Sean Dengler](mailto:dengler@asu.edu)

* The [Simulator Building](https://maps.asu.edu/?id=120&mrkIid=62727) has a machining and manufacturing center with CNC mills and lathes, a welding room, and fiberglassing equipment.

    **Lab Manager:** [Josh Patton](mailto:jdpatto1@asu.edu)

* The [Polytechnic Campus Library](https://maps.asu.edu/?id=120&mrkIid=63247) has small group meeting rooms with whiteboards and is [open late](https://lib.asu.edu/hours).

## Community Values

* We engage in the process of innovation.
* We help each other become better.
* We identify needs and recognize design opportunities.
* We follow an engineering design process.
* We are creative - you have the license to "think outside the box".
* We fail early and often but keep going.
* We take risks, as engineering design involves LOTS of iteration.
* We build on each other's ideas and strengths in our design community.
* We contribute to our teams.
* We are comfortable with ambiguity.
* We make convincing arguments based on sound technical principles for why a solution meets a need.
* We communicate and document in multiple ways - orally, visually, interpersonally, written, in person and virtually.

## Professionalism

> This course is welcome to individuals of all visible and nonvisible differences. All members of this class are expected to contribute to a respectful, welcoming and inclusive environment for every other member of the class.

A portion of your grade will be based on your individual professionalism in the course with regard to the respect you show the people around you, the resources provided, and the physical space. This grade will be based on formal and informal communication with your team, classmates, teaching staff, and external stakeholders (if applicable). Your conduct in the classroom, office hours, and in the Peralta Lab space will be considered.  

If you would like to let us know about something positive or negative you observe in a context related to this course, please fill out a [professionalism form](https://docs.google.com/forms/d/e/1FAIpQLSfP8GehhS1Ae9yY8yq5rLVQPX-wnkc98QiYxYWY4vAaJGSsew/viewform?usp=sf_link).  We will follow up with you if we need details or have questions.

## Attendance

On-time attendance and participation in class activities is an essential part of the learning process, and students are expected to attend class regularly. **[Attendance will be taken](https://docs.google.com/spreadsheets/d/1oD6AKyehDSWOM9dGUFJ24iwgaFHtzkeWIrDxPZsalSA/edit?usp=sharing) by a TA or professor at the beginning and/or the end of each class session.** If you are not physically present at the time attendance is taken, <ins>you <strong>will not be counted </strong> as present for that class session</ins>.

You may miss up to **3** class sessions without penalty. Beginning with your fourth absence, <ins>each missed class session will result in the <strong>loss of 200</strong> points from your final grade</ins>. You can [check your attendance here](https://docs.google.com/spreadsheets/d/1-nrPrLC7SZ2o-j3tgH8tFHUR4pvp3lwE8H-N-UXpx_o/edit?usp=sharing). Some absences are, however, unavoidable. Excused absences for classes (with prior notification to your professor) will be given without penalty to the grade in the cases of:

1. A university-sanctioned event [ACD 304--02](https://public.powerdms.com/ASU/documents/1557490fZAJGwgVrSll_r4&opi=89978449)
2. Religious holidays [ACD 304--04](https://public.powerdms.com/ASU/documents/1541225); a [list can be found here.](https://eoss.asu.edu/cora/holidays)
3. Work performed in the line-of-duty according [SSM 201--18](https://public.powerdms.com/ASU/documents/1560515)
4. Illness, quarantine or self-isolation related to illness as documented by a health professional.

> <strong>Note</strong> that class sessions may be recorded, and recordings provided to enrolled students, instructors or instructional support personnel. If you have concerns about being recorded, please contact your professor.

## Course Expectations

* **Active participation in and technical contribution to your team is required.** Students with concerns about the participation or contributions of a team member can nominate them for a "pink slip" by emailing the professor during one of the team evaluation weeks (see the course calendar on [Canvas](https://canvas.asu.edu/)). At the professor's discretion, a pink slip will be issued or the student removed from their team. Students who receive a pink slip must meet virtually with their professor to determine a remediation plan, which must be completed by a professor-determined deadline in order to remain on their team. Students who receive a pink slip will also receive an Academic Status Report. Students who are removed from their team must complete the semester project alone.
* **This is a time-intensive class that requires significant work outside of scheduled class meeting times. Plan on spending *at least* 6 - 8 hours per week outside of scheduled class sessions.** If you cannot make this commitment, please see your professor.
* **Professionalism is required** in all communication related to this course, including in-class discussions, presentations, canvas discussion board posts, and e-mail. We will not reply to rude or unprofessional emails. In addition, please preface the subject line of all emails to professors or course staff with \[ESD\].
* If your success in this class is in question, please see your professor. The sooner you do, the more likely we will be able to find a resolution.
* Embedded Systems Design Project class time is for Embedded Systems Design Project class work *only*.

## Deliverables

This course will consist of individual in-class work, homework assignments, and team assignments. A current schedule of deliverables is available in the calendar on [Canvas](https://canvas.asu.edu). All deliverables are due at 11:59 PM on the due date unless otherwise specified. **It is the responsibility of your team members to check whether each of your Canvas submissions were successful. We recommend that you take a screenshot of each successful submission to provide evidence in case the submission goes awry. If you are unable to submit to Canvas due to a system outage, email the submission to your instructor before the assignment deadline.**

Please follow the instructions in the [Document Submission Best Practices](/3x4/submission-best-practices/) document for detailed information on how to submit files in this class.

Many assignments impact subsequent ones and/or are reviewed multiple times as part of the "checkpoint" process (see below). It is therefore in the students' best interests to seek out advice and guidance from the teaching team, including instructors, TA's and graders. *Not all teaching team members will give the same advice, however*. We thus recommend obtaining ***multiple points of view***. It is the responsibility of the student to seek out that advice and implement a solution that addresses the feedback received.

### Individual Deliverables

1. **In-Class Checkoffs** -- Throughout the semester, there will be in-class activities to help you learn critical knowledge and skills for your project.
2. **Individual Homeworks** -- Throughout the semester, you will develop and demonstrate content knowledge on specific technical topics. This will culminate in you individually designing, building, testing, and demonstrating an acceptable subsystem, for use in your team's project.
3. **Mid-Semester and End-of-Semester Team Member Effectiveness Surveys (CATME)** -- A portion of your grade will be based on peer evaluations. You must complete this survey in both the middle and end of the semester to evaluate the effectiveness of and provide constructive feedback to your team.
4. **Professionalism -** A portion of your grade will be based on your individual professionalism in the course. See the section on professionalism for more information.

### Team Deliverables

1. **Team Design Workflow Homeworks -** These assignments will lead your team through a semester-long customer discovery and design process. Draft assignments will be checked off in class for feedback, submitted to Canvas for a grade, *and* deposited into your living report document (described below) for grading at each checkpoint.
2. **Project Checkpoints** -- There will be three major project checkpoints throughout the semester for presenting your work and receiving more detailed oral and written feedback. They will consist of the following deliverables:
    1. **Team Presentations** reviewed in depth by experts including faculty members, course staff, project stakeholders, industry representatives, past students, and your classmates.
    2. **Living Project Report** -- This report will document your team's progress through the embedded system design process. They will include all team assignments, and the checkpoints will provide a mechanism for instructors to give more detailed and in-depth feedback than during initial in-class homework checkoffs. Team documents will be reviewed at each checkpoint, requiring them to stay up-to-date.
    3. **Updated Team Repository** containing the latest versions of team assignments in the living project report, in addition to supporting files, appendices, and collected information. **Must be electronic** on Google Drive (<http://drive.google.com>)
3. **Stand Ups** -- on selected days, one member from each team will stand up and share a 1-minute team progress report.

### Notes

* There will be no final exam.
* You will receive [formative feedback](https://sites.tufts.edu/teaching/assessment/assessment-approaches/formative-and-summative-feedback/) on assignments throughout the semester.
* Team members who do not participate in a presentation or demonstration **will not receive credit for it**.
* Team members who do not lead the design on at least one acceptable embedded (hardware/software) subsystem (see Project Description) for their team's project **will not receive credit** for the project. This is an embedded systems design class, not a mechanical design class.
* There will be **no opportunities for extra credit**. Instead, please put your time into completing the regular assignments.

## Course Structure, Assessment, and Grading Policies

### Assignments (deadlines listed on Canvas)

| Assignment                                 | Individual Points | Team Points | %    |
| ------------------------------------------ | ----------------- | ----------- | ---- |
| icc-01-supplies-regulators-multimeters-304 | 50                | 0           | 0.6  |
| icc-02-hello-world-psoc-304                | 50                | 0           | 0.6  |
| icc-03-mosfets-and-h-bridges-304           | 50                | 0           | 0.6  |
| icc-04-analog-io-and-uart-304              | 50                | 0           | 0.6  |
| icc-05-filtering-analog-signals-304        | 50                | 0           | 0.6  |
| icc-06-hardware-orders-304                 | 50                | 0           | 0.6  |
| icc-07-bluetooth-with-psoc-304             | 50                | 0           | 0.6  |
| ind-01-power-supply-schematic              | 300               | 0           | 3.4  |
| ind-02-psoc-in-depth-304                   | 300               | 0           | 3.4  |
| ind-03-using-the-pwm-subsystem             | 300               | 0           | 3.4  |
| ind-04-amplifying-analog-signals           | 300               | 0           | 3.4  |
| ind-05-subsystem-design-304                | 600               | 0           | 6.7  |
| ind-06-subsystem-verification-304          | 600               | 0           | 6.7  |
| ind-07-cadence-schematic-design            | 300               | 0           | 3.4  |
| team-00-team-repository                    | 0                 | 50          | 0.6  |
| team-01-team-organization-charter-304      | 0                 | 50          | 0.6  |
| team-02-stakeholder-interviews             | 0                 | 50          | 0.6  |
| team-03-user-needs-and-benchmarking-304    | 0                 | 50          | 0.6  |
| team-04-product-requirements               | 0                 | 50          | 0.6  |
| team-05-design-ideation-304                | 0                 | 50          | 0.6  |
| team-06-checkpoint-1-304                   | 0                 | 800         | 8.9  |
| team-07-block-diagram-304                  | 0                 | 50          | 0.6  |
| team-08-component-selection-304            | 0                 | 50          | 0.6  |
| team-09-hardware-proposal-304              | 0                 | 50          | 0.6  |
| team-10-software-proposal-304              | 0                 | 50          | 0.6  |
| team-11-checkpoint-2-304                   | 0                 | 1050        | 11.7 |
| team-hardware-implementation-304           | 0                 | 300         | 3.4  |
| team-software-implementation-304           | 0                 | 300         | 3.4  |
| team-system-verification-304               | 0                 | 1000        | 11.2 |
| team-checkpoint-3-304                      | 0                 | 1200        | 13.4 |
| catme-teammaker-304                        | 0                 | 0           | 0    |
| catme-1                                    | 150               | 0           | 1.7  |
| catme-2                                    | 150               | 0           | 1.7  |
| catme-3                                    | 150               | 0           | 1.7  |
| professionalism                            | 300               | 0           | 3.4  |
| Subtotal                                   | 3800              | 5150        |
| Percentage of Total                        | 42                | 58          |
| Total                                      | 8950              |             |


### Grading Policies

* Students must be present during team presentations and demonstrations in order to receive credit.
* Assignments that require a Canvas submission must be submitted to Canvas in order to receive credit.
* Assignments submitted incorrectly (e.g., incorrect file types, some required files missing) but that are still "gradable" will lose 25% of the total points that the assignment is worth. Refer to the [Document Submission Best Practices](/3x4/submission-best-practices/) document for detailed information.
* The grading scale for this course is as follows:

#### Grading Scale

The grading scale for this course is as follows:

| Letter Grade | : **Cutoff % |
| ------------ | ------------ |
| A+           | 97%          |
| A            | 93%          |
| A-           | 90%          |
| B+           | 87%          |
| B            | 83%          |
| B-           | 80%          |
| C+           | 77%          |
| C            | 70%          |
| D            | 60%          |
| E            | 0%           |

*Cutoffs may be lowered but will never be raised.*

#### Late Assignments

Late assignments will be graded as follows:

| Late submission time (hours) | $f(a,c,t)$     |
| ---------------------------- | -------------- |
| $t  \leq  0$                 | $a  -  c*0%$   |
| $0 < t  \leq  24$            | $a  -  c*10%$  |
| $24 < t  \leq  48$           | $a  -  c*25%$  |
| $48 < t  \leq  96$           | $a  -  c*50%$  |
| $96 < t$                     | $a  -  c*100%$ |

where $f(a,c,t)$ is the final assignment grade, $a$ is the raw assignment grade before any late penalty deduction, $c$ is the total number of points that the assignment is worth, and $t$ is the number of hours that an assignment was submitted after the submission deadline.

* Late homework demonstrations will be graded using the same equation above but excluding days with no office hours.
* The late policy does not apply to the following homework types:
    * In-Class Checkoffs
    * CATME Submissions
    * Team Assignment Draft Submissions
    * Checkpoint 3 Submissions
    * Final System Verification
* **Absolutely no submissions will be accepted after 11:59 p.m. on Monday, December 9, 2024.**

#### General Grading Rubric

Unless otherwise specified in assignments, we will use the following grading rubric:

| Quality                    | Points |
| -------------------------- | ------ |
| Exceeds Expectations       | 100    |
| Above Expectations         | 85     |
| Meets Expectations         | 70     |
| Below Expectations         | 55     |
| Does Not Meet Expectations | 40     |
| Not Submitted              | 0      |

#### Team Assignments

The purpose of initial team assignments (low-point-value first submissions of team assignments) is to obtain feedback from the teaching team. If the assignments are presented in incomplete form, it is impossible for the teaching team to deliver high-quality feedback that can be acted upon for project checkpoints.

Therefore, incomplete draft assignments will be graded on a complete / incomplete basis. Complete submissions will receive 100% of the available points. Incomplete submissions will receive 0%. It is at the instructor's discretion to award partial credit in extraordinary circumstances.

#### Demonstrations

Many homework assignments require checkoffs from a teaching team member to demonstrate system functionality. Individual demonstration items will be graded on a complete / incomplete basis unless otherwise stated. No partial credit will be given.

## Additional Information

* The campus provides a number of valuable resources to help you achieve both personal and academic success. These include:
    * Student Success and Writing Center - <http://tutoring.asu.edu> The Poly Tutoring & Writing Center offers free academic support services to all ASU students. At the Poly Tutoring & Writing Center, you will receive help in math, science, engineering, computer science, and writing. To book an appointment, please use [their website](https://tutoring.asu.edu/tutor-search) or call 480-727-1452.
    * Counseling Center - <https://eoss.asu.edu/counseling>
    * Career & Professional Development Services - <https://eoss.asu.edu/cs>
    * Other [Student Resources](https://engineering.asu.edu/resources/) from the Ira A. Fulton Schools of Engineering
* **Academic Integrity.** Students in this class must adhere to [ASU's academic integrity policy](https://provost.asu.edu/academic-integrity/policy). Students are responsible for reviewing this policy and understanding each of the areas in which academic dishonesty can occur. In addition, all engineering students are expected to adhere to both the [ASU Academic Integrity Honor Code](https://provost.asu.edu/academic-integrity/honor-code) and the [Fulton Schools of Engineering Honor Code](https://engineering.asu.edu/ira-a-fulton-schools-of-engineering-honor-code/). **All academic integrity violations will be reported to the Fulton Schools of Engineering Academic Integrity Office (AIO).** The AIO maintains a record of all violations and has access to academic integrity violations committed in all other ASU colleges/schools.
* **Generative AI.** Use of generative AI is generally permitted within guidelines. Artificial intelligence (AI), including ChatGPT, are being used in workplaces all over the world to save time and improve outcomes by generating text, images, computer code, audio, or other media. Use of AI tools is generally welcome and encouraged in this class with proper disclosure of use as described in each assignment. AI tools might be employed to brainstorm, draft, edit, revise text and code. Any submitted course assignment not explicitly identified as having used generative AI will be assumed to be entirely your original work. Using AI tools to generate content without proper disclosure will be considered a violation of [ASU's academic integrity policy](https://provost.asu.edu/academic-integrity/policy) and students may be sanctioned for confirmed, non-disclosed use. If at any point you have questions about what is permitted, contact the instructor to discuss *before* submitting work.
* **Copyrighted Materials.** The contents of this course, including lectures and other instructional materials, are copyrighted materials. Students may not share outside the class, including uploading, selling or distributing course content or notes taken during the conduct of the course. Any recordings of class sessions is authorized only for the use of students enrolled in this course during their enrollment in this course. Recordings and excerpts of recordings may not be distributed to others (see [ACD 304--06](https://www.asu.edu/aad/manuals/acd/acd304-06.html), "Commercial Note Taking Services" and ABOR Policy [5-308 F.14](https://public.azregents.edu/Policy%20Manual/5-308-Student%20Code%20of%20Conduct.pdf) for more information).
    * You must refrain from uploading to any course shell, discussion board, or website used by the course instructor or other course forum, material that is not the student\'s original work, unless the students first comply with all applicable copyright laws; faculty members reserve the right to delete materials on the grounds of suspected copyright infringement.
* **Policy Against Threatening Behavior.** Per the Student Services Manual [SSM 104-02](https://www.asu.edu/aad/manuals/ssm/ssm104-02.html)**,** students, faculty, staff, and other individuals do not have an unqualified right of access to university grounds, property, or services. Interfering with the peaceful conduct of university-related business or activities or remaining on campus grounds after a request to leave may be considered a crime. All incidents and allegations of violent or threatening conduct by an ASU student (whether on- or off-campus) must be reported to the ASU Police Department (ASU PD) and the Office of the Dean of Students.
* **Disability Accommodations.** Suitable accommodations are made for students having disabilities. Students needing accommodations must register with [Student Accessibility and Inclusive Learning Services](https://eoss.asu.edu/drc) and provide documentation of that registration to the instructor. Students should communicate the need for an accommodation in sufficient time for it to be properly arranged. See [ACD 304-08](https://www.asu.edu/aad/manuals/acd/acd304-08.html) Classroom and Testing Accommodations for Students with Disabilities.
* **Harassment and Sexual Discrimination.** Arizona State University is committed to providing an environment free of discrimination, harassment, or retaliation for the entire university community, including all students, faculty members, staff employees, and guests. ASU expressly prohibits discrimination, harassment, and retaliation by employees, students, contractors, or agents of the university based on any protected status: race, color, religion, sex, national origin, age, disability, veteran status, sexual orientation, gender identity, and genetic information.

    Title IX is a federal law that provides that no person be excluded on the basis of sex from participation in, be denied benefits of, or be subjected to discrimination under any education program or activity. Both Title IX and university policy make clear that sexual violence and harassment based on sex is prohibited. An individual who believes they have been subjected to sexual violence or harassed on the basis of sex can seek support, including counseling and academic support, from the university. If you or someone you know has been harassed on the basis of sex or sexually assaulted, you can find information and resources at [https://sexualviolenceprevention.asu.edu/faqs](https://sexualviolenceprevention.asu.edu/faqs).

    **Mandated sexual harassment reporter:** As mandated reporters, professors are obligated to report any information we become aware of regarding alleged acts of sexual discrimination, including sexual violence and dating violence. ASU Counseling Services, [https://eoss.asu.edu/counseling](https://eoss.asu.edu/counseling), is available if you wish to discuss any concerns confidentially and privately.

> **Any information in this syllabus (other than grading and absence policies) may be subject to change with advance notice.**

<!-- 
## Extra Stuff to Save

- ## EGR314 Course Catalog Description

- Applies design principles to conceptualize, implement and characterize an embedded electromechanical system in a project setting. Project emphasizes communication with project stakeholders; applying a human-centered design approach in the context of an embedded system; critical thinking in developing system specifications and evaluating a prototype relative to these specifications; and increasing technical competence.

&nbsp;

- The following items will be required in the event that the university returns to sync or fully remote learning during the semester:

    - Webcam and/or cell phone camera (for assignment demonstrations)

    - Headset/earbuds and microphone (either built-in or separate)

## 314 Prerequisites

- Required: Embedded Systems Design Project I (EGR 304) with C or better

- Recommended Co-Requisite: Microcontrollers in Smart Systems (EGR 338)

EGR314

- Martin Luther King Jr. Day: Jan 16, 2023

&nbsp;

- Spring Break: March 5 - 12, 2023

## EGR314 Course Learning Outcomes

Upon successful completion of this course, you should be able to:

#### Engineering Problem Solving (ABET 1)

1. Select and use sensors and actuators in an embedded system

2. Choose and design with a microcontroller

3. Design, build, test, and debug a printed circuit board

4. Design, program in C/C++, test, & debug embedded systems software

5. Communicate among multiple chips or devices

6. Use hardware or software interrupts in an embedded system

7. Interface with an embedded system wirelessly

#### User Centered Design (ABET 2)

8. Develop design concepts based on specifications

9. Critique the design of an embedded system

#### Communication (ABET 3)

10. Demonstrate the ability to present technical material orally

11. Demonstrate the ability to present technical material in writing

#### Professional Context (ABET 4)

12. Describe the impact of embedded system on society

#### Multidisciplinary Teamwork (ABET 5)

13. Demonstrate the ability to function in a team

14. Use collaboration technology to work in a team

15. Create a block diagram of an embedded system

#### Critical Thinking & Decision Making (ABET 6)

16. Test and demonstrate embedded system components and system functionality

#### Strategic Learning (ABET 7)

17. Identify and find information necessary to design an embedded system

## Computer and Network Requirements for All Students

PC or Mac (via Boot Camp/Parallels/etc.) with at least 25 GB free hard drive space, running Windows 10 (64-bit) Professional (not Starter or Home Basic)

Recommended: Intel CoreTM i7 4.30 GHz or AMD Ryzen 7 4.30 GHz with at least 4 cores, 16 GB RAM, 50 GB free disk space, 1920 x 1200 display resolution. Full list of recommended specifications. -->

[da]:https://search.asu.edu/profile/2727366
[kn]:https://search.asu.edu/profile/361106
