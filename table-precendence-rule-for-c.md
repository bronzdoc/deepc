Table Precendece Rule

| The Precedence Rule for Understanding C Declarations |
|:----------------------------------------------------:|
| A | Declarations are read by starting with the name and then reading in precedence order. |
| B | The precedence, from high to low, is: |
|   | B.1 | parentheses grouping together parts of a declaration |
|   | B.2 | the postfix operators: |
|   |     | parentheses () indicating a function, and |
|   |     | square brackets [] indicating an array.   |
|   | B.3 | the prefix operator: the asterisk denoting "pointer to". |
| C | If a const and/or volatile keyword is next to a type specifier (e.g. int, long , etc.) it applies to the type specifier. Otherwise the const and/or volatile keyword applies to the pointer asterisk on its immediate left.|


char* const *(next)();

Table 3-1. Solving a Declaration Using the Precedence Rule

| Rule to apply | Explanation |
|:--------------|:------------|
| A   | First, go to the variable name, " next ", and note that it is directly enclosed by parentheses.|
| B.1 | So we group it with what else is in the parentheses, to get " next is a pointer to...".|
| B   | Then we go outside the parentheses, and have a choice of a prefix asterisk, or a postfix pair of parentheses.<Paste>|
| B.2 | Rule B.2 tells us the highest precedence thing is the function parentheses at the right, so we have " next is a pointer to a function returning..."|
| B.3 | Then process the prefix " * " to get "pointer to".|
| C   | Finally, take the " char * const ", as a constant pointer to a character.|

Then put it all together to read:
" next is a pointer to a function returning a pointer to a const pointer-to-char"
and we're done. The precedence rule is what all the rules boil down to.

