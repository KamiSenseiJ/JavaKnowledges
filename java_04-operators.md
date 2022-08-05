# 1. operators

operator used for operating operands;

example: `i++`
1. `++` which calls operator
1. `i` which calls operands
    1. operands can be variable, or literals (like `i += 2`);


operator has precedence, when many operators comes in one expression, the highest precedence operating first

## 1.1 operators and precedence

operators	| precedence | associativity
-----------|----------------------|-----------------
postfix	| expr++  <br /> expr-- | 	left to right
unary	| ++expr <br />  --expr <br />  +expr <br />  -expr <br />  ~  <br /> ! | right to left
multiplicative		| * <br />  / <br />  %  | 	left to right
additive	| 	+  <br /> -  | 	left to right
shift	| 	<< <br />  >>  <br /> >>>  | 	left to right
relational		| <  <br /> > <br />  <=  <br /> >=  <br /> instanceof  | 	left to right
equality	| 	==  <br /> !=  | 	left to right
bitwise AND	|  	&  | 	left to right
bitwise exclusive OR	| 	^  | 	left to right
bitwise inclusive OR 	| 	&#124;  | 	left to right
logical AND		|   &&  | 	left to right
logical OR		|  &#124; &#124;  | 	left to right
ternary		| ? :   | right to left
assignment	| 	= <br /> +=  <br /> -= <br />  *= <br />  /=  <br /> %= <br />  &= <br />  ^=  <br /> &#124;=  <br /> <<=  <br /> >>=  <br /> >>>=  | right to left

1. top is precedence higher, bottom is precedence lower;
    1. example: `++` precedence is higher than `/`;
1. same line has the equals precedence;
    1. example: `++` and `--` at the same line, and has the equals precedence;
1. evaluate order
    1. if precedences are different, higher goes first;
        - example: `i = i + j / k;`, `/` is higher than `+` which higher than `=`, so `j / k` evaluate first and it's result `+` i, and assign to i;
    1. use `()` change evaluate order
        - example: `i = (i + j) / (k + p);`, `i + j` go first, then `k + p`, then `/`, last `=`;
    1. if precedences are same, depending on it's associativity;
        - simple: assignment operators are evaluated from right to left, other binary operators (has 2 operands) are from left to right;
        - example: `i = 3 / 2 * 5;`, `/` precedence equals `*`, so evaluated from left to right, `3 / 2` go first then `*`;
        - example: `i = j = k += 3;`, all operator precedences are same and all are assignment, so evaluated from right to left, `k += 3` go first (assume k origin is 2), k will be 5, then `j = k`, j will be 5, last `i = j`, i will be 5;

