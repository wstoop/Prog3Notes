- C++ standard deals with semantics
- Compiler implements the standard. good semantics => machine code

| Layer        | interface                 | implementation | platform dependant? |
| ------------ | ------------------------- | -------------- | ------------------- |
| Applications | high level C++            | high level C++ | no                  |
| Library      | high level C++            | low level c++  | no                  |
| Engine       | low level C/C++           | low level      | yes                 |
| OS           | low level C/C++/assembler |                |                     |
| Hardware     |                           |                |                     |


**If you know low level stuff, you understand higher level stuff better**