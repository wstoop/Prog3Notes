# Type
**Fundamental:**
- bool
- int
- double
- ...
**Compound:**
- bool*
- int[]
- double&
- enum
- struct
- class
- ...
# Value category
## Lvalue:
- located-inside-a-variable (located in memory)
- can be assigned to (is in RAM)
- binds to an Lvalue reference
### Examples:
- variables as we know them
## PRvalue
- pure-right-hand-side-of-an-assignment
- binds to an Rvalue reference
### Examples
- the literal number 12
- the result of built in operations (3 + 9, happens on the ALU)
## Xvalue
- eXpiring value => value is going to get destroyed(= safer for move)
- can be assigned to (is in RAM)
- binds to an Rvalue reference
### Examples

## Properties
### Lvalues
- address can be taken (&variable)
- can be written, if not => const
### PRvalues
- aren't stored => can't be written to
- usually automatic system (ALU, CPU) => dangerous to point to
### Xvalues
- usually on stack, sometimes ok to point at, sometimes not => be careful
