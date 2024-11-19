# B3-RoboticsLab
In this repository we cover the work done by the group B3 for the Final Tasks for the Introduction to Robotics Tutorial course

Members: Jose Flores, Danna Lopez, Facundo Rolon, Enrique Shrem

## Course Overview
In the Introduction to Robotics Tutorial course, we work with industrial robots (EPSON and ABB) to make practices and achieve specific tasks, we cover topics such as:
- Instalation of the I/O connections
- Programing of the robot
- Simulation of the tasks
- Robot usage to perform the tasks

Enviroment materials:
Tokens: two types, coin and block
Feeder: a platform with vertically aligned tokens (stacked by types)
Tray: a platform with multiple sockets for the tokens (3 for each kind)
Fixture: a platform used for the alignment of the tokens with the tool
Others materials can be missed, since they don't offer relevance during the tasks mentioned below.

## Task 1: Pick and Place
Move tokens from feeder to the fixture, align them and then precisely insert them into the tray.

Install tools and components (feeder, fixture, tray) and explore their coordinates with tools (extra parts may be required to proceed the calibration).

Define the World (local0), Local, tool(tool0), tool coordinates. (Based on the robots and works cell).
Measure the tool dimension and the center offset between tool0(J6, robot) and tools.(Tool1: gripper, Tool2: vacuum nozzle).
Decide the space between "objects"(tokens and blocks) at pick-up and approach gap when place.
Exercise: Transfer tokens from the feeder to the fixture first, then move them to the tray.

## Task 2: Stack-Up
Stack up tokens and blocks alternatively. (5 token and 5 blocks)
