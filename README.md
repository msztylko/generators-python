# generators-python
Exploration of Python generators

## Iteration Protocol

Any object that supports `iter()` i.e.  
  * implements `__iter__()` method, or
  * supports the sequence protocol i.e.
    * implements `__getitem__()` method with integer arguments starting at 0.  
    
is said to be "iterable". [`iter()`](https://docs.python.org/3/library/functions.html#iter) returns iterator, so:
```python
iterator  = iter(iterable)
```

### For statement
```python
for x in obj:
    # statements
```
correponds to 
```python
_iter = iter(obj)             # get iterator object
while True:
    try:
        x = _iter.__next__()  # get next item
    except StopIteration:     # no more items
        break
    # statements
```

A common pattern is to implement `__next__()` and `__iter__()` returning object itself. This way object is its own iterator. 

## Generators
A generator is a function that produces a sequence of results instead of a single value, e.g.:
```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for i in countdown(5):
    print(i, end= ' ')
    
5 4 3 2 1
```

Generators have different behavior than normal function:
1. Calling a function returns result
2. Calling a generator creates generator object. However, it does not start running the function.




