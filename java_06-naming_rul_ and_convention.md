# 1. naming rule and convention

## 1.1 rule

1. name in java must begin with `"$"`, `"_"`, or `letter`
    1. so use "3number" for variable name will compiling error, use "number3" instead
1. subsequent characters can be `digit`, `"$"`, `"_"`, or `letter`
1. name can not be a keyword or reserved word
    1. example, "int class = 1;", class is keyword used for declare class can not used for variable name


## 1.2 naming convention

1. begin with letter, not `"$"`, `"_"`
    1. dollar sign is used for nested type naming in jvm internal
    1. subsequent characters should with `digit`, or `letter`

1. class name, each word should capitalize first letter
    1. example, "Calculator", "AddCalculator"
1. if variable is a single word, use lowercase, like apple, box; others capitalize every subsequent word's first letter, like appleNumber, boxColor
1. use fullname instead of abbreviations
    1. example, "numberOfApple" not "numOfApp"
1. use meaningful name instead of meaningless name, example, "appleCount" instead of "c"
1. if variable is constant, capitalize all words and slipt with "-", like APPLE_MAX_COUNT
    1. what is constant, we will talk in later course
