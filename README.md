# Iterators
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
