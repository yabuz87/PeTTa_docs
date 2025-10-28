### list and expression

#### ***1. fold-flat*** 
process every element of a flat list one by one, combining them into a single final value using a custom rule
```
(fold-flat $list $acc $combiner)
params
$list: list
$acc:  accumulator
$combiner: a combiner ( a function to process each element in the list)
```
***
```metta
(= (sum-combiner $acc $x) ; helper function to  combine two elements.
   (+ $acc $x))

!(fold-flat (1 2 3 4) 0 sum-combiner)
```
***output***
```metta
10
```
#### ***2. fold-nested*** 
process every element of a nested list one by one, combining them into a single final value using a custom rule
```
(fold-flat $list $acc $combiner)
params
$list: list
$acc:  accumulator
$combiner: a combiner ( a function to process each element in the list)
```
***
```metta
(= (sum-combiner $acc $x)(+ $acc $x));helper function

!(fold-nested (1 (2 3) (4 (5))) 0 sum-combiner)
```
***output***
```metta
15
```
#### ***3. map-flat*** 
Transforms each element of a flat list individually using a given function, producing a new list of results, unlike **fold-flat** which reduces a list to a single value.
```metta
(= (double $x)(* $x 2))

!(map-flat (1 2 3 4) double)

```
***output***
```metta
(2 4 6 8)
```
#### ***4. map-flat*** 
Recursively transforms each atomic element of a nested list using a given function, preserving the nested structure, unlike **map-flat** which only works on flat lists.
```metta
(= (double $x) (* $x 2))

!(map-nested (1 (2 3) (4 (5))) double)


```
***output***
```metta
(2 (4 6) (8 (10)))
```
#### ***5. sort-atom*** 
sorts element in ascending order
```metta
!(sort-atom (1 0 -4 5 6 9 5))
!(sort-atom (zebra banana apple))
```
***output***
```metta
((-4 0 1 5 5 6 9))
((apple banana zebra))
```

#### ***6. exclude-item*** 
 removes all occurence of an atom from the list. if the element is not a member of the list,returns the list itself. 
```metta
!(exclude-item 5 (1 4 5 5))
```
***output***
```metta
(1 4)
```
#### ***7. is-member*** 
checks wether it is a member or not in the list and retuns a boolean value
```metta
!(is-member 1 (1 3 4))
```
***output***
```metta
(true)
```
#### ***8. reverse*** 

```metta
!(reverse (2 3 45))
!(reverse ( apple banana potato))
```
***output***
```metta
((45 3 2))
((potato banana apple))
```