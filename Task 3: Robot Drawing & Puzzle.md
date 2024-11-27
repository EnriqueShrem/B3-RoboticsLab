# Simulation


# SPEL+ Code
```
Function Main

Motor On
Power High
Tool 1
Speed 30
Accel 30, 30
SpeedS 500
AccelS 5000
Global Real s
s = 10

'Agregar Botones para los task

Fend


Function TaskPeople

Go P0
Call PeopleStack
Call PeopleReverse
Go P0

Fend


Function PeopleStack

'Stack 1 and 2...
For i=0 to 1

  Go P3 +X(-25)
  Go P3 +X(15 * i)
  Wait 0.5
  On 11
  Go P3 +X(-25)
  
  Go P4 +X(-50) +Y(53 * i)
  Go P4 +Y(53 * i)
  Wait 0.5
  Off 11
  Go P4 +X(-50) +Y(53 * i)

Next i

'Stack 3...
Go P3 +X(-25)
Go P3 +X(30)
Wait 0.5
On 11
Go P3 +X(-25)

Go P4 +X(-50) +Y(16.5) +Z(35) 
Go P4 +Y(16.5) +Z(35)
Wait 0.5
Off 11
Go P4 +X(-50) +Y(16.5) +Z(35)

Fend


Function PeopleReverse

'Reverse Stack 3...
Go P4 +X(-50) +Y(16.5) +Z(35) 
Go P4 +Y(16.5) +Z(35)
Wait 0.5
On 11
Go P4 +X(-50) +Y(16.5) +Z(35)

Go P3 +X(-25)
Go P3 +X(30)
Wait 0.5
Off 11
Go P3 +X(-25)

'Reverse Stack 1 and 2...
For i=0 to 1
  
  Go P4 +X(-50) +Y(53 * (1 - i))
  Go P4 +Y(53 * (1 - i))
  Wait 0.5
  On 11
  Go P4 +X(-50) +Y(53 * (1 - i))
  
  Go P3 +X(-25)
  Go P3 +X(15 * (1 - i))
  Wait 0.5
  Off 11
  Go P3 +X(-25)

Next i

Fend


Function TaskDrawing

Go P0
Call PickPencil
Call Drawing
Call Signature
Call PlacePencil
Go P0

Fend


Function PickPencil

Go P2 +Z(40)
Go P2
Wait 0.5
On 11
Go P2 +Z(40)

Fend


Function Drawing

'House Box...
Go P1 +Z(40)
Go P1
Go P1 +X(6*s)
Go P1 +X(6*s) +Y(10*s)
Go P1 +X(-6*s) +Y(10*s)
Go P1 +X(-6*s)
Go P1
Go P1 +Z(10)

'House Door...
Go P1 +X(2*s) +Z(10)
Go P1 +X(2*s)
Go P1 +X(2*s) +Y(4*s)
Go P1 +X(-2*s) +Y(4*s)
Go P1 +X(-2*s)
Go P1 +X(-2*s) +Z(10)

'House Handle...
Go P1 +X(1*s) +Y(2*s) +Z(10)
Go P1 +X(1*s) +Y(2*s)
Go P1 +X(1*s) +Y(2*s) +Z(10)

'House Window...
Go P1 +X(2*s) +Y(8*s) +Z(10)
Go P1 +X(2*s) +Y(8*s)
Go P1 +X(2*s) +Y(9*s) 
Go P1 +X(-2*s) +Y(9*s)
Go P1 +X(-2*s) +Y(7*s)
Go P1 +X(2*s) +Y(7*s)
Go P1 +X(2*s) +Y(8*s)
Go P1 +X(-2*s) +Y(8*s)
Go P1 +X(-2*s) +Y(8*s) +Z(10)

'House Window2...
Go P1 +Y(9*s) +Z(10)
Go P1 +Y(9*s)
Go P1 +Y(7*s)
Go P1 +Y(7*s) +Z(10)

'House Roof...
Go P1 +X(-6*s) +Y(10*s) +Z(10)
Go P1 +X(-6*s) +Y(10*s)
Go P1 +X(-8*s) +Y(10*s) 
Go P1 +Y(15*s) 
Go P1 +X(8*s) +Y(10*s) 
Go P1 +X(6*s) +Y(10*s)
Go P1 +X(6*s) +Y(10*s) +Z(10)

'House Chimney...
Go P1 +X(-5*s) +Y(12*s) +Z(10)
Go P1 +X(-5*s) +Y(12*s)
Go P1 +X(-5*s) +Y(14*s)
Go P1 +X(-3*s) +Y(14*s)
Go P1 +X(-3*s) +Y(13*s)
Go P1 +X(-3*s) +Y(13*s) +Z(40)

Fend


Function Signature

'G...
Go P1 +X(2.5*s) +Y(-3*s) +Z(40) 
Go P1 +X(2.5*s) +Y(-3*s)
Go P1 +X(2*s) +Y(-3*s)
Go P1 +X(2*s) +Y(-4*s)
Go P1 +X(2.5*s) +Y(-4*s)
Go P1 +X(2.5*s) +Y(-3.5*s)
Go P1 +X(2.25*s) +Y(-3.5*s)
Go P1 +X(2.25*s) +Y(-3.5*s) +Z(10)

'R...
Go P1 +X(3*s) +Y(-4*s) +Z(10)
Go P1 +X(3*s) +Y(-4*s)
Go P1 +X(3*s) +Y(-3*s)
Go P1 +X(3.5*s) +Y(-3*s)
Go P1 +X(3.5*s) +Y(-3.5*s)
Go P1 +X(3*s) +Y(-3.5*s)
Go P1 +X(3*s) +Y(-3.5*s) +Z(10)
Go P1 +X(3.25*s) +Y(-3.5*s) +Z(10)
Go P1 +X(3.25*s) +Y(-3.5*s)
Go P1 +X(3.5*s) +Y(-4*s)
Go P1 +X(3.5*s) +Y(-4*s) +Z(10)

'O...
Go P1 +X(4*s) +Y(-4*s) +Z(10)
Go P1 +X(4*s) +Y(-4*s)
Go P1 +X(4*s) +Y(-3*s)
Go P1 +X(4.5*s) +Y(-3*s)
Go P1 +X(4.5*s) +Y(-4*s)
Go P1 +X(4*s) +Y(-4*s)
Go P1 +X(4*s) +Y(-4*s) +Z(10)

'U...
Go P1 +X(5*s) +Y(-3*s) +Z(10)
Go P1 +X(5*s) +Y(-3*s)
Go P1 +X(5*s) +Y(-4*s)
Go P1 +X(5.5*s) +Y(-4*s)
Go P1 +X(5.5*s) +Y(-3*s)
Go P1 +X(5.5*s) +Y(-3*s) +Z(10)

'P...
Go P1 +X(6*s) +Y(-4*s) +Z(10)
Go P1 +X(6*s) +Y(-4*s)
Go P1 +X(6*s) +Y(-3*s)
Go P1 +X(6.5*s) +Y(-3*s)
Go P1 +X(6.5*s) +Y(-3.5*s)
Go P1 +X(6.5*s) +Y(-3.5*s)
Go P1 +X(6.5*s) +Y(-3.5*s) +Z(10)

'B...
Go P1 +X(3*s) +Y(-5.5*s) +Z(10)
Go P1 +X(3*s) +Y(-5.5*s)
Go P1 +X(3*s) +Y(-5*s)
Go P1 +X(3.4*s) +Y(-5*s)
Go P1 +X(3.4*s) +Y(-5.5*s)
Go P1 +X(3*s) +Y(-5.5*s)
Go P1 +X(3*s) +Y(-6*s)
Go P1 +X(3.5*s) +Y(-6*s)
Go P1 +X(3.5*s) +Y(-5.5*s)
Go P1 +X(3.4*s) +Y(-5.5*s)
Go P1 +X(3.4*s) +Y(-5.5*s) +Z(10)

'3...
Go P1 +X(4*s) +Y(-5*s) +Z(10)
Go P1 +X(4*s) +Y(-5*s)
Go P1 +X(4.5*s) +Y(-5*s)
Go P1 +X(4.5*s) +Y(-6*s)
Go P1 +X(4*s) +Y(-6*s)
Go P1 +X(4*s) +Y(-6*s) +Z(10)
Go P1 +X(4.2*s) +Y(-5.5*s) +Z(10)
Go P1 +X(4.2*s) +Y(-5.5*s)
Go P1 +X(4.5*s) +Y(-5.5*s) 
Go P1 +X(4.5*s) +Y(-5.5*s) +Z(40)

Fend


Function PlacePencil

Go P2 +Z(40)
Go P2
Off 11
Go P2 +Z(40)

Fend


