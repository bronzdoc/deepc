Table 2-1. Symbol Overloading in C

| Symbol | Meaning           |
|:-------|:-----------------:|
| static | Inside a function, retains its value between calls<br>At the function level, visible only in this file |
| extern | Applied to a function definition, has global scope (and is redundant)<br>Applied to a variable, *defined elsewhere* |
| void   | As the return type of a function *doesn't return a value*<br>In a pointer declaration, the type of a generic pointer<br>In a parameter list, *takes no arguments* |
| *      | The multiplication operator<br>Applied to a pointer, indirection<br>In a declaration, a pointer |
| &      | Bitwise AND operator<br>Adress-of operator |
| =      | Assigment operator |
| ==     | Comparison operator |
| <=     | Less-than-or-equal-to operator |
| <<=    | Compound shift-left assignment operator |
| <      | Less-than operator<br>Left delimiter in #include directive |
| ()     | Enclose formal parameters in a function definition<br>Make a function call<br>Provide expression precedence<br>Convert (cast) a value to a different type<br>Define a macro with arguments<br>Make a macro call with arguments<br>Enclose the operand of the sizeof operator when it is a typename |

