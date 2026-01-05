---
title: Team System Verification
---

***Multi-Part Team Assignment***

## Objectives

To demonstrate how your project's components work independently and with each other in your final PCB. This assignment will help you plan your verification strategy and communicate what needs to be tested to instructors.

The Teaching Team will make a copy of your team's updated verification table to share back with the team for tracking progress. You will then check off as a team against that document.

## Resources

- [Verification Table Example and Template](https://www.dropbox.com/s/b2g9anxlmh5emlj/Verification%20Table%20Example%20and%20Template.xlsx?dl=0)
- Canvas discussion board

### Part 1 Submission: Block Diagram and Project Verification Table (Team)

* Ensure your block diagram and verification table are up to date
* **Part 1-1: Updated Block Diagram in PDF format.** Submit to Canvas by the deadline in the course calendar on Canvas. Make sure your block diagram and verification table are up to date.
* **Part 1-2: Final Project Verification Table.** Submit a *link* **(not a PDF or XLS)** to your completed Project Verification Table in Google Drive to this assignment on Canvas by the deadline in the course calendar on [Canvas](https://canvas.asu.edu). Make sure that the version is editable by the following course staff:

    The graders will make a copy of your team's Project Verification Table for your team and share it back with each of you (read only) via Google Drive. The grader's copies will be used for checking off the team's project.

    It is your responsibility to ensure that your submission to Canvas was successful. Late Canvas submissions will be graded per the policy in the syllabus. No credit will be awarded for assignments not submitted to Canvas.

### Part 2: Prior to Teaching Team Verification (Team)

**Verification must occur on your team's final full combined PCB, not on breadboards, perfboards, protoboards, or individual subsystem PCBs.**

1. On your team's combined PCB, verify that all of the subsystems/components work *independently*. As you verify each subsystem/component, update your local copy of the Verification Table to change the ```u``` on the diagonal for each subsystem to an ```x``` indicating that you have verified the subsystem/component.
2. On your team's combined PCB, independently verify that all of the subsystems work *with each other*, referencing your local copy of the Verification Table to determine which subsystems should be connected to each other. As you verify connections between each subsystem/component, update your local copy of the Verification Table to change the ```u``` to an ```x``` indicating that your team has verified the connection.

### Part 2 Submission: None

### Part 3: Teaching Team Verification (Team)

**Verification must occur on your team's final full combined PCB, not on breadboards, perfboards, protoboards, or individual subsystem PCBs.**

1. In office hours (or in class as time permits), prepare your hardware and software to demonstrate.
2. Show the markings (team number) on your team's combined PCB. ***You must show these markings every time you check off your PCB.***
3. On your team's combined PCB, demonstrate each of the subsystems independently that have been verified by you (```x``) but not yet been verified by the teaching team. The teaching team will update the appropriate Project Verification Table cells from ```x``` to ```v``, *with their initials and the date*, to indicate that the subsystem has been verified.
4. On your team's combined PCB, demonstrate each of the subsystems connecting to other subsystems that have been verified by your team (```x``) but not yet been verified by the teaching team. The teaching team will update the appropriate Project Verification Table cells from ```x``` to ```v``` to indicate that the connection has been verified.
5. You may continue to check off unverified subsystems and connections up to the deadline in the calendar on Canvas.

### Part 3 Submission: None

## Grading

### EGR 304

The last opportunity for grading is noted in the calendar on Canvas (last office hours of the day). No late checkoffs will be accepted.

| **Item**                                                                                                                                                                                                                 | **Points** | **Grade** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | ----------|
| **Part 1-1.** Updated block diagram in PDF format submitted to Canvas by the due date noted in the assignment on Canvas<br>*(-10 points per error up to total, required for grading)*                                    | **100**    | Team      |
| **Part 1-2.** Final Hardware and Software Verification Table stored on your team's Google Drive and a link submitted to Canvas by the due date noted in the assignment on Canvas<br>*(-10 points per error up to total)* | **100**    | Team      |
| **Part 2.** *No demonstration or submission required*                                                                                                                                                                    | **0**      | **None**  |
| **Part 3.** Teaching team verification of your team's project. No submission required. Grade for **Part 3** will be calculated on the final verification deadline as follows:                                            | **800**    | Team      |
| # of teaching team-verified subsystems<br>(#```v``` along diagonal) <br>---------------------------------------------------------------------- * 200<br>total # subsystems<br>(# cells along diagonal)                               | **200**    | Team      |
| # of teaching team-verified connections between subsystems<br>(#```v``` not along diagonal)<br>---------------------------------------------------------------------------------------------------- * 600<br>total # connections between subsystems<br>(#```u``` + #```x``` + #```v``` not along diagonal)                             | **600**    | Team      |
| **Total**                                                                                                                                                                                                                | **1000**   | Team      |

### EGR 314

The last opportunity for grading is noted in the calendar on Canvas (last office hours of the day). No late checkoffs will be accepted.

| **Item**                                                                                                                                                                                                                 | **Points** | **Grade**                                                                   |             |      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------------------------------------------------------------------- | ----------- | ---- |
| **Part 1-1.** Updated block diagram in PDF format submitted to Canvas by the due date noted in the assignment on Canvas<br>*(-10 points per error up to total, required for grading)*                                    | **25**     | Team                                                                        |             |      |
| **Part 1-2.** Final Hardware and Software Verification Table stored on your team's Google Drive and a link submitted to Canvas by the due date noted in the assignment on Canvas<br>*(-10 points per error up to total)* | **25**     | Team                                                                        |             |      |
| **Part 2.** *No demonstration or submission required*                                                                                                                                                                    | **0**      | **None**                                                                    |             |      |
| **Part 3.** Teaching team verification of your team's project. No submission required. Grade for **Part 3** will be calculated on the final verification deadline as follows:                                            | **650**    | **Team**                                                                    |             |      |
| # of teaching team-verified subsystems<br>(#```v``` along diagonal)                                                                                                                                                        | /          | total # subsystems<br>(# cells along diagonal)                              | (out of 50) | Team |
| # of teaching team-verified connections between subsystems<br>(#```v``` not along diagonal)                                                                                                                                | /          | total # connections between subsystems<br>(#```u``` + #```x``` + #```v``` not along diagonal) | (out 600)   | Team |
| **Total**                                                                                                                                                                                                                | **700**    | **Team**                                                                    |             |      |

## Frequently Asked Questions

**Q:** Do all of our subsystems need to be verified by the Part 1 deadline?

**A:** No. The Part 1 deadline is simply to submit your completed table with all of the boxes completed.

---

**Q:** Do we have to have all of our code written?

**A:** Mostly yes. You need to have enough done so that you can demonstrate independent operation of subsystems, and that subsystems are able to work with the subsystems to which they are connected.

## Most Common Mistakes

- Make sure that your power source (battery / plug-in supply) and voltage regulator(s) are all listed as separate rows/columns on the verification table.
- For op amps, include the sensor associated with them for clarity (e.g., "Ultrasonic Opamp")
- If you have multiple of the same device (e.g., 2 motors and 2 motor drivers), each must be listed separately (e.g., Motor Driver 1, Motor 1, Motor Driver 2, Motor 2) as one working correctly does not mean that both will work correctly.
- Make sure that at least 2 members of your team double-check all of the ```u``` / ```nc``` cells in the spreadsheet. This verification is critical as it will help to make sure your team members are on the same page with the system design.
- ***(EGR 314 only)*** The ESP32 should only be connected to power (3.3V or 5V) and the PIC via UART (we have determined over spring break that the I<sup>2</sup>C drivers on the ESP32 will not work easily with the PIC). Your ESP32 should have no direct connections to any of your sensors or actuators. If your PIC is running at 5V, you will need level shifting circuitry on the UART TX line from the PIC to the ESP32. This should be reflected in both your block diagram as a level shifting block and in your verification table.
