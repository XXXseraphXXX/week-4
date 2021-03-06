# Week-4 Types and Ml Tutorial by Jimmy Zhang
## Introduction to Types
- A type is a Set of value 

In the variable x we can see that x is a varible of type int and that in-tails that x can take on any value from tne set of all integer values.
- **Example:** int x;
- The following types that are most commonly use: float, double, char, etc...
- There are different kind of types like primitive type and constructed type

**Primitive type** is a type that is not define
- Example: integer, char, boolean 

**Constructed type** is a user defined type
- Example: array, sets, list, tuples, function, etc...

  ![pc](prim.JPG)
### Supertype and Subset
A **supertype** is a subtype of an elements of a type 

What does that mean so in a language like c++ byte is a subtype of int 
we can observe:
  ![subset](subset.JPG)
- converting a value of a subtype to a values of the super-type is
called **widening type conversion.** (safe)
- it is safe because the two types are compatible and happen when user assign a value of a smaller type(subtype) to a bigger type(supertype) 
 ![widen](widen.png)
 
- converting a value of a supertype to a value of a subtype is
called **narrowing type conversion.** (not safe)
- it is not safe because error can be generated usually happen when user assign a value of a bigger type(supertype) to a smaller type(subtype)  
 ![narrow](narrow.png)

### Function type 
- Functions can be passed as values; just as values that belong to other data types
- Functions belong to function types
so in ml we can consider the function type real → int
This type represents the set of all functions from real to int
other member of this type would be :

  ![function](function.png)

- Example of functions as value:

fun example (x:real):int = round(x);

val example = fn:real -> int

- Example of functions as function arguments:

fun myfun(f:real -> int) = …;

myfun(round);

myfun(ceil);

**Static checking:** type checking done at compile time

**Dynamic checking:** type checking done at run time

### Type Equivalence 
- **Structural equivalence:** Names are replaced by the type expressions they define. If the resulting type expressions have the same structure(famework), they are equivalent.

 ![struct](struct.JPG)
 
- **Name equivalence:** Names are not replaced by the type expressions they define. Two expressions are equivalent if and only if they are structurally equivalent without name substitution.

typedef link struct *cell;

link next, last;

struct *cell p;

struct *cell q,r;

## Patterns
Patterns take on many appearances, such as:

- Constants: 150
- Variables: x
- Tuples: (true, _)
- Lists: x::xs
- cons

val (x,y) = (1,2)

  - The result is that 1 gets bound to x, and 2 gets bound to y.

  - Pattern matching may fail. For example, the following raises exception Bind.

val 10 = 9

Besides val declarations, pattern matching is also used in function declarations

fun length nil  = 0
   |    length (x::xs) = 1 + length(xs);

### Syntax let and in
- 'let' limit the score of the definition
- Variables defined with val between the let and the in are visible only from the point of declaration up to the end
![example](exampleP.png)
### mergesort
![merge](merge.png)

more information on mergehttps://en.wikipedia.org/wiki/Merge_sort

more practice: https://cs.fit.edu/~ryan/sml/intro.html

# Reference
- SML, Some Basic Examples, https://cs.fit.edu/~ryan/sml/intro.html. 
- “Merge Sort.” Wikipedia, Wikimedia Foundation, 4 May 2022, https://en.wikipedia.org/wiki/Merge_sort. 
- Webber, Adam. Modern Programming Languages: A Practical Introduction. Franklin, Beedle &amp; Associates, 2011.
- “Type Conversion in Java with Examples.” GeeksforGeeks, 22 Nov. 2021, https://www.geeksforgeeks.org/type-conversion-java-examples/. 
- https://brightspace.uri.edu/content/enforced/188472-2226_200753_3000_0000_SS3/CSC301_slides/Week%205%20LV1_%20Types.pdf?_&d2lSessionVal=dIGhiPJ4EpidZJxPUL279OQ1K&ou=188472
- https://brightspace.uri.edu/content/enforced/188472-2226_200753_3000_0000_SS3/CSC301_slides/Week%205%20LV2_%20A%20Second%20Look%20at%20ML.pdf?_&d2lSessionVal=mCaX3ciK9lF9UEkDVdnILjQWZ&ou=188472
