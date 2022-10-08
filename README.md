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
