# Standard Library Overview

PeTTa comes with a **set of additional functions** that extend the capabilities of the base MeTTa language.  
These functions form the **PeTTa Standard Library** and provide convenient utilities for common operations.

---

## What is the PeTTa Standard Library?

- The library includes functions for:
  - **Arithmetic operations** (`+`, `-`, `*`, `/`)
  - **List operations** (`cons-atom`, `car-atom`, `decons-atom`, etc.)
  - **Logical operations** (`and`, `or`, `not`)
  - **Comparison operations** (`==`, `<`, `>`, etc.)
  - **Control flow** (`if`, `case`)
  - **Meta-level functions** for introspection and advanced evaluation

- These functions are **predefined and ready to use** in PeTTa program.  
- They are designed to **simplify programming** and reduce repetitive code.

---

## How to Use the Standard Library

1. Simply write expressions using PeTTa functions in your `.metta` files.
2. Functions are already loaded when you run PeTTa; **no additional imports are required**.
3. Use examples in the `examples/` folder to understand behavior and expected output.

---
you can check functions in the examples folder.

```bash
time sh run.sh./examples/test.metta
```
