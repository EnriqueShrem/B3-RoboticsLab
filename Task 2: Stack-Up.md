# Task 2: Stack-Up
## Simulation
Simulation video link:
<p align="center">
<a  href="https://youtu.be/qhKUARaJpzY" target="_blank">
    <img src="https://img.youtube.com/vi/qhKUARaJpzY/0.jpg" alt="Simulation Video" style="width:50%; max-width:600px, height:30%;">
</a>
</p>

## SPEL+ Code
```
Global Real n 
Function Main 'Main Function, call all the other functions
Motor On
Power High
Tool 1
Speed 50
Accel 50, 50
SpeedS 500
AccelS 5000
n = 7


'Define Control Box Switches...
Start_Loop:
Wait Sw(0) = On
Xqt Task2
Do While Sw(0) = On
       If Sw(5) = On Then
              Halt Task2
       EndIf
       If Sw(7) = On Then
              Quit Task2
              Reset
              Go P0
              Off 8
              Off 12
              GoTo Start_Loop
       EndIf
       If Sw(6) = On Then
              Resume Task2
       EndIf
       If Sw(4) = On Then
              Quit Task2
              On 12
       EndIf
Loop
Halt Task2
Fend 'Ends The Main Function

Function Task2 'Call Initial Position and Stack Function
Go P0
Call Stack
Go P0
Fend

Function Stack 'Starts the Stacking Function

Integer i
For i = 0 To 9
       Go P2 +Z((6 * n) + (6 * (2 + i))) CP 'Goes to the Block Picking Positions
       Move P2 +Z((6 * n) - (6.2 * i))
       On 8
       Wait 0.1
           
       Move P2 +Z((6 * n) - (6.2 * i) + 2)
       Wait 0.1
       Move P2 -X(15) +Y(15) +Z((6 * n) + (6 * (2 + i)))  'Goes to the Placing Position to Leave the Block
       ' Go P1 -X(15) +Y(15) +Z((6 * n) + (6 * (2 + i))) CP
       Go P8 +Z(24 + (12 * i)) CP
       Move P8 +Z(6 + (12 * i))
       Wait 0.1
       Off 8
       Wait 0.1
       
       Move P8 +Z(24 + (12 * i)) 'Goes to the Coin Picking Position
       Go P1 +Z((6 * n) + (6 * (2 + i)))
       Move P1 +Z((6 * n) - (6.2 * i))
       On 8
       Wait 0.1
       
       Move P1 +Z((6 * n) - (6.2 * i) + 2)
       Wait 0.1
       Move P1 -X(20) +Z((6 * n) + (6 * (2 + i)))  'Goes to the Placing Position to leave the Coin
       Go P8 +Z(30 + (12 * i)) CP
       Move P8 +Z(12 + (12 * i))
       Wait 0.1
       Off 8
       Wait 0.1
       
       Move P8 +Z(30 + (12 * i)) 'Ends Action
       Next i
Fend
```
