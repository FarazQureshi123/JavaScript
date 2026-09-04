# JavaScript Notes - Day 7: Assignment Operators

Welcome to **Day 7** of the JavaScript Learning Series! Today's session covers **Assignment Operators** in JavaScript, including basic assignments, compound arithmetic assignments, bitwise assignment operations, and shift assignments.

---

## 📌 What are Assignment Operators?

**Assignment Operators** are used to assign values to variables or update the existing values stored in variables based on various mathematical or logical calculations.

---

## 📚 Summary of Assignment Operators Learned

### 1. Simple Assignment Operator
Assigns the right-hand operand's value to the left-hand variable.
* `=` : `let a = 10;`

### 2. Compound Arithmetic Assignment Operators
Combines arithmetic operations with assignment to shorten code syntax.

| Operator | Syntax | Equivalent Expression | Description |
| :--- | :--- | :--- | :--- |
| `+=` | `a += b` | `a = a + b` | Adds `b` to `a` and reassigns result to `a` |
| `-=` | `a -= b` | `a = a - b` | Subtracts `b` from `a` and reassigns result to `a` |
| `*=` | `a *= b` | `a = a * b` | Multiplies `a` by `b` and reassigns result to `a` |
| `**=` | `a **= b` | `a = a ** b` | Raises `a` to power `b` and reassigns result to `a` |

---

### 3. Bitwise Assignment Operators
Performs bitwise operations on binary representations of numbers and reassigns the result.

* **AND Assignment (`&=`)**:
  * Example: `a = 5` (`0101`) and `a &= 3` (`0011`)
  * Bitwise `0101 & 0011` yields `0001` (Output: `1`)

* **OR Assignment (`|=`)**:
  * Example: `a = 5` (`0101`) and `a |= 3` (`0011`)
  * Bitwise `0101 | 0011` yields `0111` (Output: `7`)

* **XOR Assignment (`^=`)**:
  * Example: `a = 9` (`1001`) and `a ^= 3` (`0011`)
  * Bitwise `1001 ^ 0011` yields `1010` (Output: `10`)

---

### 4. Shift Assignment Operators
Shifts the binary representation of a number by a specified number of bits.

* **Left Shift Assignment (`<<=`)**: Shifts bits to the left (multiplies by $2^{\text{shift}}$).
  * Example: `c = 8`, `c <<= 1` ➔ Result: `16`
* **Right Shift Assignment (`>>=`)**: Shifts bits to the right preserving sign bit.
  * Example: `c = 16`, `c >>= 1` ➔ Result: `8`
* **Unsigned Right Shift Assignment (`>>>=`)**: Shifts bits to the right filling empty positions with zeros.

---

