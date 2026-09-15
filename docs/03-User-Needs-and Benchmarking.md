---
title: User Needs and Benchmarking
---

## Voice of the Customer Benchmarking Example

### Search #1

**Keywords:** "kid science kit robotics"

**Search Results Link:** [https://www.amazon.com/s?k=kid+science+kit+robotics&crid=201H95H867ASY&sprefix=kid+science+kit+robotic%2Caps%2C162&ref=nb_sb_noss_2](https://www.amazon.com/s?k=kid+science+kit+robotics&crid=201H95H867ASY&sprefix=kid+science+kit+robotic%2Caps%2C162&ref=nb_sb_noss_2)

### Selected Products

#### 1. [Tinkering Labs Robotics Engineering Kit](https://www.amazon.com/Tinkering-Labs-Electric-Engineering-Experiments/dp/B01M5GJFQ1/) < (link to the product)

![](image1.png)

**(include a picture)**

* Price: $65

* Vendor: Amazon

* Description: The kit includes over 50 high quality components and 10 Challenges that inspire kids to invent their own creations. The pieces are a combination of the everyday and the mysterious, perfect for generating creativity, boosting IQ and instilling STEM knowledge.

##### Positive Comments

| Voice of the Customer                                                                                                                                                                  | Restated Customer Need                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| "My son just turned 6 and he loves this due to the real tools, real wiring and building to truly make something. It is too advanced for his age to do alone but he will grow into it." | 1.  The kit is perceived as more than a toy (explicit)                              |
|                                                                                                                                                                                        | 2.  The kit can be used by younger children without parental supervision (explicit) |
|                                                                                                                                                                                        | 3.  The kit is safe for children of all ages (latent)                               |

##### Negative Comments

| Voice of the Customer                                                                                                                                                                                                                                                                                                                                                                                | Restated Customer Need                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| "I am a STEM teacher and bought a large quantity of these kits and I am disgusted by how easily the motor breaks. 12 years in STEM schools and this product is at the bottom of my list. The ladybug platform, as we call it, needs some reimagining and the materials simply can't handle the wear and tear of a classroom. Sad that I spend my own money on this with so little we got out of it." | 1.  The kit is robust. (explicit)                       |
|                                                                                                                                                                                                                                                                                                                                                                                                      | 2.  The moving parts of the kit are reinforced.(latent) |
|                                                                                                                                                                                                                                                                                                                                                                                                      | 3.  The kit survives multiple uses (explicit)           |

#### 2. Next Product goes here

### Search #2

(you don't have to perform multiple searches, but sometimes different keywords reveal slightly different results)

**Keywords:** <list an alternative search you did, if applicable>

**Search Results Link:** <add your link here>

### Selected Products

#### 3. Next Product goes here

#### 4. Next Product goes here

#### 5. Next Product goes here


## Organized Need Statements

The team collected 75 user needs related to the robotic arm motor control system. The needs were first considered individually and were then organized into groups based on similarities in their purpose and function. A meta-need was created for each group to represent the broader objective shared by the individual needs within that category.

After grouping the needs, the categories were prioritized based on their importance to the safe and successful operation of the robotic arm motor control system. Safety and essential control functions were given the highest priority, followed by feedback, hardware features, reliability, customization, usability, and quality-related needs.

### First Placement

The following image documents the initial placement of the 75 user needs before they were grouped and prioritized.

**[INSERT FIRST PLACEMENT SCREENSHOT HERE]**

### Grouped with Categories

The following image documents the 75 user needs after similar needs were organized into categories and broader meta-needs were identified.

**[INSERT GROUPED NEEDS SCREENSHOT HERE]**

### Ranked

The following image documents the final stage of the organization process, where the groups were prioritized according to their importance to the motor control system.

**[INSERT RANKED NEEDS SCREENSHOT HERE]**


## Compiled List of User Needs

### Rank 1 — Safety Functions

**Meta-Need:** The motor controller protects the user, robotic arm, motors, and electrical components from unsafe or unexpected operating conditions.

1. Errors automatically clear when solved
2. Errors are ranked on their severity
3. Safety boundary constraints
4. Automatic temperature shutoff
5. A fuse should be included to prevent the user from accidentally overvolting the controller
6. The controller should be able to understand the position of the arm immediately after being started up
7. Controller should be able to have an emergency shut off command which cuts power to the motor
8. Controller should be able to stop mid-movement from an external command
9. Controller should be able to change movement directions mid-movement from an external command
10. Powering on the controller shouldn’t make the arm move sporadically


### Rank 2 — On Board Computation

**Meta-Need:** The motor controller performs necessary calculations locally to provide fast, accurate, and efficient robotic arm control while reducing the computational load on the host computer.

1. Forward kinematics solving
2. Inverse kinematics solving
3. Internal PID for ensuring the position of the arm is held
4. Controller should be able to take the fastest “route” to the desired position
5. Controllers should be able to reference one another to achieve a desired position
6. Controller should be able to move smoothly
7. Motor controller should be able to handle as much kinematic computation as possible in order to free up the host computer


### Rank 3 — Computational Feedback

**Meta-Need:** The motor controller provides accurate operating feedback and fault information so that the robotic system can monitor its condition and respond appropriately.

1. Joint position output
2. Joint torque output
3. Motor temperature feedback
4. Motor current draw feedback
5. Error reporting to computer with specific information
6. Significant quantities of poor positional feedback should throw an error
7. Significant quantities of poor temperature feedback should throw an error
8. Significant electrical noise should throw an error before it damages the controller
9. Significant force feedback errors should throw an error
10. Significant force beyond a setable limit should throw an error, but the current position should be held
11. Significant current feedback errors should throw an error
12. Significant current draw beyond the motor’s indicated limit should throw an error
13. Attempts to path to a zone which is sandwiched between two dead zones should throw an error
14. Controller should be able to detect a stall and throw an error


### Rank 4 — On Board Features

**Meta-Need:** The motor controller provides the integrated control and monitoring features necessary for accurate, stable, and reliable robotic arm operation.

1. PWM control
2. USB-c connection
3. Direct motor power from controller board
4. Precise control for repeatability
5. Collision detection
6. Self collision prevention
7. Calibration should be stored locally
8. Controller should be able to “understand” if other magnetic fields are messing with the main one
9. Controller should avoid vibrating once it has reached a specified position
10. Controller shouldn’t “rubber band” around the set point
11. Poor positional feedback should be able to be sorted out
12. Controller should be able to store a custom ID internally
13. Controller should be able to show that it is receiving power
14. Controller should be able to show what its current state is


### Rank 5 — On-Board Components

**Meta-Need:** The motor controller includes the necessary hardware components to support accurate sensing, fault detection, and reliable operation.

1. Angle encoders
2. Error indication lights
3. Watchdog timer


### Rank 6 — Board Specs

**Meta-Need:** The motor controller operates efficiently and reliably under the expected physical, electrical, and environmental conditions of the robotic arm.

1. Ambient temperature range from 0-50 C
2. Controller should be capable of withstanding external electrical noise
3. The controller should consume minimal power
4. Controller should be compact
5. Internal wires which may be prone to getting hot should be kept away from other wires which are sensitive to damage


### Rank 7 — Customizability

**Meta-Need:** The motor controller can be configured and adapted to different robotic arm designs, motion requirements, and operating conditions.

1. PID parameters are configurable
2. Different gear ratios should be able to be taken into account
3. Controller code should be open source
4. Controller should be able to take in “deadzones” to avoid
5. Controller should be able to have its rotation speed controlled
6. Controller should be able to have its rotation acceleration controlled
7. Controller should be able to have its rotation jerk controlled


### Rank 8 — Quality of Life

**Meta-Need:** The motor controller is easy for users to configure, integrate, install, understand, troubleshoot, and maintain.

1. Homing/calibration of the controller should be simple
2. It should be possible for the controller to understand if it needs to be recalibrated
3. Controller should be able to work with both degrees and radians
4. Attempts to give dead zones which have a good zone between them should throw a warning
5. Driver should be able to interface with java
6. Driver should be able to interface with C languages
7. Driver should be able to interface with python
8. Controller should be able to be easily swapped out with another controller of the same model
9. Controller should be easy to install
10. Components of the pcb should be clearly labelled
11. The controller should have a clear diagram in its manual
12. The controllers code should be well documented to ensure an end user understands what each function does
13. Parameters which may be dangerous to edit should be clearly identified as such


### Rank 9 — Quality Control

**Meta-Need:** The motor controller and its critical components provide consistent, tested, and verified performance.

1. Angle encoder should be of good quality
2. The board itself should be thoroughly tested to ensure its capabilities are known


## Grouping and Prioritization Process

The team first compiled the 75 user needs for the motor control system. Each need was then compared with the other needs and placed into a category based on its primary purpose. This resulted in nine categories: Safety Functions, On Board Computation, Computational Feedback, On Board Features, On-Board Components, Board Specs, Customizability, Quality of Life, and Quality Control.

After the individual needs were grouped, a meta-need was created for each category. The meta-needs summarize the overall objective represented by the individual needs within each group.

The groups were then prioritized based on how strongly they affect the safe and successful operation of the robotic arm motor control system. Safety Functions was ranked first because failures involving emergency stopping, uncontrolled motion, temperature, voltage, or operating boundaries could result in damage to the robotic arm or create an unsafe condition. On Board Computation was ranked second because accurate computation and motion control are fundamental to controlling the robotic arm. Computational Feedback was ranked third because the system requires reliable feedback and fault detection to determine its operating condition and respond to problems.

On Board Features and On-Board Components were ranked next because they provide the functionality and hardware necessary to operate and monitor the controller. Board Specs was ranked sixth because environmental, electrical, power, and physical requirements affect the controller's overall reliability. Customizability was ranked seventh because configuration options allow the controller to work with different robotic arm designs and operating requirements. Quality of Life was ranked eighth because installation, documentation, programming support, and ease of use improve the user's ability to work with the controller. Quality Control was ranked ninth because testing and component quality support overall reliability but do not directly control the immediate operation of the robotic arm.

