## 1.1 types overview

jvm and java types
1. primitive types, except returnAddress which is used for jvm internal, all defined in jvm and java language; 
    1. primitive type is built into the java language, operations on primitive type has corresponding bytecode directly supported by jvm; 
1. reference type is defined in jvm and java language; 
    1. we can think reference type is high level abstraction which consists of primitive type or another reference type;
1. null type defined by java language, jvm do not support for it;

`[` and `]` means inclusive, `(` and `)` means exclusive;


1. primitive type
    1. numeric type
        1. integral type
            - byte (8 bits signed two's-complement, `[-128, 127] / [-2^7, 2^7 - 1]`, default value `0`); 
            - short (16 bits signed two's-complement, `[-32768, 32767] / [-2^15, 2^15 - 1]`, default value `0`); 
            - int (32 bits signed two's-complement, `[-2147483648, 2147483647] / [-2^31, 2^31 - 1]`, default value `0`); 
            - long (64 bits signed two's-complement, `[-9223372036854775808, 9223372036854775807] / [-2^63, 2^63 - 1]`, default value `0L`); 
            - char (16 bits unsigned represents unicode BMP's code points, utf-16 encoding, `[0, 65535]`, default value `\u0000`/`null`/`NUL`);
        1. floating point type
            - float  (32bits IEEE 754 binary32 format, default value `+0.0f`);
            - double (64bits IEEE 754 binary64 format, default value `+0.0d`);
    1. boolean type
        - boolean (true or false, default value `false`);
    1. returnAddress (pointers to the opcodes of jvm instructions, only used by jvm internal);
        - used by jsr, ret, and jsr_w instructions;
        - used to implements `finally {}`, after java 7, almost no longer used; 
1. reference type (pointer to an object in jvm's heap, default is `null` which is a special reference means point to nothing);
    1. class
    1. interface
    1. array: in jvm, array is an object too stoed in java's heap, so we can pass array directly to method's parameter with no memory copy;
1. null type: no name, can not direct declare; we can simply treat null as a special literal;
    1. defined by java, jvm does not support for null type;
        - in jvm, null is a special reference, has no runtime type, and can cast to reference type;
        - in jvm, `aconst_null` instruction is used for assign null reference to an reference type indirectly;
        - jvm does not assume null's value, in other programming language commonly treat null as NUL `\0`;
    1. null reference is only value of the null type, null type can convert to any kind of reference type;
        - so, `Object obj = null`, convert a null type which value is null to a Object reference type, and assigned to obj variable, in strictly speaking;

note

1. fields (instance or class variable) has default value, local variables has no default value;
    1. local variables must initialized before use, or compile error;

### char type

1. char can not be used to represents every unicode's code points;
    1. it only can be used to represents unicode'a Basic Multilingual Plane (BMP), from `\u0000` to `\uffff`;
        - `\u`: represents unicode's code points, hexadecimal (`heksəˈdesɪml`); 
    1. if we declare `char c1 = '🏴'`, will get a bug, `\u01f3f4` will be truncate;
1. in internationalization, do not use char to represents a character, use `java.lang.String` instead;

### floating point type

1. floating type is non precise values, should not used for financial;
    1. use integer or `java.math.BigDecimal` instead;

### boolean type

1. java and jvm defined boolean type, but jvm has limited support on it, cause historical reasons;
    1. in early java and jvm implements, no consider for boolean type support, just like utf-16 char in java and jvm;
    1. for backward compatibility, this does not changed in modern java and jvm implements;
1. jvm has no boolean instructions for it;
    1. java boolean type will compiled to int type, boolean value will stored in int in jvm;
    1. java boolean expressions will compiled to int type;
        - `i > j` expression represents a boolean value in java, will compiled to int;
        - `0` represents false, non-zero represents true; (similar to c/cpp boolean type);
        - boolean operation use int instructions, just like byte, char, short;
        - boolean expression implemented in jvm by condition control instructions, like ifXXX;
    1. jvm directly support boolean array;
        - `newarray` instruction can be used for create boolean array;
        - but boolean array's elements access and modify is used `baload`、`bastore` instructions (byte array instructions);

### array

array is consecutive of memory, that can store many values of a single type;

1. each values of array call elements;
    1. the index of the first element of an array is 0, not 1;
1. array's length (elements total number) can not be changed when array been created;
1. array is reference type, array variable or object is stored in the java heap, managed by jc;
    1. array variable passed in function call by reference, not the value;

## 1.2 type conversion

```java
public class TypeConversion {
    public static void main(String... args) {

        // widening conversion 1: may lost precision
        int i1 = 2147483647;
        float f1 = i1;   // should not use this type of conversion!
        /*
           after assignment
           f1 equals 2.14748365E9 (2147483650.0), lost precision
        */
        System.out.println(f1);      


        /*
            widening conversion 1: not lost precision
            1. smaller integral type to bigger integral type
                - byte to char, byte to short, byte to long
                - char to int, char to long
                - short to int, int to long
                - int to long
            2. byte, short, char to float or double
            3. int, float to double
        */
        byte b1 = 127;
        short s1 = b1;             // this type of conversion can used in code cause not lost precision
        System.out.println(s1);    // 127


        /*
            narrowing conversion
            1. may lost precision
            2. need explicit conversion or compiling error
        */
        float f2 = 3.1415f;
        // int i2 = f2;   // compile error
        int i2 = (int) f2;   // explicit conversion (this type of conversion is not recommend)
        System.out.println(i2);   // 3 
    }
}
```


