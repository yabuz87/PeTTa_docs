## arithmetic and comparsion

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
### ***1.all arithmetic Operations***
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
