## comparisons

### ***1. assertEqual***
 Compares (sets of) results of evaluation of two expressions.

```
Parameters:
ExpressionAtom: First expression.
ExpressionAtom: Second expression.
```
```metta
!(assertEqual (+ 1 2) (- 6 3)) ; 
!(assertEqual (+ 1 2) (+ 2 2))
```
**output**

```metta
(); this is for the first asserEqual
;Expected: 4
;Got: 3
```
### ***2. test***
tests wether the two statments are true or not.
```metta
!(test (+ 4 2) (- 6 0))
!(test (+ 3 4) (+ 3 5))
```
**output**


```metta
is 6, should 6. ✅
is 7, should 8. ❌
```
## arthimetics

### ***1. ==***
strict equality.
```metta
!(== 2 3)
```
**output**

```metta
false
```
### ***2. >=***
less than or equal
```metta
!(<= 2 3)
```
**output**

```metta
true
```
### ***3. <=***
greater than or equal 
```metta
!(>= 10 20)
```
**output**

```metta
false
```
### ***4. arithmetic Operations***
operations
```metta
!(+ 2 3)
!(- 2 3)
!(* 2 3)
!(/ 2 3)
```
**output**

```metta
(5)
(-1)
(6)
(0.6666666666666666)
```
### ***5. min***
 returns minimum of two atoms
```metta
!(min 2 3)
```
**output**

```metta
2
```
### ***6. max***
 returns maximum of two atoms
```metta
!(max 2 3)
```
**output**

```metta
3
```
### ***7. exp***
Returns the natural exponential value of x, computed as 
𝑒^𝑥
,where e is the base of the natural logarithm.
```metta
!(exp 2)
```
**output**

```metta
(7.38905609893065)
```
## more on math functions

### ***1. pow-math***
```metta
!(pow-math 2 2)
```
**output**

```metta
(4)
```
### ***2. sqrt-math***
```metta
!(sqrt-math 4)
```
**output**

```metta
(2.0)
```
### ***3. abs-math***
```metta
!(abs-math -4)
```
**output**

```metta
(4)
```
### ***4. log-math***
```
!(log-math $base $number)
```
```metta
!(log-math 2 4)
```
**output**

```metta
(2.0)
```
### ***5. trunc-math***

```metta
!(trunc-math 4.5)
```
**output**
```metta
(4)
```
### ***6. ceil-math***

```metta
!(ceil-math 4.5)
```
**output**

```metta
(5)
```
### ***7. floor-math***

```metta
!(floor-math 4.5)
```
**output**

```metta
(4)
```
### ***8. round-math***

```metta
!(round-math 4.5)
```
**output**

```metta
(5)
```
### ***9. Trigonometric functions***

```metta
!(sin-math 0) ; Returns 0.0 the input param is angle in radian.
!(cos-math 0) ; Returns 1.0 the input param is angle in radian.
!(tan-math 0) ; Returns 0.0 the input param is angle in radian.
!(asin-math 0) ; Returns 0.0 the input param is floating point
!(acos-math 1) ; Returns 0.0 the input param is floating point
!(atan-math 0) ; Returns 0.0 the input param is floating point

```
**output**

```metta
(0.0)
(1.0)
(0.0)
(0.0)
(0.0)
(0.0)
```
### ***10. isnan-math***
Returns True if input value is NaN. False - otherwise
```metta
!(isnan-math 0.0)
```
**output**

```metta
(false)
```
### ***11. isinf-math***
Returns True if input value is positive or negative infinity. False - otherwise
```metta
!(isinf-math 0.0)
```
**output**

```metta
(false)
```
### ***12. min-atom***
Returns atom with min value in the expression. Only numbers allowed False - otherwise
```metta
!(min-atom (1 0 -3 4 5 6))
```
**output**

```metta
(-3)
```
### ***12. max-atom***
Returns atom with max value in the expression. Only numbers allowed
```metta
!(min-atom (1 0 -3 4 5 6))
```
**output**

```metta
(6)
```

