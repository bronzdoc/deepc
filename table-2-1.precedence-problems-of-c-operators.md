Table 2-1. Precedence Problems of C Operators

| Precendence problem                                                          | Expresion           | What people expect                         | What they actually get                                 |
|:-----------------------------------------------------------------------------|:-------------------:|:------------------------------------------:|:------------------------------------------------------:|
| . is higher precedence than * <br>the p->f op was<br>made to smooth over this| *p.f                | the f field of what p<br>points to (*p).f  | take the f offset from p,<br>use it as a pointer *(p.f)|
| [] is higher than *                                                          | int *ap[]           | ap is a ptr to array of ints<br>int(*ap)[] | ap is an array of ptrs-to-int<br> int *(ap[])          |
|  |                                                                           |                     |                                            |                                                        |


