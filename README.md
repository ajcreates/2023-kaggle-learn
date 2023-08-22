# Explore Kaggle with Codespaces & Jupyter Notebooks

## Learning Objectives

1. Learn Python basics to be able to natually write code
2. Learn how to convert algorithms into writable Python code
3. Learn how to problem-solve with Python on the spot
 

## About USACO
[USA Computing Olympiad (USACO)](http://www.usaco.org/index.php) is a competitive programming event for _high school students_. The USACO organization is a non-profit with the mission of motivating and training high-school computing students with:
 - training resources (free)
 - programming contests (online)
 - training camp (summer, invitation only)
 - opportunity for top 4 students each year to represent USA in the International Olympiad in Informations (IOI).


## USACO Requirements

The current USACO competitions require solutions to be written in one of three supported languages: `C++`, `Python` or `Java` - which aligns with the [TIOBE index](https://www.tiobe.com/tiobe-index/) in popular adoption rankings.

Code needs to optimize for _running time_ and _code size_, which can create added challenges based on selected language.
 - C++ is best from speed/size perspective, but is more complex to learn and debug for new programmers.
 - Python is the easiest to learn but may not always allow solutions that fit the time or size constraints.
 - Java is a good middle ground with moderate performance and ease of use, making it a good starting point for first-time competitive programmers.

**We will be using Python for problem-solving**

# 1️⃣ | Python Basics 

## What is Python 
Python uses a simple natural language syntax, incorporating many English words as key commands. Variables are used in Python to house various data types, typically named using lowercase lettering, with words separated by underscores. Variables and the data types they house are the main focus of a program, which intends to output a result. Functions can be applied to variables, which typically output a result based on the variable input. Various data structures such as lists, tuples, dictionaries and more can house large amounts of data with different uses and applications.

## Python Data Types 

### Strings 

Strings are pieces of texts denoted by single, double, or triple quotes
- Properties: Length(number of characters), Format(upper/lower case), Immutability, No Character Restrictions
- Uses: Concatonation, Copying, Splicing, Formatting, Parameter, Data Structure Incorporation
- Functions: str(), len(), find(), count(), index(), join(), upper(), lower(), format()

### Int 

Integers are numbers that can be expressed as a fraction p/q where q | 
- Properties: Value, Characters Limited To Numbers
- Uses: Arithmetic Operations, Iteration Type, Parameter, Comparisons, Data Structure Incorporation
- Functions: int(), abs(), floor(), ceil(), range(), imag()

### Booleans 

Booleans consist of two statements, either True or False
- Properties: Value(1 or 0), Answer To Question
- Uses: Logic Operations, Addition , Parameter, Comparisons
- Functions: bool()

## Parsing Files in Python

Knowing how to open, read, edit, and close files in Python is essential for USACO problems as both input files and output files are required. 

### Opening Files
* Opening files requires the use of the open() command which takes in parameters *File Name* and *Access Mode* and stores the file's contents in a variable. The type of Access Mode allows for variations in the possible operations that can be performed on files. Note that the Python program file and the opened file must be in the same directory to be accessed.
* Read Only('r') is the default parameter and only opens an existing file for reading line by line(usually a text file)
* Read and Write('r+') opens existing files for reading and writing
* Read and Append('a+') creates a file for editing and adds to the end of a file, not the beginning.

### Closing Files
* Files can be closed with the close() command, which frees memory and is needed to switch access modes.

### File Operations
* read(n) allows the entire contents of the file to be outputted and printed if need be, with the optional parameter of adding the exact number of characters to be outputted
* split() can also be used with files, separating segments of text into a list
* write() allows a string to be inserted into a file on a new line which also creating new files
* writelines() inserts multiple strings in a list into a file on separate lines
* **with** statements allow the arduous work of opening, editing, and closing files to be condensed into one or two line of code



# 2️⃣ | Time Complexity

USACO requires contestants to submit programs that run within a certain amount of time (**2 seconds for C and C++ and 4 seconds for Java and Python**). Therefore, it is very important to know relatively how long a program will take to run and if it can be simplified. 

One way to do this is by noting a program's **Time Complexity**, or the number of operations it takes to run an algorithm. **Big-O** notation is used for this. It takes in a program and outputs a worst-case scenario for complexity. Here are some examples for BigO complexity:


* `O(1)` 👉🏽 for basic input-output steps that don't iterate 
* `O(n)` 👉🏽 is the complexity of a loop with *n* iterations
* `O(*mn*)`👉🏽  Nested loops with *m* outer loop iteratons & *n* inner loop iterations: 
* `O(*a+b*)` 👉🏽  Independent non-nested operations with complexities O(*a*) and O(*b*)
* `O(1)` 👉🏽 Mathematical formulas outputting a calculated answer
* `O(*n log n*)` 👉🏽 Default Sorting: 
* `O(*2^n*)`👉🏽  Iterating though all subsets: 
* `O(*n!*)` 👉🏽 Iterating through all permutations:

**Note that Big-O is only an estimate. Many USACO Bronze problems have n < 100, leaving much room for error.**

## BigO References
 1. [USACO Guide - Time Complexity](https://usaco.guide/bronze/time-comp?lang=py) 
 2. [Visualization of BigO Notation](https://omicron.devillers.nl/demo)

<br/>
<br/>

# 3️⃣ | Problem Types

## 3.1 Rectangle Geometry

<details>
<summary>Rectangle geometry tasks often deal with coordinate geometry, area, and intersecting shapes. It is always important
to recognize whether rectangles are in fact parallel to the coordinate axis.  </summary>
<br/>

 * Rectangles are defined by top right(**tr**) and bottom left(**bl**) coordinates. 
    - width = **tr_x** - **bl_x**
    - length = **tr_y** - **bl_y**
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

</details>


## 3.2 Complete Search
USACO problems often require a "brute force" method called **complete search**, where a program iterates throughout an entire solution set, be it integers, combinations, or other objects. In Python, for and while loops are often used to iterate through elements, however, this method can be time-consuming. A technique called recursion is often used, in which certain data structures can be updated after each iteration of a loop, which compiles the results of a complete search within a single data structure, such as a list or dictionary.

### 3.2.1 Subsets

<details>
<summary>
Acquiring the subsets of a set of objects is a common task in USACO problems. If a set A has N elements, then it has 2^N subsets, which includes the empty set. 
</summary>
<br/>

In Python, we can use **bitmasks** to represent these subsets. With bitmasks, all integers from 0 to 2^(N-1) are converted to binary, representing all 2^N subsets. A 0 in this binary number shows that the corresponding element in set A is excluded from the subset, while a 1 shows that the element is included. The k-th digit from the right of the binary number is indicative of the inclusion of the k-1 element of set A. 

For example, the number 7 in binary is *111*, which indicates that the 0th, 1st, and 2nd elements of A are included in the subset. This opens up a whole new set of Python operations known as **bitwise operations**, about which more can be found at [USACO Guide - Intro to Bitwise Operations](https://usaco.guide/silver/intro-bitwise?lang=py)

</details>

### 3.2.2 Permutations

<details>
<summary>
Permutations are another possible result of complete searches, where objects such as lists, sets, tuples, characters, or numbers are reordered in all possible ways to generate a complete list of orderings. 
</summary>
<br/>

However, computers often take positions into account, rather than distinguishability, which often leads to problems. For example, the list [1,1,1] should only have 1 possible ordering but the computer simply reorganizes the positions of each element to generate 6 orderings that are identical. To remedy this, the **set()** command can be used, which removes such duplicates. 

It is also good to be familiar with **lexographical order**, a topic which appears often. This is a method of ordering permutations in a similar way that words can be organized alphabetically or numbers in increasing order. To compare two permutations, the first elements are compared and the permutations ordered alphabetically or numerically. If they are the same, the second elements are compared, then if needed the third, and so on. 

One can achieve this by applying the **sort()** command, but note that ordering N > 10! permutations can exceed time. To return a set of sorted permutations, one can apply the **itertools.permutations()**, sort(), and set() commands.
</details>

### 3.2.3 Chessboard Problems

<details>
<summary>
A popular set of USACO problems and puzzles in general, deal with the combinations of chess pieces on the board. 
</summary>
<br/>

When we place N chess pieces on the board, we can choose 64_C_N ways to do so, and multiplying this by all possible permutations, taking into account identical pieces. This is a time-consuming strategy that will likely not work, so applying the symmetry of the chessboard and the rules of chess can often cut down on time. 

Backtracking is another useful strategy, where we store the state of the board inside some variable, make an incremental change to the board, check its viability, and discard failures. The computer stores failed positions and with an optimal counting strategy, can help avoid repeated failure. The symmetry of a chessboard with yield multiple successful positions due to rotations and reflections and we will likely stumble upon one quickly with an optimal strategy.

</details>


## 3.3 Sorting 

<details>
<summary>
Sorting is an essential algorithmic skill when solving problems, it autmatically can reveal duplicate elements and simple iterations as well as simplifying complex arrays.
</summary>
<br/>
Common orders include alphabetical order, numerical order and lexographical order. Python allows
for the use of the built-in sorting commands **sort()** and **sorted()**, the first of which replaces the old list with a sorted one and the second of which returns a new sorted list. Both have a parameter called *key*, that allows for a specific sorting algorithm to be specified.

Most coding languages usse a sorting algorithm called **bubble sort** which takes a list and iterates through consecutive elements, rearranging them in the proper order and repeating this process over and over until the list is sorted. The mistakes the algorithm finds in consecutive elements are called *inversions* and a sorted list has 0 inversions. The time compexity of this is about O(n^2), compared to Python's built-in commands which run at an efficient O(n log n).

Python also provides convenient functions in its **operator** module to deal with common yet more complex types of sorting, utilizing the **itemgetter()**, **attrgetter()**, and **methodcaller()** commands
</details>

## 3.4 Sets and Maps

<details>
<summary>
A set is a group of elements that contain no duplicates, denoted by {} brackets and created with the **set()** command. 
</summary>
<br/>
Sets in Python utilize three major operations:

* `add(x)` adds the element x to a set if not already present
* `remove(x)` removes the element x from a set if present
* `x in s` checks whether the set *s* contains the element x
</details>
<details>
<summary>
A map in Python is called a dictionary (the **dict()** command) and contains elements of the form *key* : *value*, where instead of indices, one can refer to a value by its key. Dictionaries also utilize three major operations
</summary>
<br/>
Suppose we have a dictionary callled *stuff*. Then

* `stuff[x] = y` inserts the key-value pairing x : y into the dictionary
* `x in stuff` returns whether the key x is in the dictionary
* `del stuff[x]` deletes the key-value pairing that has key x

Dictionaries also allow for iteration over keys, values, or key-value pairings and allow for changes while iterating. Note that sorting methods can solve most problems requiring them but sets and dictionaries useful properties can simplify this.
</details>

## 3.5 Ad Hoc Problems

## 3.6 Greedy Algorithms

## 3.7 Graphs