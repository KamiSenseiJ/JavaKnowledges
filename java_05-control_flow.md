# 1. control flow statements

## 1.1 if


### 1.1.1 if

```java
void f() {
    int i = 1;
    int j = 3;
    boolean flag = false;
    
    if (i > j) {
        flag = true;
    }
}
```

### 1.1.2 if...else...

```java
void f() {
    int i = 1;
    int j = 3;
    boolean flag = false;
    
    if (i > j) {
        flag = true;
    } else {
        flag = false;
    }
}

```


### 1.1.3 if...if...else

```java
void f() {
    int i = 1;
    int j = 3;
    int k = 5;
    boolean flag = false;
    
    // not recommend
    if (i > j)
        if (j > k)
            flag = true;
        else   // this else belongs to which if ?
            flag = false;
        
    
    // better and clear
    if (i > j) {
        if (j > k) flag = true;
        else flag = false;
    }
}
```

1. in java, else belong inner most if; 


### 1.1.4  if...else if...

```java
void f() {
    int i = 1;
    int j = 3;
    int k = 5;
    boolean flag = false;
    
    if (i > j) {
        flag = true;
    } else if (i > k) {
        flag = false;
    } else if (j > k) {
        flag = false;
    } else {
        flag = true;
    }
}
```

## 1.2 switch

```java
int dayOfWeek = 1;
String dayOfWeekName = null;

switch (dayOfWeek) {
    case 1:  dayOfWeekName = "monday";
             break;
    case 2:  dayOfWeekName = "tuesday";
             break;
    case 3:  dayOfWeekName = "wednesday";
             break;
    case 4:  dayOfWeekName = "thursday";
             break;
    case 5:  dayOfWeekName = "friday";
             break;
    case 6:  dayOfWeekName = "saturday";
             break;
    case 7:  dayOfWeekName = "sunday";
             break;
    default: dayOfWeekName = "error";
             break;
}

String msg;
switch (dayOfWeek) {
    case 1: case 2: case 3:
    case 4: case 5:
             msg = "working";
             break;
    case 6:  case 7:
             msg = "weekend";
             break;
    default: msg = "error";
             break;
}

```
1. String in switch, use it equals() method for compare;
1. if no break statement, execution will continue from up to next break no matter whether case is equals;

## 1.3 while

### 1.3.1 while...do

```java
int i = 1;
int j = 3;
while (i <= j) {
    i++;
}
```
1. loop 1: i <= j, 1 <= 3, true
    1. i++, i = 2;
1. loop 2: i <= j, 2 <= 3, true
    1. i++, i = 3;
1. loop 3: i <= j, 3 <= 3, true
    1. i++, i = 4;
1. loop 4: i <= j, 4 <= 3, false
    1. loop stoped;
    1. i equals 4 finally;

### 1.3.2 do...while

```java
int i = 1;
int j = 3;
do {
    i++;
} while (i <= j);
```
1. loop 1: i++, i = 2;
    1. i <= j, 2 <= 3, true
1. loop 2: i++, i = 3;
    1. i <= j, 3 <= 3, true
1. loop 3: i++, i = 4;
    1. i <= j, 4 <= 3, false
    1. stop loop
    1. i equals 4 finally;

## 1.4 for statement

```java
for (initialization; condition; update) {
    // for body
}
```
1. initialization: execute once at the for loop begin;
1. condition: if condition is false, for loop terminate;
1. update: update state;
1. execute order after initialization executed: condition --> for body --> update;



### 1.4.1 common example

```java
int j = 3;

for (int i = 1; i <= j; i++) {
    System.out.println(i);
}
```
1. loop 1: i <= j, 1 <= 3, true
    1. print i, print 1;
    1. i++, i = 2;
1. loop 2: i <= j, 2 <= 3, true
    1. print i, print 2;
    1. i++, i = 3;
1. loop 3: i <= j, 3 <= 3, true
    1. print i, print 3;
    1. i++, i = 4;
1. loop 4: i <= j, 4 <= 3, false
    1. not execute the for body;
    1. not execute increment;
    1. so, i equals 4, finally;

## 1.5 break, continue

1. continue: end the current inermost loop and contine next loop
1. break: end the outmost loop











