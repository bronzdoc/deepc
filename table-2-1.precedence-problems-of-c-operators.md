Table 2-1. Precedence Problems of C Operators

| Precendence problem                                                          | Expresion            | What people expect                                   | What they actually get                                 |
|:-----------------------------------------------------------------------------|:--------------------:|:----------------------------------------------------:|:------------------------------------------------------:|
| . is higher precedence than * <br>the p->f op was<br>made to smooth over this| *p.f                 | the f field of what p<br>points to (*p).f            | take the f offset from p,<br>use it as a pointer *(p.f)|
| [] is higher than *                                                          | int *ap[]            | ap is a ptr to array of ints<br>int(*ap)[]           | ap is an array of ptrs-to-int<br> int *(ap[])          |
| function() higher than *                                                     | int *fp()            | fp is a ptr to function returning int<br> int(*fp)() | fp is a function returning ptr-to-int<br> int *(fp())  |
| == and != higher precedence than bitwise operators                           | (val&mask != 0)      | (val&mask) != 0                                      | val & (mask != 0)                                      |
| == and != higher precedence than assigment                                   | c = getchar() != EOF | (c = getchar()) != EOF                               | c = (getchar() != EOF)                                 |
| arithmetic higher precedence than shift                                      | msb << 4 + lsb       | (msb << 4) + lsb                                     | msb << (4+lsb)                                         |
| , has the lowest precedence of all operators                                 | i = 1, 2;            | i = (1, 2)                                           | (i = 1), 2;                                            |
