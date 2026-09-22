---
title: User Needs and Benchmarking
---

## 1. Stakeholder Mapping

**What is our group trying to accomplish?**
We want to make the motor control system for the main arms joints of a robotic arm

### Stakeholders list

| Stakeholder | Role | How to find their voice | Technical / Non-Technical |
|---|---|---|---|
| Operator | Person who controls the robot | Technical forums, operator manuals, expert interviews | Technical |
| Maintainer | The person who repairs the robot | Technical forums, service bulletins, parts supplier reviews | Technical |
| Firmware integration lead | Developer who writes drivers and bus communication routines | Microcontroller subreddits, GitHub issues, MCU application notes | Technical |
| Hardware System | The robot itself | specifications, failure mode analysis, industry standards | Technical |
| Manufacturer | The person or group who actually makes the robot | forums, manufacturing documents, schematics | Technical |

---

## 2. Expert user interview

**Interviewer:** Connor Loos  
**Interviewee:** Jake Okun - Robotics Professor at ASU  

**Q1: What functions and features do you desire in a motor controller?**  
A1: I want precise position and speed control, smooth motion, easy tuning, built-in safety features, and reliable communication with the rest of the system. Real-time feedback and fault diagnostics are also very important.  

**Q2: What problems have you found to frequently occur in common motor controllers?**  
A2: The most common issues are difficult configuration, poor documentation, communication errors, and limited diagnostic information when something goes wrong.  

**Q3: What sort of things do you think a student would want to have in a motor controller in a robotic arm? For example, what things do you think would make it better for students to use the Dobot Robotic arms?**  
A3: Students would benefit from a simple, user-friendly interface, clear error messages, built-in safety limits, easy calibration, and example code for common programming languages. Good documentation and visualization tools for motor status and movement would also make learning much easier.  

---

## 3. Voice of the customer benchmarking

### Search #1

