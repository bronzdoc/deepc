Table 2-1. Symbol Overloading in C

| Symbol                      | Meaning           |
| ----------------------------|:-----------------:|
| static                      | Inside a function, retains its value between calls
                                At the function level, visible only in this file |
| extern                      | Applied to a function definition, has global scope (and is redundant)
                                Applied to a variable, *defined elsewhere* |
| void                        | As the return type of a function *doesn't return a value*
                                In a pointer declaration, the type of a generic pointer
                                In a parameter list, *takes no arguments* |
| *                           | The multiplication operator
                                Applied to a pointer, indirection
                                In a declaration, a pointer |
| &                           | Bitwise AND operator
                                Adress-of operator |
| =                           | Assigment operator |
| ==                          | Comparison operator |
| <=                          | Less-than-or-equal-to operator |
| <<=                         | Compound shift-left assignment operator |
| <                           | Less-than operator
                                Left delimiter in #include directive |
| ()                          | Enclose formal parameters in a function definition
                                Make a function call
                                Provide expression precedence
                                Convert (cast) a value to a different type
                                Define a macro with arguments
                                Make a macro call with arguments
                                Enclose the operand of the sizeof operator when it is a typename |

