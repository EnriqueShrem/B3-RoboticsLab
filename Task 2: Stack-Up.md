# Task 2: Stack-Up
## Simulation

## SPEL+ Code

Function Stacking

Motor On
Power High
Tool 1
Speed 30
Accel 30, 30
SpeedS 500
AccelS 5000

'Define Switch...
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

Fend

Function Task2
Go P0
Call Stack
Go P0

Fend

Function Stack

Integer i
For i = 0 To 9

'Pick Block
Go P2 +Z(6 * i)
Wait 0.5
Go P2 +Z(-6 * i)
On 8
Wait 0.5                               
Go P2 +Z(6 * i)

'Place Block
Go P5 +Z(24 + (12 * i))
Go P5 +Z(6 + (12 * i))
Wait 0.5
Off 8
Wait 0.5
Go P5 +Z(24 + (12 * i))

'Pick Coin
Go P1 +Z(6 * i)
Wait 0.5
Go P1 +Z(-6 * i)
On 8
Wait 0.5
Go P1 +Z(6 * i)

'Place Coin
Go P5 +Z(30 + (12 * i))
Go P5 +Z(12 + (12 * i))
Wait 0.5
Off 8
Wait 0.5
Go P5 +Z(30 + (12 * i))

Next i
 
Fend
