  most of the previous MeTTa/MeTTalog standard library functions work well in PeTTa but some of them are not done yet so it is good to see this document before writing a code in PeTTa to got some intution on std functions.

 ***1. bind!***
```metta
  !(bind! &myspace (new-space)) 
```
***PeTTa output***
```metta 
[(bind! &myspace (new-space))]
```
### work around: 
```
```
 ***2. chain***
```metta
  !(chain (+ 2 4) $x (* $x 3)) 
```
***PeTTa output***
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
***PeTTa output***
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


