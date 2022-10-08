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
