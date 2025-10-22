# control flow

## if 
(if (condition) (code to run if condition is true) (code to run if  condition is false))
```metta
!(if (> 1 2) (3 4) (5 6))
```

***output***
```metta
[true]
```
## case
switchs based on the given variable condition
```metta 
(= (casetest $x)
   (case $x ((4 42)
             ($otherpattern 44)
             ($otherother $45))))

!(casetest 5)
```
***output***
```metta
44
```
