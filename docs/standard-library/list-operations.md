### list Manipulation

***(is-var )*** 
checks wether the input is variable or not and returns a boolean value.
```metta
!(is-var $x)
```
***output***
```metta
true
```
***(is-expr )*** 
checks wether the input is expression or not and returns a boolean value. expression is anything emebeded in parenthsis.
```metta
!(is-expr (foo 3))
```
***output***
```metta
true
```