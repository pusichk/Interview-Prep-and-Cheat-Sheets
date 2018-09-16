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
  * [Notes](#array-notes)
* [Math](#math)

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

### Math
Notes on basic math functions in python, and things like integer division.
* min
* max
* divmod

## Strings
Notes on Strings

## Lists
Notes on lists
