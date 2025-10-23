## Higher Order Peridicates

### ***1. fold-flat*** 
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
### ***2. fold-nested*** 
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
### ***3. map-flat*** 
Transforms each element of a flat list individually using a given function, producing a new list of results, unlike **fold-flat** which reduces a list to a single value.
```metta
(= (double $x)(* $x 2))

!(map-flat (1 2 3 4) double)

```
***output***
```metta
(2 4 6 8)
```
### ***4. map-flat*** 
Recursively transforms each atomic element of a nested list using a given function, preserving the nested structure, unlike **map-flat** which only works on flat lists.
```metta
(= (double $x) (* $x 2))

!(map-nested (1 (2 3) (4 (5))) double)


```
***output***
```metta
(2 (4 6) (8 (10)))
```