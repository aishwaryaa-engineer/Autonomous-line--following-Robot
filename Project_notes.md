The purpose of Phase 1 is to design the thinking process of the robot before writing Verilog code.
"If the robot sees something through its sensors, what should it do?"
**Step 1:** Define the robot's goal
Write in your Project_Notes.md:
Project Goal:
The goal of this project is to design an autonomous robot that can follow a path using sensors and make movement decisions automatically using digital logic.
**Step 2: **Identify inputs and outputs
Think of the robot like a computer.
Inputs (information coming into the robot)
These are the sensors:
Left IR Sensor
Detects whether the line is on the left side.
Center IR Sensor
Detects whether the robot is correctly on the line.
Right IR Sensor
Detects whether the line is on the right side.
Obstacle Sensor
Detects objects in front of the robot.
Write:
Inputs:
L = Left sensor
C = Center sensor
R = Right sensor
O = Obstacle sensor
Outputs (actions the robot performs)
The controller sends signals to motors.
Outputs:
LM = Left motor
RM = Right motor
Step 3: Create decision rules
Now imagine you are the robot.
Case 1: Robot is on the line
Sensors:
L = 0
C = 1
R = 0
Decision:
"Line is in the center, move straight."
Motor output:
LM = 1
RM = 1
Case 2: Line is on the left
L = 1
C = 0
R = 0
Decision:
"Robot moved away from line, turn left."
Output:
LM = 0
RM = 1
Case 3: Line is on the right
L = 0
C = 0
R = 1
Decision:
"Robot moved away from line, turn right."
Output:
LM = 1
RM = 0
Case 4: No line detected
L = 0
C = 0
R = 0
Decision:
"Stop and search."
Output:
LM = 0
RM = 0
Step 4: Make the truth table
Create this in your documentation:
L
C
R
Action
0
1
0
Forward
1
0
0
Turn Left
0
0
1
Turn Right
0
0
0
Stop
Step 5: Convert this idea into Verilog
Only after this Phase 1 is complete, you write Verilog.
Your Verilog module will simply convert:
Sensor inputs → Motor outputs
Like:
IR Sensors
    ↓
Decision Logic (Verilog)
    ↓
Motor Control Signals
