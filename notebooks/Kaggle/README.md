# My Kaggle Notebooks

## Python Syntax
Python uses a simple natural language syntax, incorporating many English words as key commands. Variables are used in Python to house various data types, typically named using lowercase lettering, with words separated by underscores. Variables and the data types they house are the main focus of a program, which intends to output a result. Functions can be applied to variables, which typically output a result based on the variable input. Various data structures such as lists, tuples, dictionaries and more can house large amounts of data with different uses and applications.

---

## Basic Python Data Types
Python utilizes a few basic data types within its syntax

Strings - Strings are pieces of texts denoted by single, double, or triple quotes.
    Properties: Length(number of characters), Format(upper/lower case), Immutability, No Character Restrictions
    Uses: Concatonation, Copying, Splicing, Formatting, Parameter, Data Structure Incorporation
    Functions: str(), len(), find(), count(), index(), join(), upper(), lower(), format()


Int - Integers are numbers that can be expressed as a fraction p/q where q | p
    Properties: Value, Characters Limited To Numbers
    Uses: Arithmetic Operations, Iteration Type, Parameter, Comparisons, Data Structure Incorporation
    Functions: int(), abs(), floor(), ceil(), range(), imag()

Booleans - Booleans consist of two statements, either True or False
    Properties: Value(1 or 0), Answer To Question
    Uses: Logic Operations, Addition , Parameter, Comparisons
    Functions: bool()

---

## Time Complexity

USACO requires contestants to submit programs that run within a certain amount of time(2 seconds fo C and C++ and 4 seconds for Java and Python). Therefore, it is very important to know relatively how long a program will take to run and if it can be simplified. One way to do this is by noting a program's **Time Complexity**, or the number of operations it takes to run an algorithm. To measure this, **Big-O** notation is used, which takes in a program and outputs a worst-case scenario for complexity.


* O(1) is defined to be the complexity of an operation that are basic input-output steps that don't iterate
* O(n) is the complexity of a loop with *n* iterations
* Nested loops with *m* outer loop iteratons and *n* inner loop iterations: O(*mn*)
* Independent non-nested operations with complexities O(*a*) and O(*b*): O(*a+b*)
* Mathematical formulas outputting a calculated answer: O(1)
* Default Sorting: O(*n log n*)
* Iterating though all subsets: O(*2^n*)
* Iterating through all permutations: O(*n!*)

Note that Big-O is only an estimate and many USACO Bronze problems have n < 100, leaving much room for error.
More information can be found at [USACO Guide - Time Complexity](https://usaco.guide/bronze/time-comp?lang=py) 
