# 1. variable

java is a statically-typed language, every variable must have a type at compile time, so variable must be declared first before be used;

## 1.1 variable declare

### 1.1.1 primitive type

```java
class A {
    byte b = 100;
    short s = 100;
    int i = 100;
    long l = 100L;
    char c1 = 100; char c2 = 'd';

    float f = 1.11f;
    double d = 1.11;
    
    boolean flag = true;
    
    void f() {
        int i;   // it's ok, it we do not use it;
        i ++;    // compile error, local variable should initialize before use;
    }
}
```
1. `c2`: assign a character to it directly;
    1. character 'd' unicode code point is 100 in decimal, so c2's value will be `100`;


### 1.1.2 class type

```java
class A {};

class Main {
    A a1;
    A a2 = new A();
}
```
1. `a1`: default value is `null`;



### 1.1.3 interface type

```java
interface A {}
class B implements A {}

class Main {
    A a = new B();
}
```
1. interface can not be instantiated directly, use sub-class;


### 1.1.4 array type

array in java is a reference type also; (is a class type in more specificly?)

```java
int[] intArray;   // just declare an array, no memory allocate for now, intArray is a reference; 
intArray = new int [5];   //  contiguous allocate 5 * 32 bits memory; each int default value is 0;
intArray[0] = 0;          // access an array, use `[]` and index, index start 0 to 4, both include;
System.out.println(intArray.length);     // length is array's attribute, size of an array; here is 5;

String[] strArray = new String [5];

int[] intArray2 = {   // declare and initialize an array at same time, use `{}`;
    1, 2, 3,
    4, 5, 6, 
    7, 8, 9
};
```
1. brackets (`[]`);
    1. An array's type is written as `type[]`; type is the array's elements type;  the brackets are special symbols indicating that this variable holds an array.
    1. The size of the array is not part of its type (which is why the brackets are empty).
    1. c style `int intArray[]`, not recommend;
    1. array's index start 0;
1. `intArray[5] = 5;`, runtime error;
    1. in java, bounds will be checked when access array's elements; 
    1. `4` is the most high index of intArray, so access `intArray[5]` will throw `ArrayIndexOutOfBoundsException` at runtime;
        - array's index start with 0, so first element of intArray is `intArray[0]`;
        - last element of intArray is `intArray[intArray.length - 1]`, which equlas `intArray[5 - 1]`;
1. array's instance is an object, so no matter wherever you defined an array, like in fields or local, array is allocated in java heap, and managed by the gc;
    1. intArray, defined an int array, allocate 5 int which size is `5 * 4 = 20` bytes in heap;
    1. strArray: defined an String array, allocate 5 String object in heap;



you can defined multidimensional array, which elements is another array, unlike the c array;

```java
int[][] nums = {
            {1, 2, 3, 4, 5},
            {11, 13},
            {21, 22, 23, 24}
        };
```

1. multidimensional array's length;
    1. `System.out.println(nums.length);`, 3;
        - nums has 3 elements, each elements is another array which type is `int[]`;
        - first element is `{1, 2, 3, 4, 5}`, second element is `{11, 13}`, third element is `{21, 22, 23, 24}`;
        - so, `nums.length` means how many elements the nums array has, anwser is 3;
    1. `System.out.println(nums[0].length);`, 5;
        - nums's first element is `{1, 2, 3, 4, 5}` which has 5 elements, so `nums[0].length` is 5;
    1. `System.out.println(nums[1].length);`, 2;
    1. `System.out.println(nums[1].length);`, 4;
1. access multidimensional array
    1. `nums[0]` means we access the first element of array nums, which is `{1, 2, 3, 4, 5}`;
    1. `nums[0][0]` means we access the first element of array `{1, 2, 3, 4, 5}`, which is 1;
    1. so `nums[0][0]` equals `1`;
1. in java, each dimension of an array can vary;
    1. `System.out.println(nums[1][2]);`, throw `ArrayIndexOutOfBoundsException` when running;
