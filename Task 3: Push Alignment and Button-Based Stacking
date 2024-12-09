# Simulation


# SPEL+ Code
```
Global Integer counter_times
Function Main

Motor On
Power High
Speed 50
Accel 50, 50
SpeedS 500
AccelS 5000
Tool 0

Off 11

Go P0 CP
Speed 30
Accel 30, 30
SpeedS 500
AccelS 5000


Call PeopleAllign
Call Counter


Fend

Function Botones

Start_Loop:

Wait Sw(0) = On
Xqt Main
Do While Sw(0) = On

    If Sw(7) = On Then
   Quit Main
   Off 12
   Reset
   Off 11
   Go P0
   GoTo Start_Loop
    EndIf
   
    If Sw(4) = On Then
   Quit Main
   On 12
EndIf

Loop
Halt Main
Fend
Function Counter

Start_Loop:
Integer i
For i = 0 To 12
CTReset i
Next i
Do
counter_times = Ctr(5)
Print counter_times

        If counter_times = 1 And Sw(6) = On Then
            Call People1
CTReset 1
GoTo Start_Loop
EndIf
        If counter_times = 2 And Sw(6) = On Then
            Call People2
CTReset 2
GoTo Start_Loop
EndIf If counter_times = 3 And Sw(6) = On Then
            Call People3
CTReset 3
GoTo Start_Loop
EndIf If counter_times = 4 And Sw(6) = On Then
            Call People4
CTReset 4
GoTo Start_Loop
EndIf If counter_times = 5 And Sw(6) = On Then
            Call People5
CTReset 5
GoTo Start_Loop
EndIf
If counter_times = 6 And Sw(6) = On Then
Call People6
CTReset 6
GoTo Start_Loop
EndIf


If counter_times > 6 Then
For i = 0 To 12
CTReset i
Next i
EndIf

    Loop
   
End_Loop:


Fend


Function PeopleAllign

'Feeder 1
Integer i
For i = 0 To 2
Move P1 +X(-52)
Move P1 +X(-14 * (2 - i))
On 11
Wait 0.5
Move P1 +X(-14 * (2 - i)) +Z(0.5)
Wait 0.5
Move P1 +X(-52) +Z(0.5)
Move P1 +X(-52) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Next i

'Feeder 2
'Integer i
For i = 0 To 2
Go P2 +X(-52)
Move P2 +X(-14 * (2 - i))
On 11
Wait 0.5
Move P2 +X(-14 * (2 - i)) +Z(0.5)
Wait 0.5
Move P2 +X(-52) +Z(0.5)
Move P2 +X(-52) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Next i

Fend

Function People1

'Stack 1
Go P3 +X(-20) +Y(-45) +Z(30)
Move P3 +X(-20) +Z(30)
Move P3 +X(-20)
Move P3
On 11
Wait 0.5
Go P3 +Y(-15) +Z(30)
Go P4 +Z(10)
Move P4
Off 11
Wait 0.5
Move P4 +X(-20)
Move P4 +X(-20) +Y(-30)

'Resting Place
Go P0
Wait 0.5

'Reverse Function
Move P4 +X(-20) +Y(-30)
Go P4 +X(-20)
Move P4 +X(1)
On 11
Wait 0.5
Move P4 +X(1) +Z(10)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20) +Z(0.1)
Go P3 +X(-20) +Y(-45) +Z(30)

Fend

Function People2

'Stack 2
Integer i
For i = 0 To 1
Go P3 +X(-20) +Y(-45) +Z(30)
Go P3 +Y(44.5 * i) +X(-20)
Move P3 +Y(44.5 * i)
Wait 0.5
Move P3 +Y(44.5 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.5 * i)) +Z(30)
Go P4 +Y(65 * i) +Z(10)
Move P4 +Y(65 * i)
Wait 0.5
Off 11
Wait 0.5
Move P4 +X(-20) +Y(65 * i)
Next i

'Resting Place
Move P0
Wait 3

'Reverse Function
For i = 0 To 1
Go P4 +X(-20) +Y(65 * (1 - i))
Move P4 +X(1) +Y(65 * (1 - i))
Move P4 +X(1) +Y(65 * (1 - i)) +Z(0.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(65 * (1 - i)) +Z(10)
Move P4 +X(-20) +Y(65 * (1 - i)) +Z(10)
Go P3 +X(60) +Y(-45) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Move P3 +X(60) +Y(-45) +Z(30)
Next i

Fend

Function People3

'Stack 3
Integer i
For i = 0 To 2
Go P3 +X(-20) +Y(-45) +Z(30)
Go P3 +Y(44.5 * i) +X(-20)
Move P3 +Y(44.5 * i)
Wait 0.5
Move P3 +Y(44.5 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.5 * i)) +Z(30)

If i < 2 Then
Go P4 +Y(65 * i) +Z(10)
Move P4 +Y(65 * i)
Wait 0.5
Off 11
Wait 0.5
Move P4 +X(-20) +Y(65 * i)
Else
Go P4 +X(-20) +Y(32.5) +Z(38.5)
Move P4 +Y(32.5) +Z(38.5)
Wait 0.5
Off 11
Wait 0.5
Move P4 +Y(32.5) +Z(38)
Move P4 +X(-20) +Y(32.5) +Z(38)
EndIf
Next i

'Resting Place
Go P0
Wait 3

'Reverse Function
For i = 0 To 2
If i = 0 Then
Go P4 +X(-50) +Y(32.5) +Z(38)
Move P4 +X(1) +Y(32.5) +Z(38)
Wait 0.5
Move P4 +X(1) +Y(32.5) +Z(38.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(-20) +Y(32.5) +Z(38.5)

Else
Go P4 +X(-20) +Y(65 * (2 - i))
Move P4 +X(1) +Y(65 * (2 - i))
Move P4 +X(1) +Y(65 * (2 - i)) +Z(0.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(65 * (2 - i)) +Z(10)
Move P4 +X(-20) +Y(65 * (2 - i)) +Z(10)
Move P4 +X(-20) +Y(-20) +Z(10)
EndIf

Go P3 +X(60) +Y(-45) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Move P3 +X(60) +Y(-45) +Z(30)

Next i

Fend

Function People4

'Stack 4
Integer i
For i = 0 To 3
Go P3 +X(-20) +Y(-45) +Z(30)
Go P3 +Y(44.5 * i) +X(-20)
Move P3 +Y(44.5 * i)
Wait 0.5
Move P3 +Y(44.5 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.5 * i)) +Z(30)

If i < 3 Then
Go P4 +Y(65 * i) +Z(10)
Move P4 +Y(65 * i)
Wait 0.5
Off 11
Wait 0.5
Move P4 +X(-20) +Y(65 * i)
Else
Go P4 +X(-20) +Y(32.5) +Z(38.5)
Move P4 +Y(32.5) +Z(38.5)
Wait 0.5
Off 11
Wait 0.5
Move P4 +Y(32.5) +Z(38)
Move P4 +X(-20) +Y(32.5) +Z(38)
EndIf
Next i

'Resting Place
Go P0
Wait 3

'Reverse Function
For i = 0 To 3
If i = 0 Then
Go P4 +X(-50) +Y(32.5) +Z(38)
Move P4 +X(1) +Y(32.5) +Z(38)
Wait 0.5
Move P4 +X(1) +Y(32.5) +Z(38.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(-20) +Y(32.5) +Z(38.5)
Else
Go P4 +X(-20) +Y(65 * (3 - i))
Move P4 +X(1) +Y(65 * (3 - i))
Move P4 +X(1) +Y(65 * (3 - i)) +Z(0.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(65 * (3 - i)) +Z(10)
Move P4 +X(-20) +Y(65 * (3 - i)) +Z(10)
Move P4 +X(-20) +Y(-20) +Z(10)
EndIf

Go P3 +X(60) +Y(-45) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Move P3 +X(60) +Y(-45) +Z(30)

Next i

Fend

Function People5

'Stack 5
Integer i
For i = 0 To 4
Go P3 +X(-20) +Y(-45) +Z(30)

If i < 4 Then
Go P3 +Y(44.5 * i) +X(-20)
Move P3 +Y(44.5 * i)
Wait 0.5
Move P3 +Y(44.5 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.5 * i)) +Z(30)

ElseIf i = 4 Then
Go P3 +Y(44.41 * i) +X(-20)
Move P3 +Y(44.41 * i)
Wait 0.5
Move P3 +Y(44.41 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.41 * i)) +Z(30)
EndIf

If i < 3 Then
Go P4 +Y(65 * i) +Z(10)
Move P4 +Y(65 * i)
Wait 0.5
Off 11
Wait 0.5
Move P4 +X(-20) +Y(65 * i)

Else
Go P4 +X(-20) +Y(32.5 + (65 * (i - 3))) +Z(38.5)
Wait 0.5
Move P4 +Y(32.5 + (65 * (i - 3))) +Z(38.5)
Wait 0.5
Move P4 +Y(32.5 + (65 * (i - 3))) +Z(38)
Wait 0.5
Off 11
Wait 0.5
Move P4 +Y(32.5 + (65 * (i - 3))) +Z(37)
Wait 0.5
Move P4 +X(-20) +Y(32.5 + (65 * (i - 3))) +Z(37)
EndIf

Next i

'Resting Place
Go P0
Wait 3

'Reverse Function

For i = 0 To 4
Go P3 +X(60) +Y(-45) +Z(30)

If i < 2 Then
Go P4 +X(-20) +Y(32.5 + (65 * (1 - i))) +Z(38)
Wait 0.5
Move P4 +X(1) +Y(32.5 + (65 * (1 - i))) +Z(38)
Wait 0.5
Move P4 +X(1) +Y(32.5 + (65 * (1 - i))) +Z(38.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(32.5 + (65 * (1 - i))) +Z(39)
Wait 0.5
Move P4 +X(-20) +Y(32.5 + (65 * (1 - i))) +Z(39)
Move P4 +X(-20) +Y(32.5) +Z(39)

Else
Go P4 +X(-20) +Y(65 * (4 - i))
Move P4 +X(1) +Y(65 * (4 - i))
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(65 * (4 - i)) +Z(10)
Move P4 +X(-20) +Y(65 * (4 - i)) +Z(10)
Move P4 +X(-20) +Y(-20) +Z(10)

EndIf

Go P3 +X(60) +Y(-45) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Move P3 +X(60) +Y(-45) +Z(30)

Next i

Fend

Function People6

'Stack 6
Integer i
For i = 0 To 5
Go P3 +X(-20) +Y(-45) +Z(30)
If i < 4 Then
Go P3 +Y(44.5 * i) +X(-20)
Move P3 +Y(44.5 * i)
Wait 0.5
Move P3 +Y(44.5 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.5 * i)) +Z(30)

ElseIf i = 4 Then
Go P3 +Y(44.41 * i) +X(-20)
Move P3 +Y(44.41 * i)
Wait 0.5
Move P3 +Y(44.41 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.41 * i)) +Z(30)

Else
Go P3 +Y(44.284 * i) +X(-20)
Move P3 +Y(44.284 * i)
Wait 0.5
Move P3 +Y(44.284 * i - 3)
Wait 0.5
On 11
Wait 0.5
Go P3 +Y(-15 + (44.284 * i)) +Z(30)
EndIf

If i < 3 Then
Go P4 +Y(65 * i) +Z(10)
Move P4 +Y(65 * i)
Wait 0.5
Off 11
Wait 0.5
Move P4 +X(-20) +Y(65 * i)

ElseIf i = 5 Then
Go P4 +X(-20) +Y(65) +Z(77)
Move P4 +X(-20) +Y(65) +Z(77)
Wait 0.5
Move P4 +Y(65) +Z(77)
Wait 0.5
Move P4 +Y(65) +Z(75)
Off 11
Wait 0.5
Move P4 +Y(65) +Z(74.5)
Wait 0.5
Move P4 +X(-20) +Y(65) +Z(74.5)
Move P4 +X(-20) +Y(65) +Z(74.5)

Else
Go P4 +X(-20) +Y(32.5 + (65 * (i - 3))) +Z(38.5)
Wait 0.5
Move P4 +Y(32.5 + (65 * (i - 3))) +Z(38.5)
Wait 0.5
Move P4 +Y(32.5 + (65 * (i - 3))) +Z(37.5)
Wait 0.5
Off 11
Wait 0.5
Move P4 +Y(32.5 + (65 * (i - 3))) +Z(37)
Wait 0.5
Move P4 +X(-20) +Y(32.5 + (65 * (i - 3))) +Z(37)
EndIf
Next i

'Resting Place
Go P0
Wait 3

'Reverse Function

For i = 0 To 5
Go P3 +X(60) +Y(-45) +Z(30)

If i = 0 Then
Go P4 +X(-20) +Y(65) +Z(75)
Move P4 +X(-20) +Y(65) +Z(75)
Wait 0.5
Move P4 +X(1) +Y(65) +Z(75)
Wait 0.5
Move P4 +X(1) +Y(65) +Z(77)
On 11
Wait 0.5
Move P4 +X(1) +Y(65) +Z(78)
Move P4 +X(-20) +Y(65) +Z(78)

    ElseIf i > 0 And i < 3 Then
Go P4 +X(-20) +Y(32.5 + (65 * (2 - i))) +Z(38)
Wait 0.5
Move P4 +X(1) +Y(32.5 + (65 * (2 - i))) +Z(38)
Wait 0.5
Move P4 +X(1) +Y(32.5 + (65 * (2 - i))) +Z(38.5)
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(32.5 + (65 * (2 - i))) +Z(39)
Move P4 +X(-20) +Y(32.5 + (65 * (2 - i))) +Z(39)
Wait 0.5
Move P4 +X(-20) +Y(-20) +Z(39)

Else
Go P4 +X(-20) +Y(65 * (5 - i))
Move P4 +X(1) +Y(65 * (5 - i))
Wait 0.5
On 11
Wait 0.5
Move P4 +X(1) +Y(65 * (5 - i)) +Z(10)
Move P4 +X(-20) +Y(65 * (5 - i)) +Z(10)
Move P4 +X(-20) +Y(-20) +Z(10)

EndIf

Go P3 +X(60) +Y(-45) +Z(30)
Go P3 +Y(-45) +Z(30)
Move P3 +Y(-45) +Z(0.1)
Move P3 +Z(0.1)
Off 11
Wait 0.5
Move P3 +X(-20)
Go P3 +X(-20) +Y(-45) +Z(30)
Move P3 +X(60) +Y(-45) +Z(30)

Next i

Fend
