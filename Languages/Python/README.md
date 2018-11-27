# Python Language Cheat Sheet

The notes, tips, and examples I find useful for using Python (and acing coding interviews with it)

## Table of Contents
* [General Python](#general-python)
  * [Programs](#programs)
  * [Classes](#classes)
  * [Functions](#functions)
  * [Math](#math)
* [Strings](#strings)
  * [Notes](#string-notes)
* [Lists](#lists)
* [Stacks and Queues](#stacks-and-queues)
* [Linked Lists](#linked-lists)
* [Sets](#sets)
* [Dictionaries (Maps)](#dictionaries-maps)
* [Heaps](#heaps)

## General Python
This section will focus on general information about Python. Things like: how to make a python script, using classes in python, how the language is interpreted, etc.

### Language Facts
* Python is a dynamic language in the sense that variable types can be implicitly converted at runtime. However, it is important to note that the interpreter keeps track of all types at runtime.
* Python is both a mix of call/pass-by-reference and call-by-value, similar to Java, referred to as __call-by-object-reference__. Immutable objects like integers, strings, tuples, etc. will be treated like _call-by-value_ and thus are not changed by a method. While on the other hand, if we pass in a list to a method it will change that list.

### Programs
A python script will just execute the top level code. So even if we define a `main` method, it will not be executed unless we explicitly call it. 
<details><summary>Example</summary>
<p>

```python
def main():
  print("Hello World!")
  
print("Goodbye.")
```
Will output `Goodbye.`

</p>
</details>

So if we want to place code in a `main` method for execution, our top-level code will have to do so via a call to `main()`.

<details><summary>Example</summary>
<p>

```python
def main():
  print("Hello World!")

if __name__== "__main__":
  main()

print("Goodbye.")
```
Will output:
> Hello World!

> Goodbye.

**Note:** In Python3, the if check isn't necessary. So the following program will have the same output as above:
```python
def main():
  print("Hello World!")

main()
print("Goodbye.")
```
</p>
</details>

### Classes
Notes on Python Classes will go here.

### Functions
* Optional parameters
* Multiple return values
* Lambda functions

**map**
Applies a given function to a list of one or more iterables, returning an iterable

### Types

### Operators and Universal Functions
* `//` integer division
* `**` power
* `len()`
* `enumerate(iterable, start=0)` returns an enumerable object, where the _next()_ method on this object will be a tuple with the index and the corresponding item from iterable.


### Math
Notes on basic math functions in python, and things like integer division.
#### Built-In Math Functions
These math-like functions come built in with Python and thus we don't need any imports.
* `min(iterable)` will return the smallest item in the iterable. If there are duplicate smallest items it will return the first one. If the iterable is empty it will throw a ValueError.
 * `min(arg1, arg2, ...)` is similar and will return the smallest argument out of all those provided.
* `max` is virtually the same as `min` but, well it returns the max
* `pow(x, y[, z])` Return x to the power y; if z is present, return x to the power y, modulo z. 
 * The two argument form `pow(x, y)` is equivalent to the power operator `x**y`
* `divmod(a,b)` takes two non-complex numbers and returns a pair of numbers consisting of the quotient and remainder when using integer division. Therefore `divmod(a,b)` will return `(a // b, a % b)`
* `round(number[, ndigits])`Return _number_ rounded to _ndigits_ precision after the decimal point. If _ndigits_ is omitted or is `None`, it returns the _number_ to its nearest integer.
 

## Strings
Notes on Strings

If you wanted to iterate over the lowercase alphabet, you could do so with
```python
from string import ascii_lowercase
for ch in ascii_lowercase:
 do_something()
```
### String Functions
* `str.capitalize()` returns a copy of the string with the first letter capitalized and the rest as lowercase
* `str.count(sub[, start[, end]])` Returns the number of non-overlapping occurrances of sub in the range start:end
* `str.endswith(suffix[, start[, end]])` and `str.startswith(prefix[, start[, end]])` use slicing notation
* `str.find(sub[, start[, end]])` Finds the lowest index of sub in str, returns `-1` if sub is not found
* `str.isalnum()` True if all alphanumeric and len>0.
  * Similar functions: `str.isalpha()`, `str.isdecimal()`, `str.isdigit()`, `str.islower()`, `str.isspace()` for only whitespace, `str.isupper()`, and `str.istitle()` for uppercase only follows an uncased (whitespace, punct, etc)
* `str.lower()` and `str.upper()` and `str.title()` do what we expect. `str.swapcase()` is also self-explanatory
* `str.join(iterable)` Returns a String which is the concatenation of strings in iterable. The joining sequence will be `str`
* `str.replace(old, new[, count])` Returns a copy with the first count (or all if count is not given) occurances of old replaced with new.
* `str.strip([chars])` Returns a copy with leading/trailing chars removed. If chars is not given defaults to whitespace.
* `str.partition(sep)` Split the string at the first occurrence of sep, and return a 3-tuple containing the part before the separator, the separator itself, and the part after the separator. If sep is not found returns (str, '', '')
* `str.split(sep=None, maxsplit=-1)` Return a list of the words in the string, using sep as the delimiter string. If maxsplit is given, at most maxsplit splits are done
  * Consecuative delimiters are not grouped, rather they lead to empty indices. So `'1,,2'.split(',')` returns `['1', '', '2'])`
  * **Note:** If sep is not specified or is None, then runs of consequative whitespace are regarded as single seperators


# Python Data Structures
Knowing how to use data structures is so important I actually made it a heading one!
## Lists
Lists are the bread and butter of python.
**Making a list**
* `[]` will make an empty list, and so will `list()`
* `[x]*k` will make a list of length k where each value is x

**List Iteration**
* Using `for i, val in enumerate(lst)` is easier than `for in range(..)`
#### List Functions
All of the below functions are called via the syntax `list.f()` where list is already defined. These functions come built-in.
* `.append(x)` will add item x to the end of the list, equivalent to `a[len(a):] = [x]`
* `.extend(iterable)` will add all of the items from iterable to the end of this list
* `.insert(i, x)` will insert item x at position i, shifting all following items
* `.remove(x)` will remove the first item x from the list, or throw a ValueError if it is not found
* `.pop([i])` removes and returns the item at index i. If no index is supplied, then it will remove the **last** item in the list.
* `.clear()` removes all items from the list, equivalent to `del a[:]`
* `.index(x[, start[, end]])` returns the index of item x if found, if not found raises a ValueError. Start and End using slicing notation, such as `a.index("val", 2, -2)` will search indicies 2, up until the third to last for "val"
  * If you just want to see if a list contains x, then simply do `if x in lst`
* `.count(x)` returns the number of times x is found in the list, if not found it returns 0
* `.sort(key=None, reversed=False)` will sort the list in place according to the key function. If reversed is True then the output is of course reversed
  * Example of key: `key=lambda student: student[2]` would sort based on the third argument of the tuple
* `reverse()` reverses the elements of the list in place
* `.copy()` returns a shallow copy of list, equivalent to `a[:]`
  * If you want a deep copy: import _copy_ and use `copied = copy.deepcopy(original)`

Some built in functions are also very helpful for lists, these functions use the syntax `f(list)`
* `sum()`

## Stacks and Queues

## Linked Lists

## Sets

* `.discard(x)` will remove x if it is present
* `.remove(x)` will remove x, but if it is not present it will throw a KeyError

## Dictionaries (Maps)
** Making a Dictionary **
* We can make an empty dictionary with `{}` or with `dict()`
* We can also make a dictionary via comprehension [https://python-3-patterns-idioms-test.readthedocs.io/en/latest/Comprehensions.html#dictionary-comprehensions](TODO Example)

** Dictionary Iteration **

### Dictionary Functions
* TODO

### Other Dictionaries
#### Counter
* A dict subclass for counting hashable objects. It is unordered.
* Trying to retrieve a key that is not in a counter will not throw an error, instead it will return zero.
* Make an empty Counter with `c = Counter()`
  * These counters are all the same: `Counter('catbutt')`, `Counter({'a':1, 'b':1, 'c':1, 't':3, 'u':1})`, or `Counter(a=1...)`
* `elements()` will return an iterator over elements repeating each as many times as its count. Arbitrary order
* `most_common([n])` returns a list of tuplies (elm, cnt) of the n most common elements and their counts. Most common to least. If `n` is ommitted then it returns all of their elements and their counts.
* `subtract(iterable-or-mapping)` reduces this counters counts by those counts in the param. Inputs and outputs can be negative.

## Heaps
