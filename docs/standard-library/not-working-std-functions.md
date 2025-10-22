  most of the previous MeTTa/MeTTalog standard library functions work well in PeTTa but some of them are not done yet so it is good to see this document before writing a code in PeTTa to got some intution on std functions.

 ***1. bind!***
```metta
  !(bind! &myspace (new-space)) 
```
***output***
```metta 
(bind! &myspace (new-space))
```
### work around: 
```
```
 ***2. chain***
 this will be solved soon.
```metta
  !(chain (+ 2 4) $x (* $x 3)) 
```
***output***
```metta 
 ERROR:(main.pl path) Arguments are not sufficiently instantiated
```
### work around:
```
```
 ***3. if-decons-expr***
```metta
   !(if-decons-expr (1 2 3) $h $t (+ $h 1) (.....))
```
***output***
```metta 
 ERROR:(main.pl path) Arguments are not sufficiently instantiated
```
### work around:
#### using customized functions like this.
```metta
(= (if-decons-expr-custom $list $h $t $then $else)
      (if (or (== $list ()) (not (== (get-metatype $list) Expression)))
            $else
            (let* (
                  ($h (car-atom $list))
                  ($t (cdr-atom $list))
                  )
                  $then
            )
            ))

```
 ***4. unique-atom***

```metta
   !(unique-atom (1 2 3 4 3 3))  

```
***output***
```metta 
 (unique-atom (1 2 3 4 3 3))
```
### work around:
using custom function like this.
```metta
(= (unique-atom ()) ())
(= (unique-atom $list)
   (let* 
         (($tail (cdr-atom $list))
          ($head (car-atom $list))
          ($rest (if (memberfast $head $tail)
                         (unique-atom $tail)
                           (append ($head) (unique-atom  $tail))
                     ))
          )
          $rest
   ))

```
### ***5. cons-atom***
this function is replaced by cons
```metta
    !(cons-atom 3 (6 4 5)) 

```
***output***
```metta 
  (cons-atom 3 (6 4 5))
```
### work around:
using cons function instead of cons-atom it works just like cons-atom
```metta
  (cons 3 (6 4 5))
```
### ***6. decons-atom***
the MeTTa decons-atom is replaced by decons function with the same functionality except that in decons (PeTTa version)  the first atom is not embedded in parenthesis.
```metta
      !(decons-atom (1 2 3)) ; Returns ((1) (2 3))  MeTTa version
      !(decons (1 2 3)) ; Returns (1 (2 3))      PeTTa version

```
***output***
```metta 
   !(decons-atom (1 2 3)) ; Returns (decons-atom (1 2 3)) PeTTa version
```
### work around:
use decons function or use a custom function
```metta
!(decons (1 2 3)) ; Returns (1 (2 3))      PeTTa version
```




