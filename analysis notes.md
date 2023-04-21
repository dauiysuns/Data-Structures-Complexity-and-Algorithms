# Algorithms & Data Structures

# Prerequisite Slides

Advanced Python Skills B01B

[https://docs.google.com/presentation/d/1H4G26Ppubex_QoksaNFsOkVfQflMFDdJZitJdBkYqjY/edit#slide=id.p](https://docs.google.com/presentation/d/1H4G26Ppubex_QoksaNFsOkVfQflMFDdJZitJdBkYqjY/edit#slide=id.p)

List Comprehension in Python 3

List Comprehension: Method to concisely create lists

- commonly used when a new list…
    - is result of some operations applied to all of its member of another sequence/iterable
    - Or elements that satisfy a certain condition

This where the **lambda** function is used, but… we will learn the other way for readability *

**Example:** Create a list with squares from [0,10)

```python
# Non-concise method:
squares = []

for x in range(10):
		squares.append(x**2)

# Concise method:

squares = [value**2 for value in range(10)] # list comprehension
```

How does it work?

**List comprehension consists of:**

- Square Brackets containing an expression
- For clause
- Then a zero or more for or if clauses

Result is a new list resulting from evaluating the expression in the context of for and if clauses that follow it

[x**2 for x in range(10)]

```python
# 1. Use list comprehension to store a list that looks like:
[[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]
From list A = [1,2,3] and B = [3,1,4]

# 2. Use list comprehension to turn a 2D array (vec) to 1D array
vec = [[1,2,3], [4,5,6], [7,8,9]]
Outputs → [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Tuples

**Tuples =** Immutable sequenceable data-type object

- Tuples are declared with parenthesis
- () is an empty tuple
- (50,) is a singleton tuple (the comma is required!)
- Tuples are sliceable; therefore, indexable using square brackets

TUPLES OPERATORS

| len((1, 2, 3)) | 3 | Length |
| --- | --- | --- |
| (1, 2, 3) + (4, 5, 6) | (1, 2, 3, 4, 5, 6) | Concatenation |
| ('Hi!',) * 4 | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | Repetition |
| 3 in (1, 2, 3) | True | Membership |
| for x in (1,2,3) : print (x, end = ' ') | 1 2 3 | Iteration |

BUILT-IN FUNCTIONS

*TEST: tuple hello and tuple world (MAKE SURE TO RETURN IN THE SAME FORMAT; EX. Lists = [’h’, ‘l’, ‘o’], don’t just have hlo

a = **max**(tuple) ; b = **min**(tuple)

↳ Returns the maximum valued item or minimum valued item from the tuple

a = **tuple**(sequence)

↳ Converts the given sequence into a tuple

Map & Filter

Why do we have them? 

**List Comprehension** allows us to create lists, 2D arrays, and matrices efficiently by using the fundamental notation concepts that are found in mathematical sets.

Map and Filter comes from the idea of Lambda or *Anonymous* functions. Moreover, we will see their uses very similar to **List comprehensions.**

*These are also iterator functions.*

Iterator Functions

**Iterator Function:** A function that returns an object that is iterable.

Example:

- The **range()** function returns an iterable collection of integer values that fit the criteria of the arguments

The map() function

a = map(*function_name, sequence)*

map() is a built-in function that applies a given function to every single value/item in the given sequence, and returns the result.

Example:

**def** square(x):

return x*x

list_a = [i for i in range(1,100)] # list(range(1,100))

list_b = list(**map**(square, list_a))

The filter() function

a = filter(*bool_function_name, sequence*)

filter() is a built-in function that filters out the items in the sequence that the function would evaluate to **True** (boolean based!) and returns the result

Example:

**def** isOdd(x):

return (x % 2) != 0

list_a = [i for i in range(1,100)]

list_b = list(

**filter**

(isOdd, list_a))

B02 - SETS

[https://docs.google.com/presentation/d/13jO1cF5zPDB3069iCUS501m0q00W2PQOslSU5DvnpIU/edit#slide=id.p](https://docs.google.com/presentation/d/13jO1cF5zPDB3069iCUS501m0q00W2PQOslSU5DvnpIU/edit#slide=id.p)

Sets (mathematical definitions; discrete)

**Set=** a well-defined collection of distinct objects, considered as an object in its own right. A set can be denoted with {} brackets mathematically

- A set does not need to be ordered {a,b,c} == {c,b,a}
- A set can contain duplicates; but the set with no duplicates of same objects will **still be considered equal (sets do not consider duplicates)**
    - **Example:** {a,b,c} == {a,a,b,b,b,c,c,c,c}
- A set can be expressed as a mathematical relationship
    - **Example:** A = {x|2x+6 = 0}
        - “set A consists of members of x; such that 2 times x plus 6 equals 0”
        - This can be also explicitly A = {-3}

> **“A set is a collection of discrete data items. The members of the set can be numbers or names.”**
> 

Common Practice in Math

Capital Letters are used as variables to denote sets

**Example:** A = {-3}

Lowercase letters usually denote a specific member of a set

**Example:** b E A (“b is a member or element of set A”)

Membership (element of/not element of)

**Element of** (Member of):

- When a specific item is a member of a set, we can declare that they are an “element of” the set

**Not Element of** (Not a Member of):

- When a specific item is a not member of a set, we can declare that they are an “not an element of” the set

Subset A ⊆ B

*A =* {Mark, Angela}

*B =* {Mark, Angela, Frank, Laura}

**Subsets:** any set whose its members are elements of another set

“*Set A is a subset of set B because all elements of set A are in Set B”*

*“Any sets are a subset of itself”*

Subset and a Set can equal to each other*

Proper Subset A ⊂ B

*A =* {Mark, Angela}

*B =* {Mark, Angela, Frank, Laura}

**Proper Subsets:**

**Let A be a proper subset of B**

- All members of **A** must strictly exist in **B**
- **A** cannot be equal to **B**
- An empty set is a proper subset to a nonempty set

*“Set A is a proper subset of B”*

Basic Set Properties

**Set within a Set:**

- *A* = { {Mark, Angela}, {Frank, Laura} }
- *A =* { Mark, Angela, Frank, Laura } #Both sets are equal

**Number of members → Vertical Line**

- ***A =* { Mark, Angela, Frank, Laura } ; |A| = 4**

**Set with no elements/members:**

- “empty set” or “null set” **∅ or { }**

**Power Set → P:** A set with all the subsets of the set

- B = {Fred, Mary}
- P(B) = { {}, {Fred}, {Mary}, {Fred,Mary} }

Set Operations

Union A **∪ B**

**Union:** The union of set A and set B is the result of all its member into a singular set with duplicate members discarded

**Example:**

A={Mary, Mark, Fred, Angela, Frank, Laura}

B={Fred, Mary, Frank, Jane}

A U B = {Mary, Mark, Fred, Angela, Frank, Laura, Jane}

Intersection A **∩ B, X ∩ Y = ∅**

**Intersection:** The intersection of set A and B is members that are present in both sets

**Example:**

A={**Mary**, Mark, **Fred**, Angela, **Frank**, Laura}

B={**Fred**, **Mary**, **Frank**, Jane}

A intersect B = {Mary, Fred, Frank}

**Disjoint:** Two sets are considered to be “disjoint” if the intersection is empty

Subtraction A - B

*Read left to right

**Subtraction:** *it doesn't really exist…* The act of A - B results to removing the members that exist in set B from set A. (Do NOT leave in values that are in B but don’t exist in A… we are only considering A)

**Example:**

A={**Mary**, ****Mark, **Fred**, Angela, **Frank**, Laura}

B={Fred, Mary, Frank, Jane}

A - B = {Mark, Angela, Laura}

Symmetric Diference (isjunctive Union)

A **∆ B**

**Symmetric Difference:** Elements that are in either set, BUT they cannot **intersect**

**Example:**

A={Mary, Mark, Fred, Angela, Frank, Laura}

B={Fred, Mary, Frank, Jane}

Symmetric Difference(A,B) = {Mark, Angela, Jane, Laura}

Universe (set) U

**Universe:** A set that is defined to contain every possible members … all the values in our data set.

- Consider it as also: **union of all subsets**
- The Entire Database

Complement 

**Complement:** A complement of set A will be the set that contain members from the Universe set that doesn’t exist in set A

**Example:**

U = {Mary, Mark, Fred, Angela, Frank, Laura, Jane}

C = {Mary, Mark, Angela, Frank, Laura}

Complement of C = {Fred, Jane}

x̅

U - C = C (with a line over i cant find the symbol)

Python 3 Implementation

Sets in Python 3

**Sets:** A set is an **unordered collection** with no duplicate elements

- Uses: membership testing and eliminating duplicate entries
- are mutable!

Supported Operations:

- Union
- Intersection
- Difference
- Symmetric Difference

Set is a built-in DataType in Python 3

```python
# Basic Declaration
basket = {'apple', 'orange', 'apple', 'pear', 'orange’}

print(“orange” in basket) # True
print(basket)
# output → {‘apple’, ‘orange’, ’pear’}

# using set()
a = set('abracadabra')
print(a) # output → {‘a’, ‘b’, ‘r’, ‘c’, ‘d’}
```

*Strings, Lists, Tuples: will have to iterate through every item in them (as many operations as there are items) to find if an item is found within them,

*set will immediately find the memory address of the item! (more efficient)

```python
# Set Operations
a = set('abracadabra') # a = {‘a’, ‘b’, ‘r’, ‘c’, ‘d’}
b = set('alacazam') # b = {‘a’ ,’l’, ‘c’, ‘z’, ‘m’}

print(a-b) # a - b (subtraction) = {‘b’, ‘r’, ‘d’}
print(a|b) # a | b (a or b) … exists in a or b … or both
# a|b = {'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'} … union

print(a & b) # a & b = {‘a’,’c’} … intersection of set A and B

print(a ^ b) 
#Symmetric difference, a member in either set but not both
#{'r', 'd', 'b', 'm', 'z', 'l'}
```

```python
# Let s be a set
		len(s) → returns the size of the set
		x in s ; x not in s → membership comparison
		s.isdisjoint(a) → isdisjoint checker
		s.issubset(a) OR s <= a → subset checker
		s < a → proper subset checker
		s.union(a) OR s | a → union operation
		s.intersection(a) OR s & a → intersection operation
		s.difference(a) OR s - a → difference operation
		s.symmetric_difference(a) OR s ^ a → symmetric difference
		s.copy() → provides a shallow copy
		
#Note: You can convert a set to a list and a list to a set
```

### Set Comprehension

Sets in Python 3 also supports comprehension like a list.

**Example:**

```python
a = {x **for** x **in** 'abracadabra' **if** x **not in** 'abc'}
# result: a = {‘r’, ‘d’}

a =

**set**

()

**# empty set not {}**
```

What can we do with Sets in Python 3:

- Check membership → x **in** set
- Determine the number of members → **len**(set)
- Iterate through the set → **for** x **in** set

What can’t we do with Sets:

- Sets are not indexable
- Set cannot be sliced
- Sets have no sequence-like behavior

Sets don’t record element position or order of insertion; therefore, we cannot sort

Set Assignment Operations

```python
# let setA and setB be sets

setA |= setB # Assigns the union of A and B to A
# works also with setA.update(setB)

setA &= setB # Assigns the intersection of A and B to A
# works also with setA.intersection_update(setB)

setA -= setB # Assigns the difference of A and B to A
# works also with setA.difference_update(setB)

setA ^= setB # The symmetric difference of A and B to A
# works also with setA.symmetric_difference_update(setB)
```

Built-in Statements for sets

```python
# Let s be a set

s.**add**(elem) # adds *elem* to the set

s.**remove**(elem) # removes *elem* from the set; error if elem DNE

s.**pop**() # removes the last element from the set, and returns it (error when set is empty)

s.**discard**(elem) # removes *elem* from the set if *elem* exists

s.**clear()** # empties the set
```

DNE → “Does Not Exist”

Why use sets?

We use sets when:

- We need to speed up → “Is X in my Dataset”
    - For lists [2,3], will have to check for every item, but with sets, {2,3}, only checks once
- We can’t have duplicate values
- We don’t need to worry about indexing

B03 Dictionary (Associative Arrays)

[https://docs.google.com/presentation/d/1ZAEmDLkcEQNTccYlOEUm1Yp5YFg_B2CrmtubEFaupv8/edit#slide=id.p](https://docs.google.com/presentation/d/1ZAEmDLkcEQNTccYlOEUm1Yp5YFg_B2CrmtubEFaupv8/edit#slide=id.p)

**Dictionary** (Associative Array, map, symbol table) is a data type that stores a collection of (key, value) pairs (think of key like an address), such that each possible **key appears at most once** in the collection

Common Operations:

- Adding a pair
- Removing a pair
- Modify an existing pair
- Lookup of a value associated with a particular key

This concept is an introduction to concepts similar to: *hash table and search trees*

**Why Dictionaries are powerful? (useful features)**

1. “Customized and Systematic Indexing our Dataset”

**Example:**

Imagine a normal array/list containing “student numbers”

If we delete index of 42, every student number in the dataset has to be remapped.

If each student number had a unique address, address 42 might be **null,** and we may update with a new student number while keeping all the other indices safe.

1. “Our index, which are called **keys,** doesn’t need to be ordered”

**Example:** I want an item to be in a special location.

Lists cannot put an item in a distinct index, unless the indices previous to it is occupied.

Where as a singleton dictionary’s item will have a unique address that can be referenced to retrieve the item’s value.

In the same sense, we can delete a value from a dictionary, and it will

**still maintain**

its dataset size/length as long the key is preserved

In Python 3

Python contains an efficient key/value “hash table” (a data structure) called “**dict**”.

We can create a dictionary using braces {} *(an empty dict)*

The items within a Dictionary follows the format:

**key: value #** Values can be any object available

Example of a dictionary would be:

sammy = {‘username’: ‘sammy’, ‘online’: True, ‘followers’: 42}

*test empty dict = {}, empty set = set()

*sets always have format of {’key/address’, ‘value’}

Keys: Unique address for an item in a dictionary

- Must use an **immutable** data type: strings, numbers, tuples, frozen set

Keys are:

- Unique; therefore, two same key values cannot exist in a single dictionary **NEWEST CREATED ITEM with a duplicate KEY wins**
- **Immutable**

If A is a dictionary, and we have *“address”* as a key

print(A[“address”]) gives us the value of the item @ address.

Functions and Methods

```python
# Let A be a dictionary
len(A) # returns the length of dictionary = data set size
str(A) # returns the dictionary as a string
type(A) # returns that A is a dict

___
# To search for an existing key, we use membership
x in A # True if x is a key/address in A
x not in A # True if x is not a key/address in A

___
# Let A and B be a dictionary … dict is a built-in keyword
A.clear() # removes all elements/items of A
A.copy() # shallow copy of A

B = dict.fromkeys(A) 
# B is now dictionary with the same keys of A
# Items of B has null values, but contain addresses of A

___
# Let A and B be a dictionary
A.keys() # Returns a sequence of keys/addresses in A
A.values() # Returns a sequence of item values in A
A.items() # Returns a sequence of key,item pairs in A

A.get(address) # Returns the item value at address

A.update(B) 
# Extends A with the dictionary of key,value pairs of B

del A[address] 
# deletes the (key,value) object at that location
```

dict() constructor

A **list of tuples** can be turned to a dictionary item (key, value) pair by using dict()

**Example:**

```python
dict([(‘one’,3),(‘two’,3),(‘three’,5)])
# Returns:
# {‘one’: 3, ‘two’: 3, ‘three’: 5}

# dict comprehension
{x: int(x)**2 for x in (‘2’,’4’,’6’)}

#Returns: {‘2’: 4, ‘4’: 16, ‘6’: 36}
```

Implementation 

```python
students = {} # Empty dictionary

students[‘GWSS01’] = ‘Jake’
students[‘GWSS02’] = ‘Audrey’

# If printed → {'GWSS01': 'Jake', 'GWSS02': 'Audrey'}

marks = dict.fromkeys(students)

print(marks[‘GWSS02’]) # None
marks[‘GWSS02’] = 92
print(marks[‘GWSS02’]) # 92
```

iterating dictionaries (methods)

```python
students = {‘GWSS01’: ‘Jake’, ‘GWSS02’: ‘Audrey’}

# iterating keys (.keys)
for key in students.keys():
	print(key)

# iterating values (.values)
for values in students.values():
	print(values)

for pairs in students.items(): # Looking at key, value pairs
	print(pairs)

# unpacking (key, value) pairs of dictionary
for key, value in students.items(): 
	print(‘Key:’, key)
	print(‘Value:’, value)

'''Our iterating variables are “unpacked” to two separate variables. This is possible because .items() returns a list of Tuples that are: (key, value)

key & value are just iterating variables; therefore,'''
```

simple exercise

```python
#For each numbers from 2 to N (N → integer user input), Create a key, value pair of its Factors

#Example: Key 16 would have the List of → 1,2,4,8,16
```
