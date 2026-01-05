---
subtitle: Robotic Adaptive Apparel for Pediatric Cancer Patients
title: EGR304 Fall 2023 Project Description
---

## Background

A number of trends have emerged in bicycling over the past decade.  First of all, the popularity of bicycling soared, especially during the COVID pandemic.  At the same time, the integration of active technology into bicycle components has made it possible to integrate phone and app-assisted features into bicycles.  E-bike popularity has soared as well, thanks to the growing availability of low-cost battery technology.  Yet, as traffic and congestion continue to grow in towns and cities, this often puts drivers and bikers at odds with one another in terms of space, safety, and visibility.

## Project Brief

This semester, your team will design, build, test, and showcase an innovative solution for byclists


### Project Challenge

In your project you will:

* Develop an understanding of the needs of each stakeholder, through specific need-finding activities.
* Create a set of specifications that meet the needs of your **primary** stakeholder, while considering the needs of *other* stakeholders.
* Ideate a number of design concepts that satisfy the specifications you developed
* Downselect your concepts based on feedback received from the instructional staff and stakeholders.

Your team will then **develop a unique project concept** and participate in design reviews at checkpoints throughout the semester. Your team will develop a set of engineering design requirements based on your analysis of the chosen concept and the intended audience. Finally, your team will design, build, and test a fully-functioning embedded system that meets the identified needs. Most design work (aside from individual subsystems) will be done as a team and combined.

Successful projects will:

1. Address user and stakeholder needs
1. Clearly delineate the path project teams took from stakeholder interviews through needfinding, product requirements generation, and design concepts, into a full, detailed design.
1. Involve an embedded system as the focal point of the proposed solution, based on material taught in this course.
1. Result in a working device that meets all course requirements

> **Your project cannot be a replica of existing projects described on Instructables, Make Magazine, etc. nor the same concept discoverable via Google.**


### Stakeholders

In your design process you must consider the needs of various stakeholders. These include (but are not limited to):

* Professional Cyclists
* Casual biyclists
* Parents of children with bicycles
* People who share the road with bicyclists
* ... and more

Your job will be to connect with 1-2 communities of these stakeholders and to identify the needs specific to this group.

### Motivations

Different stakeholders may have different goals regarding new product offerings, including

* Health
* Performance
* Safety
* Visibility
* Accessibility
* Security and Theft Prevention
* ... and more.

It will be your job to identify the needs of your selected users and stakeholders in order to ideate and develop a unique concept.


## Subsystems

Each individual is required to design, build, and verify their own subsystem.  The typical system board will consist of four subsystems (one per teammate in a 4 person team), such as:

* Microcontroller & Voltage Regulator (required)
* Analog Sensors
* Digital Sensors using a serial protocol to communicate
* H-Bridge-based motor drivers, using wired control
* Motor drivers using serial communication

We have also seen

* Amplified Audio Drivers
* other special cases involving PCB design and software interaction.

> Please note that special subsystems require written approval from the instructor.

### Voltage Regulator and Microcontroller Subsystem

The voltage regulator & microcontroller subsystem is the heart of any embedded system, is required for all projects, and is considered one subsystem.

#### Voltage Regulator

At least one voltage regulator must be included in final project.  See the table below for required specifications.

| 304         | 
| ----------- | 
| linear type | 
| 5V          | 

> You may not use a USB power bank to power your system.

#### Required Microcontroller Subsystem module for team final project

| 304                                      | 
| ---------------------------------------- | 
| CY8CKIT-142 (BLE) or CY8CKIT-143-A (BLE) | 


> The teammate responsible for the microcontroller subsystem is also responsible for the power supply.

#### Communication  

| 304             | 
| --------------- |
| UART (for debugging with PC) |

#### Wireless Requirements

| 304                                                      |
| -------------------------------------------------------- |
| Board-to-Phone duplex communication over Bluetooth$^{1}$ |

$^{1}$Duplex, or bidirectional capability must play a meaningful role in the use of system function.


### Sensor And Actuator Subsystems

| 304                                                                        | 
| -------------------------------------------------------------------------- | 
| At least 1 signal conditioned, amplified analog sensor                     | 
| At least 1 motor or linear actuator with bidirectional control ability$^*$ | 

All sensor and actuator subsystems must use custom software to read, filter (if necessary), and control microcontroller output(s) via the required microcontroller.  Additionally, all **analog sensor subsystems** must use custom-designed, non-trivial, hardware-based, amplification and filtering.  

> Teams may not duplicate subsystems.  This means they must be materially different, using different chips, design processes, and accomplishing different functions

Please see the sections at the bottom of the course sequence requirements page regarding permitted [analog sensors](/3x4/course-sequence-requirements/#permitted-analog-sensors), permitted [serial sensors](/3x4/course-sequence-requirements/#permitted-serial-sensors), and permitted [actuators](/3x4/course-sequence-requirements/#permitted-actuators).  For example, RC Servos, are **not permitted** in EGR304.

> $^*$ **(304 Only)** Please see your instructor if you would like to consider using a motor for power generation rather than to create motion.