**Keywords:** "Robotic Arm Servomotor"  
**Source:** Feetech Testing & Analysis documentation  
**Source Link:** [Testing of Feetech STS3215 Servomotor](https://robonine.com/testing-of-feetech-sts3215-servomotor-backlash-repeatability-and-torque/)  

#### Selected Product

**Product Under Discussion:** Robotic arm Serial Bus Servo Motor  
* **Price:** $19.90  
* **Source:** ST3215 Serial Bus Servo (12V, 30kg, 360° Magnetic Encoder)  

##### Positive Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| "The repeatability test... showed a tip deviation of ±0.3 mm, corresponding to an angular repeatability of approximately 0.17°... indicating good positional consistency." | 1. The servomotor should provide high positional consistency and accurate angular repeatability for joint positioning. | Implicit |
| "Compared with the datasheet specifications... the measured repeatability represents about 34 % of the specified backlash and roughly two encoder counts, which is reasonable..." | 2. The motor performance should meet or exceed manufacturer datasheet specifications under unloaded operating conditions. | Explicit |
| "...encoder resolution 0.088°, backlash ≤0.5°, torque 30 kg-cm, and nominal voltage 12 V..." | 3. The actuator should integrate high encoder resolution and high holding torque in a compact voltage platform | Explicit |

##### Negative Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| "The spring probe compensates for mechanical slack, but the test could be refined or repeated under load to better reflect in-operation performance." | 1. The motor testing should provide clear performance metrics and repeatability under active payload conditions. | Implicit |
| "The maximum specified backlash of 0.5° corresponds to about 0.87 mm at a 10 cm radius, which means that gear slop is the dominant source of positioning uncertainty." | 2. Design precautions should minimize mechanical gear backlash to prevent cumulative end-effector jitter in multi-DOF arm assemblies. | Implicit |
| "With a 12-bit encoder (0.088° resolution), one encoder step yields approximately 0.153 mm of tip movement at a 10 cm arm radius, making encoder discretization a noticeable factor in high-precision control." | 3. High-precision applications require higher-resolution encoders to reduce tip deviation errors when using longer lever arms. | Explicit |

---

### Search #2

**Keywords:** "Robotic Arm Controller"  
**Source:** STEPFOC Troubleshooting documentation  
**Source Link:** [STEPFOC Docs](https://source-robotics.github.io/STEPFOC-docs/troubleshooting/)  

#### Selected Product

**Product Under Discussion:** Robotic arm stepper motor controller  
* **Price:** €74,00 EUR  
* **Vendor:** Source Robotics Website  

##### Positive Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| "If driver gets over some temperature it will automatically shut down. This is hardware feature of the hardware chip we use and cant be modified in software." | 1. The motor controller should be capable of turning itself off to ensure that it will not destroy itself from overheating. | Implicit |
| "In UART mode you can enter #Error to view what errors are active. In CAN mode you can call Send_Respond_State_of_Errors to get a response of all active errors." | 2. There should be a way for users to quickly identify which errors are occurring, and perhaps such an error should be its own object in the driver which can be referenced by the user's own program | Implicit |
| "Recommended distance between encoder and the magnet is 1mm." | 3. It should be easy for the user to know what the required distance between the motor and the board is. | Implicit |

##### Negative Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| "Error mode is active if any error on the motor driver is active. List of possible errors: Temperature error, Drv error, Encoder error, Vbus error, Velocity error, Current error, Not calibrated, Received ESTOP, Watchdog error" | 1. It should be easy for the user to identify which of the problems the driver is facing via one or more multicolour LEDs | Implicit |
| "To clear errors you can call UART command #Clear or CAN command Send_Clear_Error. Calling these commands will try to clear the error but if the error is still present it will activate again." | 2. It should be easy for the user to clear any error they are facing, and perhaps it would be best if the user could easily see if the error they are facing has been resolved automatically. | Implicit |
| "Magnet too close or touching the sensor of the STEPFOC can brick and even destroy the mcu." | 3. Design precautions should be taken to ensure that the MCU can't be completely destroyed if a magnet is placed too close | Implicit |

---

### Search #3

**Keywords:** "ODrive S1 robotic motor controller troubleshooting"  
**Source:** ODrive S1 Product Page and ODrive Troubleshooting Documentation  
**Source Link:** [ODrive S1 Product Page](https://shop.odriverobotics.com/products/odrive-s1)  

#### Selected Product

**Product Under Discussion:** ODrive S1 Motor Controller  
* **Price:** $149 USD  

##### Positive Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| The ODrive S1 supports two absolute encoders, allowing precise load positioning and immediate operation after startup. | 1. The motor control system should accurately determine the position of the robotic arm joint after startup. | Explicit |
| The controller monitors inverter and motor temperatures and automatically reduces motor current as temperatures approach configured limits. | 2. The motor control system should protect itself and the motor from unsafe operating temperatures. | Explicit |
| The S1 uses locking connectors intended to make wiring harness design and assembly easier | 3. The motor control system should provide reliable electrical connections that remain secure during the operation | Explicit |

##### Negative Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| ODrive documentation states that encoder noise can result from issues such as long encoder wires and ribbon cables and recommends shielding or twisted-pair wiring. | 1. The motor control system should maintain reliable position feedback in the presence of electrical noise. | Latent |
| Troubleshooting documentation states that a motor may vibrate while stationary or continuously make noise when controller gains are incorrectly configured. | 2. The motor control system should maintain stable joint positioning without unwanted vibration or movement. | Latent |
| ODrive states that inaccurate encoder measurements can cause poor control, spinout errors, erratic behavior, and even damage. | 3. The motor control system should respond safely to inaccurate or unreliable position feedback. | Latent |

---

### Search #4

**Keywords:** "Spark max motor controller troubleshooting"  
**Source:** SPARK MAX Motor Controller product page  
**Source Link:** [REV Robotics SPARK MAX](https://www.revrobotics.com/rev-11-2158/)  

#### Selected Product

**Product Under Discussion:** SPARK MAX Motor Controller  
* **Vendor:** REV Robotics  
* **Price:** $100  

##### Positive Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| If you use the Spark Max PID implementation the PID Controller will run on the motor controller and will presumably be faster, | 1. Allowing the PID to run on the motor controller frees up more processing for the main controller. | Implicit |
| HUGE PROPS to REV for giving every device a USB-C port. You can actually update firmware and set CAN IDs without having to apply power to the device. | 2. Easy access to be able to diagnose issues and update firmware through USB-C | Explicit |
| open the REV software and splice the sparkmax into the CAN bus to troubleshoot breaks in the CAN Bus | 3. Ability to access entire CANbus from the USB-C allows easy troubleshooting for all motor controllers even in hard to reach places | Explicit |

##### Negative Comments

| Voice of the Customer | Restated Customer Need | Type |
|---|---|---|
| "A lot of the FRC CAN motor controllers have proprietary packets so you can't really use them outside of FRC/vendor approved ecosystems." | 1. This motor controller CAN uses proprietary code not allowing it outside of First robotics competitions | Explicit |
| The REV Hardware Client reports an Over Current Fault on the affected controller. Even with wheels free to spin on chocks, the same controller trips again within seconds of re-enable. | 2. Over current fault is not automatically cleared and will continue to appear until it is cleared | Explicit |
| there is a failure mode within a NEO where if it gets too hot, ie stalled for a long period of time, a short can occur internally. Once this short occurs, it will fry the SparkMAX it's connected to as well. | 3. The motor controller can suffer from a short caused by the motor being stalled, adding a timer or a stall sensor could prevent the flow of power to the controller and motor | Explicit |

---

## 4. Grouped and Prioritized List of 75 Unique User Needs

### On-board Computation
*Needs Full Kinematic and PID calculations to be easily referenced and shared the fastest way possible between all other controllers.*

1. Forward kinematics solving
2. Inverse kinematics solving
3. Internal PID for ensuring the position of the arm is held
4. Controller should be able to take the fastest "route" to the desired position
5. Controllers should be able to reference one another to achieve a desired position
6. Controller should be able to move smoothly
7. Motor controller should be able to handle as much kinematic computation as possible in order to free up the host computer

### On-board Features
*The controller should be able to act as independently as possible from the main system to ensure that minimal computational power is taken from the main controlling system.*

1. PWM control
2. USB-C connection
3. Direct motor power from controller board
4. Precise control for repeatability
5. Collision detection
6. Self collision prevention
7. Calibration should be stored locally
8. Controller should be able to "understand" if other magnetic fields are messing with the main one
9. Controller should avoid vibrating once it has reached a specified position
10. Controller shouldn't "rubber band" around the set point
11. Poor positional feedback should be able to be sorted out
12. Controller should be able to store a custom ID internally
13. Controller should be able to show that it is receiving power
14. Controller should be able to show what its current state is

### On-board Components
*The controller should include a controller, an angle encoder, error indication LEDs, and a dedicated watchdog timer to ensure proper functioning.*

1. Angle encoders
2. Error indication lights
3. Watchdog timer

### Computational Feedback
*The controller should be able to get data from its sensors and communicate that feedback to the user.*

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
12. Significant current draw beyond the motor's indicated limit should throw an error
13. Attempts to path to a zone which is sandwiched between two dead zones should throw an error
14. Controller should be able to detect a stall and throw an error

### Safety Functions
*The controller should have safeguards to prevent overheating, shorts, and dangerous movements of the arm.*

1. Errors automatically clear when solved
2. Errors are ranked on their severity
3. Safety boundary constraints
4. Automatic temperature shutoff
5. A fuse should be included to prevent the user from accidentally overvolting the controller
6. The controller should be able to understand the position of the arm immediately after being started up
7. Controller should be able to have an emergency shut off command which cuts power to the motor
8. Controller should be able to stop mid-movement from an external command
9. Controller should be able to change movement directions mid-movement from an external command
10. Powering on the controller shouldn't make the arm move sporadically

### Board Specs
*The controller should be small but hardy in order to improve the range of use cases.*

1. Ambient temperature range from 0-50 C
2. Controller should be capable of withstanding external electrical noise
3. The controller should consume minimal power
4. Controller should be compact
5. Internal wires which may be prone to getting hot should be kept away from other wires which are sensitive to damage

### Quality Control
*The controller's PCB should be designed with reliability in mind to ensure that the end product will last.*

1. Angle encoder should be of good quality
2. The board itself should be thoroughly tested to ensure its capabilities are known

### Customizability
*Each and every parameter should be able to be changed by the end user to improve the range of applications that this controller can be used for.*

1. PID parameters are configurable
2. Different gear ratios should be able to be taken into account
3. Controller code should be open source
4. Controller should be able to take in "deadzones" to avoid
5. Controller should be able to have its rotation speed controlled
6. Controller should be able to have its rotation acceleration controlled
7. Controller should be able to have its rotation jerk controlled

### Quality of Life
*The controller should be easy to install and program from a variety of methods and languages.*

1. Homing/calibration of the controller should be simple
2. It should be possible for the controller to understand if it needs to be recalibrated
3. Controller should be able to work with both degrees and radians
4. Attempts to give dead zones which have a good zone between them should throw a warning
5. Driver should be able to interface with Java
6. Driver should be able to interface with C languages
7. Driver should be able to interface with Python
8. Controller should be able to be easily swapped out with another controller of the same model
9. Controller should be easy to install
10. Components of the PCB should be clearly labelled
11. The controller should have a clear diagram in its manual
12. The controllers code should be well documented to ensure an end user understands what each function does
13. Parameters which may be dangerous to edit should be clearly identified as such
