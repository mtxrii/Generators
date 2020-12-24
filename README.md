# What is this?
Here I'll be compiling a list of various generator functions. That is, manually created iterables that allow looping through some interesting values. I'll be using jupyter Notebooks and Google Colab to run these python files.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mtxrii/generators/)

More on generators...

## Iterators
Some objects in Python allow iteration. You've probably seen this pattern before:
```python
for x in y:
```

Objects that support this have an internal collection of items you can cycle through in loops. The most obvious examples are collections.
```python
for a in list():
for b in set():
for c in tuple():
for d in dict():
```

Strings also allow iteration. After all, internally they're just lists of characters.
```python
for char in "string":
```

In fact, all for loops in python are done this way. When looping a set number of times, you use the `range()` function.
```python
for i in range(5):
```
But how can a function create an iteration like that?

## Generators
Normal functions return something. This is done with the `return` keyword as we know.
```python
def add(x, y):
  return x + y
```

Generators are special functions that instead `yield` values. These functions provide a set of values, but instead of loading them all onto memory, they yield one value at a time. At every yield, the function pauses, sends the value back to the iteration, then picks up where it left off. This lets you make functions that effectively behave like iterable lists.

Here's an example of a function that yields each vowel in a string:
```python
def vowels(string):
  vowelChars = {'A', 'E', 'I', 'O', 'U'}
  for c in string.upper():
    if c in vowelChars:
      yield c
```
```python
for vowel in vowels("Hello, World!"):
  print(vowel)
```
