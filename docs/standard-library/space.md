## space manipulation

### ***1. match***
matchs any pattern from the knowledge space.
```
!(match &space pattern output)
```
```metta
(1 2)
(1 5)
(1 3)
 !(match &self (1 $x) $x)
```

***output***
```metta
(2 5 3)
```
### ***2. bind!***
use to bind a knowledge space.
```
!(bind &space-name (new-space))
```
```metta
 !(bind! &mySpace (new-space))
```

***output***
```metta
()
```
### ***3. add-atom***
add a knowledge into the defined or created knowledge i.e. a pattern or rule.
```
!(add-atom &space-name knowledge)
```
```metta
 !(add-atom &mySpace (a b))
```

***output***
```metta
()
```
### ***4. remove-atom***
removes the occurence of that pattern from the knowledge base of that space.
```
!(remove-atom &space-name pattern)
```
```metta
(1 2)
(1 5)
(1 3);by default these patterns are considered to be a knowledge in this file knowledge space self.
 !(remove-atom &self (1 $x)); 
 !(match &self (1 $x) $x)
```

***output***
```metta
()
```