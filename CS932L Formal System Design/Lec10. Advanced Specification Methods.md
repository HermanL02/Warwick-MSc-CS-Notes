# Arrays
Can model fixed length arrays as total functions

## Initialization 
```
myoptions : (1 . . 5) -> MODULE
mytimetable : (WEEKDAY × HOUR) -> SESSION
```
## Update
`
```
arr(i) := E
arr := arr <+ {i 7→ E}
arr := arr <+ {i 7→ E1, j 7→ E2}
```
### What cannot do?  
Cannot use multiple assignment **on the same array**

# Records 
A type of constructor: **struct**
An element of that type: **rec**

## Initialization
Example 1. 
```
persondata : struct(p name : NAME, p age : N)
persondata := rec(p name : myname, p age : 21)
```
Example 2. 
```
1. 
clubreg : MID 7→ struct(memname : NAME, memDOB : DOB)
2. 
clubreg := {}
clubreg(mm) := rec(memname : inputname, memDOB : inputDOB)
```
