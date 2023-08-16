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

---

## Rectangle Geometry

Rectangle geometry tasks often deal with coordinate geometry, area, and intersecting shapes. It is always important
to recognize whether rectangles are in fact parallel to the coordinate axis. Rectangles are usually defined by their top right(**tr**) and bottom left(**bl**) coordinates. From that, we have that:
* width = **tr_x** - **bl_x**
* length = **tr_y** - **bl_y**
* Rectangles *A* and *B* do not intersect if
    * **tr(A)_y** < **bl(B)_y**
    * **bl(A)_y** > **tr(B)_y**
    * **tr(A)_x** < **bl(B)_x**
    * **bl(A)_x** > **tr(B)_x**
* If the rectangles *A* and *B* intersect to form a rectangle, then that intersection has
    * width = min(**tr(A)_x**, **tr(B)_x**) - max(**bl(A)_x**, **bl(B)_x**)
    * length = min(**tr(A)_y**, **tr(B)_y**) - max(**bl(A)_y**, **bl(B)_y**)
    * If either of these quantities are non_positive, then *A* and *B* do not intersect

To learn more about Rectangle Geometry, visit [USACO Guide - Rectangle Geometry](https://usaco.guide/bronze/rect-geo?lang=py)

---

## Complete Search

USACO problems often require a "brute force" method called **complete search**, where a program iterates throughout an entire solution set, be it integers, combinations, or other objects. In Python, for and while loops are often used to iterate through elements, however, this method can be time-consuming. A technique called recursion is often used, in which certain data structures can be updated after each iteration of a loop, which compiles the results of a complete search within a single data structure, such as a list or dictionary.

# Subsets

Acquiring the subsets of a set of objects is a common task in USACO problems. If a set A has N elements, then it has 2^N subsets, which includes the empty set. In Python, we can use **bitmasks** to represent these subsets. With bitmasks, all integers from 0 to 2^(N-1) are converted to binary, representing all 2^N subsets. A 0 in this binary number shows that the corresponding element in set A is excluded from the subset, while a 1 shows that the element is included. The k-th digit from the right of the binary number is indicative of the inclusion of the k-1 element of set A. For example, the number 7 in binary is *111*, which indicates that the 0th, 1st, and 2nd elements of A are included in the subset. This opens up a whole new set of Python operations known as **bitwise operations**, about which more can be found at [USACO Guide - Intro to Bitwise Operations](https://usaco.guide/silver/intro-bitwise?lang=py)

# Permutations

Permutations are another possible result of complete searches, where objects such as lists, sets, tuples, characters, or numbers are reordered in all possible ways to generate a complete list of orderings. However, computers often take positions into account, rather than distinguishability, which often leads to problems. For example, the list [1,1,1] should only have 1 possible ordering but the computer simply reorganizes the positions of each element to generate 6 orderings that are identical. To remedy this, the **set()** command can be used, which removes such duplicates. It is also good to be familiar with **lexographical order**, a topic which appears often. This is a method of ordering permutations in a similar way that words can be organized alphabetically or numbers in increasing order. To compare two permutations, the first elements are compared and the permutations ordered alphabetically or numerically. If they are the same, the second elements are compared, then if needed the third, and so on. One can achieve this by applying the **sort()** command, but note that ordering N > 10! permutations can exceed time. To return a set of sorted permutations, one can apply the **itertools.permutations()**, sort(), and set() commands.

# Chessboard Problems

A popular set of USACO problems and puzzles in general, deal with the combinations of chess pieces on the board. When we place N chess pieces on the board, we can choose 64_C_N ways to do so, and multiplying this by all possible permutations, taking into account identical pieces. This is a time-consuming strategy that will likely not work, so applying the symmetry of the chessboard and the rules of chess can often cut down on time. Backtracking is another useful strategy, where we store the state of the board inside some variable, make an incremental change to the board, check its viability, and discard failures. The computer stores failed positions and with an optimal counting strategy, can help avoid repeated failure. The symmetry of a chessboard with yield multiple successful positions due to rotations and reflections and we will likely stumble upon one quickly with an optimal strategy.

---
