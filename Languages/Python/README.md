# Python Language Cheat Sheet

The notes, tips, and examples I find useful for using Python (and acing coding interviews with it)

## Table of Contents
* [General Python](#General-Python)
  * [Programs](#Programs)
* [Strings](#Strings)
  * [Notes](#string-notes)
* [Arrays](#arrays)
  * [Notes](#array-notes)
* [Recursion](#recursion)

## General Python
This section will focus on general information about Python. Things like: how to make a python script, using classes in python, how the langauge is interpreted, etc.

### Langauge Facts
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
So if we want to place code in a main method and execute it, our top-level code will have to do so.
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
* Mutliple return values

