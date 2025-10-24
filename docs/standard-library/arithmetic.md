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
### ***4.all arithmetic Operations***
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
