## control flow

### ***1. if***
(if (condition) (code to run if condition is true) (code to run if  condition is false))
```metta
!(if (> 1 2) (3 4) (5 6))
```

***output***
```metta
[true]
```
### ***2. case***
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
### ***3. let***
A simpler version that binds a single variable to a value in an expression.
```
(let $var $expr $val)
params:
$var: variable to carry the bounded value.
$expr: expression to bind to varaible.
$val:  Expression to evaluate after binding.
```
```metta 
!(let $x 5 (+ $x 3))

```
***output***
```metta
8
```
### 4. let*
multiple bindings at once, sequentially.
```
(let ($vars) $val)
params: 
$vars: one or more variables with their bindings.
$val: evaluation after binding.
```
```metta 
(let* (($x 5) 
      ($y 2))
      (+ $x $y)
)
```
***output***
```metta
7
```
### 5. println!
consoles/prints the output

```metta 
!(println! (hello world))
```
***output***
```metta
(hello world)
```
### 6. readln!
Reads text input from the user via the console/keyboard

```metta 
!(let $x (readln!) (println! $x))
```
***output***
```metta
outputs the user input text
```
### 7. trace!
prints intermediate values during execution

```metta 
!(trace! "Adding one and two!" (+ 1 2))
```
***output***
```metta
Adding one and two!
(3)
```

## type checking in PeTTa
### ***1. get-metatype***

```metta 
!(get-type 4) ; returns Grounded
!(get-type A) ; returns Symbol
!(get-type $a) ; returns Varaible
!(get-type (1 E)) ;returnsExpression
```
***output***
```metta
meta-type
```
