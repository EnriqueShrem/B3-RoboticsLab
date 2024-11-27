# Task 2: Stack-Up
## Simulation
Simulation video link:
<p align="center">
<a  href="https://youtu.be/qhKUARaJpzY" target="_blank">
    <img src="https://img.youtube/qhKUARaJpzY/0.jpg" alt="Simulation Video" style="width:50%; max-width:600px, height:50%;">
</a>
</p>

## SPEL+ Code
```
Function Stacking 'Main Function, call all the other functions
Motor On
Power High
Tool 1
Speed 30
Accel 30, 30
SpeedS 500
AccelS 5000

'Define Control Box Switches...
Start_Loop:
Wait Sw(0) = On
Xqt Task1
Do While Sw(0) = On
       If Sw(5) = On Then
              Halt Task1
       EndIf
       If Sw(7) = On Then
              Quit Task1
              Reset
              Go P0
              Off 8
              Off 12
              GoTo Start_Loop
       EndIf
       If Sw(6) = On Then
              Resume Task1
       EndIf
       If Sw(4) = On Then
              Quit Task1
              On 12
       EndIf
Loop
Halt Task1
Fend 'Ends The Main Function

Function Task2 'Call Initial Position and Stack Function
Go P0
Call Stack
Go P0
Fend

Function Stack 'Starts the Stacking Function
Integer i
For i = 0 To 9
       Go P2 +Z(6 * i) 'Goes to the Block Picking Positions
       Wait 0.5
       Go P2 +Z(-6 * i)
       On 8
       Wait 0.5
           
       Go P2 +Z(6 * i) 'Goes to the Placing Position to Leave the Block
       Go P5 +Z(24 + (12 * i))
       Go P5 +Z(6 + (12 * i))
       Wait 0.5
       Off 8
       Wait 0.5
       
       Go P5 +Z(24 + (12 * i)) 'Goes to the Coin Picking Position
       Go P1 +Z(6 * i)
       Wait 0.5
       Go P1 +Z(-6 * i)
       On 8
       Wait 0.5
       
       Go P1 +Z(6 * i) 'Goes to the Placing Position to leave the Coin
       Go P5 +Z(30 + (12 * i))
       Go P5 +Z(12 + (12 * i))
       Wait 0.5
       Off 8
       Wait 0.5
       
       Go P5 +Z(30 + (12 * i)) 'Ends Action
       Next i
Fend
```
