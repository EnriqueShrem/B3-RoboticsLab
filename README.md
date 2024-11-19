# B3-RoboticsLab
##Overview
The Robotics Lab is a class in which we work with industrial robots (EPSON and ABB) to make practices and achieve specific tasks, we cover topics such as:
- Instalation of electrical and pneumatic components
- Programing of the robot
- Simulation of the task
- Robot usage to perform the tasks

Enviroment materials:
Tokens: coin and block
Feeder: a platform with vertically aligned tokens
Tray: a platform used for the alignment of the tokens with the tool
Fixture: a platform with multiple sockets for the tokens (3 for each kind)


##Task 1: Pick and Place
Move tokens from feeder (a platform with vertically aligned tokens), to the tray (a platform used for the alignment of the tokens with the tool), and then precisely insert them into the fixture(a platform with multiple sockets for the tokens)

Install tools and components (feeder, fixture, tray) and explore their coordinates with tools (extra parts may be required to proceed the calibration)

Define the World (local0), Local, tool(tool0), tool coordinates. (Based on the robots and works cell)
Measure the tool dimension and the center offset between tool0(J6, robot) and tools.(Tool1: gripper, Tool2: vacuum nozzle)
Decide the space between "objects"(tokens and blocks) at pick-up and approach gap when place
Exercise: Transfer tokens from the feeder to the fixture first, then move them to the tray.

##Task 2: Building the simulation environment:
There are two ways to build the simulation environment:

Use the measured dimension of the robot envelope and the work cell in Basic: Task 1.
Start a new layout arrangement with the CAD files Exercise: Insert CAD models in a robot envelope.
