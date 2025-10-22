### list Manipulation

### ***1. excludefast*** 
 removes all occurence of an atom from the list. if the element is not a member of the list,returns the list itself. 
```metta
!(excludefast 5 (1 4 5 5))
```
***output***
```metta
(1 4)
```
```metta
!(excludefast 0 (1 4 5 5))
```
***output***
```metta
(1 4 5 5)
```

### ***2. memberfast*** 
checks wether **element** is memebr of the list or not and returns a boolean value.
```metta
!(memberfast 0 (1 4 5))
```
***output***
```metta
false
```
### ***3. car-atom*** 
returns the first atom from the given list.
```metta
!(car-atom (1 2 4 3))
```
***output***
```metta
1
```
### ***3. cdr-atom*** 
returns the list except   from first atom in the list.
```metta
!(cdr-atom (1 2 4 3))
```
***output***
```metta
(2 4 3)
```
### ***4. decons*** 
```metta
!(cdr-atom (1 2 4 3))
```
***output***
```metta
(1 (2 4 3))
```
### ***5. cons*** 
    appends the an atom at the first index of the list
```metta
!(cons 0 (1 2 3))
```
***output***
```metta
(0 1 2 3)
```
### ***6. is-expr*** 
checks wether the input is expression or not and returns a boolean value. expression is anything emebeded in parenthsis.
```metta
!(is-expr (foo 3))
```
***output***
```metta
true
```
### ***7. is-var***
checks wether the input is variable or not and returns a boolean value.
```metta
!(is-var $x)
```
***output***
```metta
true
```

### ***8. substract*** 
list based Subtraction 
```
(subtract $pred $list $sub)

params
$pred:  predicate
$list: list
$sub:  list to subtract
the default predicate is equal (==)
```
```metta
!(subtract >= (1 2 3) (2 3))
```
***output***
```metta
(1)
```
### ***8. instersection*** 
list based intersection 
```metta
!(intersection  (1 2 3 4) (2 3 5))
```
***output***
```metta
(2 3)
```
### ***8. append*** 
concatenates two expression( lists)
```
 (append $expr1 $expr2 ) 
 $expr1 : the first list
 $expr2: the second list


```
```metta
!(append (1 3 4) (2 4 5 6))
```
***output***
```metta
(1 3 4 2 4 5 6)
```
## set Operations in PeTTa

### ***1. union*** 
set based onion operation
```metta
!(union (1) (2 3 4 5))
```
***output***
```metta
(1 2 3 4 5)
```
