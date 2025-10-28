## space manipulation
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