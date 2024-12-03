# Task 1: Pick and Place
## Simulation
Task 1 simulation video link:
<p align="center">
<a  href="https://youtu.be/znjjijPPfI8" target="_blank">
    <img src="https://img.youtube.com/vi/znjjijPPfI8/0.jpg" alt="Simulation Video" style="width:50%; max-width:600px, height:30%;">
</a>
</p>

## SPEL+ Code
```
'Define Difference Between Tray Positions...
Global Long Dx
Global Long Dy

'Define Block Off-Set Alignment Positions...
Global Real Bx
Global Real By

'Define Coin Off-Set Alignment Positions...
Global Real Mx
Global Real My

Function PickPlace
Motor On
Power High
Tool 1
Speed 30
Accel 30, 30
SpeedS 500
AccelS 5000


Dx = -24.06
Dy = 18.22
Bx = -15
By = 0
Mx = -15
My = 0

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


Function Task1 'Executes the Pick and Place tasks
Go SafetyPosition
Call FORCOINS
Call FORBLOCKS
Go SafetyPosition
Fend


Function FORCOINS 'For Coin Tokens
Integer i
For i = 0 To 2
       Go P1 +Z(50) /0'Goes to the Picking Positions
       Move P1 +Z(-6 * i) /0
       Wait 0.5
       On 8
       Wait 0.5
       Move P1 +Z(2 + (-6 * i)) /0

       Go P1 +X(-15) +Y(15) +Z(50) /0 'Goes to the Fixture Positions
       Go P3 +X(Mx) +Y(My) +Z(30) /1
       Move P3 +X(Mx) +Y(My) /1
       Off 8
       
       Move P3 +X(-Mx) +Y(-My) /1 'Aligns the Tokens
       Move P3 +X(-Mx) +Y(-My) +Z(10) /1
       Move P3 +Z(10) /1
       Move P3 /1
       Wait 0.5
       On 8

       Move P3 +Z(30) /1 'Goes to Tray Positions
       Go P5 +X(Dx * i) +Y(Dy * i) +Z(30) /2
       Move P5 +X(Dx * i) +Y(Dy * i) /2
       Wait 0.5
       Off 8

       Move P5 +X(Dx * i) +Y(Dy * i) +Z(30) /2 'Ends Action      
       Next i
Fend


Function FORBLOCKS 'For Block Tokens
Integer i
For i = 0 To 2
       Go P2 +Z(50) /0 'Goes to Picking Positions
       Move P2 +Z(-6 * i) /0
       Wait 0.5 
       On 8
       Move P2 +Z(2 + (-6 * i)) /0

       Go P2 +X(-15) +Y(15) +Z(50) /0 'Goes to Fixture Positions
       Go P4 +X(Bx) +Y(By) +Z(30) /1
       Move P4 +X(Bx) +Y(By) /1
       Wait 0.5
       Off 8
       
       Move P4 +X(-Bx) +Y(-By) /1 'Aligns Tokens
       Move P4 +X(-Bx) +Y(-By) +Z(10) /1
       Move P4 +Z(10) /1
       Move P4 /1
       Wait 0.5
       On 8

       Move P4 +Z(30) /1 'Goes to Tray Positions
       Go P6 +X(Dx * i) +Y(Dy * i) +Z(30) /2
       Move P6 +X(Dx * i) +Y(Dy * i) /2
       Wait 0.5
       Off 8
       
       Move P6 +X(Dx * i) +Y(Dy * i) +Z(30) /2 'Ends Action
       Next i
Fend
```
