### 1. list and expression

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

## 2. space manipulation
#### ***1. cut***
only cut out the first output from the all the patterns from the specified space.
```
!(match-single &self ($x $y) ($x $y))
```
```metta
(foo 1)
(foo 2)

(= (match-single $space $pat $ret)
   (let* (($x (match $space $pat $ret))
          ($temp (cut)))
         $x))
!(match-single &self ($x $y) ($x $y))
```
#### 2. readln!
Reads text input from the user via the console/keyboard

```metta 
!(let $x (readln!) (println! $x))
```

***output***
```metta
((foo 1))
```
## 3. python-binding
#### ***1. py-call***
built-in function in PeTTa that calls a Python function or expression and returns its result back into the MeTTa/PeTTa runtime.
```metta
(py-call (python_expression))

```
illustration
```metta
;Clean separation from Python calls
(= (make-object) (py-call (types.SimpleNamespace)))
(= (get-attribute $obj $name) (py-call (getattr $obj $name)))
(= (set-attribute $obj $name $value) (py-call (setattr $obj $name $value)))
(= (import $name) (py-call (importlib.import_module $name)))
(= (math.pi) (get-attribute (import math) pi))

;Clean program using objects and pi: 
!(test (let* (($obj (make-object))
              ($temp (set-attribute $obj foo (math.pi))))
             (get-attribute $obj foo))
       3.141592653589793)
```
## 4.MORK 
#### 1. mm2-exec
used to execute to implement mm2.here is an illustration.
```metta
;makes example fail without MORK:
!(mm2-exec &mork 1)

;generator: (separate non-det return of each item)
(= (range $K $N)
   (if (< $K $N)
       (superpose ($K (range (+ $K 1) $N)))
       (empty)))
                                      ;Add K atoms, then match 300000's times for friends relations:
!(let $temp (let $x (range 0 100000)  ;K=10000000  takes 48s    with MORK,   7s with predicate store
                                      ;K=50000000  takes 3m32s  with MORK,  36s with predicate store
                                      ;K=60000000  takes 4m5s   with MORK, 1m5s with predicate store
                                      ;K=100000000 takes 6m24s  with MORK, out of mem with predicate store
                                      ;K=200000000 takes 14m50s with MORK, out of mem with predicate store
                                      ;K=300000000 takes 20m2s  with MORK, out of mem with predicate store
                                      ;K=400000000 takes 28m21  with MORK, out of mem with predicate store
                                      ;K=500000000 out of mem   with MORK, out of mem with predicate store
                 (add-atom &mork (friend sam $x)))
      (empty))


!(let $temp (let $x (range 1 100000)
                 (match &mork (friend $y $x) (friend $y $x)))
      (empty))

!(let $temp (let $x (range 1 100000)
                 (match &mork (friend $y $x) (friend $y $x)))
      (empty))

!(let $temp (let $x (range 1 100000)
                 (match &mork (friend $y $x) (friend $y $x)))
      (empty))

!(remove-atom &mork (friend sam 42))
!(test (collapse (match &mork (friend sam 42) (friend sam 42))) ())
!(test (length (collapse (match &mork (friend $y $x) (friend $y $x)))) 99999)
```