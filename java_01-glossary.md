## 1.1 symbols

1. braces (or call curly brackets)
    1. left brace: `{`
    1. right brace: `}`
    1. a pair of braces, or just braces: `{ }`
1. brackets (or call square brackets)
    1. left bracket: `[`
    1. right bracket: `]`
    1. a pair of brackets, or just brackets: `[ ]`
1. parentheses (`pəˈrɛnθəˌsiz`, or call round brackets)
    1. left parenthesis(`pəˈrenθəsɪs`): `(`
    1. rigth parenthesis: `)`
    1. a pair of parentheses, or just parentheses: `( )`
1. underscore: `_`
1. dollar sign: `$`
1. slash, "/", backslash `"\"`
1. vertical bar, `|`
1. ...
1. ampersand (ˈæmpərsænd), `&`
1. exclamation mark (ˌekskləˈmeɪʃn), `!`
1. single quotes (' ')
1. double quotes (" ")
1. varargs, Arbitrary Number of Arguments,  ellipsis (three dots, ...)
1. colon {koʊlən}: ":"
1. `circumflex {ˈsɜːrkəmfleks}`, "^"

## 1.2 variable and types


if we say fields, means instance and class variables; if we say variables, means all;

1. variables
    1. instance variables (non-static fields) 
        - defined in class, no `static` modifier;
        - unique in objects;
    1. class variables (static fields) 
        - defined in class, with `static` modifier;
        - shared with objects;
    1. constant variables
        - class variable, with `final` modifier;
    1. local variables
        - declared in `{}`, such as in functions;
    1. parameters
        - declared in function's `()`;
        - only can see in function's body;
    1. arguments
        - values passed to parameters during function call;
1. objects: reference type's instance;
1. fields
    1. instance variables (non-static fields) 
    1. class variables (static fields) 
1. class members
    1. fields
    1. methods
    1. nested class
1. nested class
    1. inner class (non-static nested class)
    1. static nested class

1.3 ## expression, statement

1. expression consists of variables, operators and methods call; expression can be evaluated and can be assigned to a variable;
    1. example
        - `i++`
        - `i + 3 / j`
        - `f(3)`
        - lambda expression
1. statement consists of expression, and commonly end of ";" (semicolon); expression can not be evaluated and can not be assigned to a variable;
    1. example
        - `i++;`
        - `i = i + 3 / j;`
        - `f(3);`


### example

```java

void f() {
    if (i > 3) {}
}
```
1. `if (i > 3) {}` is a if statements;
1. `i > 3` is an expression;

## 1.4 others

1. method signature: method name, and method parameters numbers, order, and type; (not include method parameter name);
    1. example
        - fx(int , int), fx(int, long), fx(long, int), fx(int), fx(long), all has different signature;
1. overload: method name is same, and method signature is different;
1. initialize/initialization
    1. {ɪˈnɪʃəlaɪz}
    1. "int x = 1;", means assign
1. instantiate/instantiation 
    1. {ɪnˌstænʃiˈeɪʃən}
    1. example: "Object obj = new Object();", means create an object of a class

