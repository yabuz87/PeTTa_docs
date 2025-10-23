## MeTTa Error handling functions that don't works in PeTTa yet.
### ***1. Error***

```metta
    (Error (add "a" 2) BadType)
```
### work around:

```metta

```
### ***2. if-error***

```metta
!(if-error (Error 5 BadType) "Error!" "No error") ; Returns "Error!"
```
### work around:

```metta

```
### ***3. return-on-error***

```metta
!(return-on-error (Error 5 BadType) 6) ; Returns (Error 5 BadType)
!(return-on-error 5 6) ; Returns 6
```
### work around:

```metta

```