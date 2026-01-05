---
title: 304 HW4 -- Amplifying Analog Signals
---

> **This is an individual homework assignment** but you may work with others to determine how to complete the assignment.  All work demonstrated in checkoff must be completed by you on your own board.

## Objectives

The purpose of this assignment is to understand how Op-Amps can be used to amplify the current change in a device and output it as a voltage. We will be building two circuits: an inverting amplifier, and a noninverting amplifier, and learning about the differences. The signal you read will be derived from HW3's PWM Output

**An individual live demonstration of Parts 3, 4, & 5 (which includes Parts 1 and 2) of this assignment is required.**

## Walkthrough Video (Thanks Ean)

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ttM15kePqQI?si=wmPTqqQbPiV4AH3s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Resources

* [Enable floating point support](https://embedded-systems-design.github.io/enable-floating-point-support/) in PSoC Creator
* Videos
    * [Video Walkthrough](https://www.youtube.com/watch?v=ttM15kePqQI) (Thanks Ean)
    * [Older Video Walkthrough](https://youtu.be/sMMXunHu-to) (Thanks Milan!)
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
| DAC low-pass filter circuit from HW3 Part 3     | 1            | See HW3                                                                                                                                                                                                          |
| Voltage Regulator circuit from HW1 *(optional)* | 1            | See HW1                                                                                                                                                                                                          |
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

1. Once HW3 is checked off, **keep the connection from the PWM_4 subsystem to the low-pass filter on your breadboard in place.** You may disconnect the output jumper wires connecting the PSoC to the MOSFET and FAN80100N motor driver.
1. Copy the HW3 "PWMAnalog" project into a new workspace named "HW4"
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

## Part 2: Schematic

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

## Individual Demonstration of Proficiency

You must complete the demonstration individually, either in office hours or in class if time permits. **Demonstrations can be done up to the last office hours on the due date noted in Canvas. This assignment can not be demonstrated on Zoom on Saturdays due to the need for an oscilloscope.**  **No late demonstrations will be accepted**

1. Properly set oscilloscope display settings on channels 1, 2, and 3.
1. Properly set oscilloscope measurement settings on channels 1, 2, and 3.
1. Properly controlled sinusoidal analog signal on channel 1, verified by oscilloscope.
1. Inverting op-amp: Properly amplified output signal on channel 2, verified by oscilloscope.
1. Non-Inverting op-amp: Properly amplified output signal on channel 3, verified by oscilloscope.

**Successful demonstration of Parts 3, 4, and 5 is sufficient for demonstrating all five parts.**

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

You must submit to Canvas **and** demonstrate your solution in order to receive credit. Late submissions and demonstrations will be graded per the policy in the syllabus.

$^1$ KiCad is only permitted in EGR304
