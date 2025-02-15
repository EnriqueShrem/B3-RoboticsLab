# Robotics Lab Final Tasks - Group B3
In this repository we cover the work done for the Final Tasks in the Introduction to Robotics Tutorial course as the group B3. See also: [Introduction to Robotics course](https://github.com/EnriqueShrem/B3-Robotics).

Members: Jose Flores, Danna Lopez, Facundo Rolon, Enrique Shrem

## Course Overview
In the Introduction to Robotics Tutorial course, we work with industrial robots (EPSON and ABB) to make practices and achieve specific tasks, we cover topics such as:
- Instalation of the I/O connections
- Integration of control box
- Programming with the respective robot software
- Simulation of the tasks
- Robot manipulation and usage to perform the tasks
- Time optimization
- Integration of custom 3D printed features

Enviroment materials:
Task 1 & 2:
- Tokens: two types, coin and block
- Feeder: a platform with vertically aligned tokens (stacked by types)
- Tray: a platform with multiple sockets for the tokens (3 for each type)
- Fixture: a platform used for the alignment of the tokens with the tool
  
Task 3:
- Tokens: 3D printed human figures
- Feeders: custom platforms for holding the human like tokens

This and other materials have been used for the performing the tasks.

## Final Tasks
### [Task 1: Pick and Place](Task%201%3A%20Pick%20and%20Place.md)
End effector: Vacuum Nozzle

Moves tokens from feeder to the fixture, aligns them and then precisely inserts them into the tray, repites the process reversely.
<p align="center">
<a  href="https://youtu.be/L9NZz7nbw-M" target="_blank">
    <img src="https://img.youtube.com/vi/L9NZz7nbw-M/0.jpg" alt="Simulation Video" style="width:40%; max-width:600px, height:30%;">
</a>
</p>

### [Task 2: Stack-Up](Task%202%3A%20Stack-Up.md)
End effector: Vacuum Nozzle

Stacks up tokens and blocks alternatively, collecting them from the feeder.
<p align="center">
<a  href="https://youtu.be/7zq75P6Hq2w" target="_blank">
    <img src="https://img.youtube.com/vi/7zq75P6Hq2w/0.jpg" alt="Simulation Video" style="width:40%; max-width:600px, height:30%;">
</a>
</p>

### [Task 3: Push Alignment and Button-Based Stacking](Task%203%3A%20Push%20Alignment%20and%20Button-Based%20Stacking.md) (Open-Ended Integration Task)

End effector: Pneumatic Gripper (Custom Gripper Fixtures)

Moves tokens from feeders to a determined position and aligns them by pushing against the next, then enables a counter button to define the number of tokens to be stacked and a play button to start the stacking, once tokens stacked returns to alignment position and renables the counter button. 


## Features
### [Control Box |🔴🟠🟢🔵⚪🚨| & I/O Connections 🔌📍](IO%20Connections.md)
### [HMI Design](HMI%20Design.md)
### [CAD Designs](Assets/CAD%20Files)


