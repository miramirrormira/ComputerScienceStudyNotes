# General Programming

## Short Circuit Evaluation
Most programming languages use short-circuit evaluation to avoid unnecessary work. 
```
if it_is_friday and it_is_raining:
    print "board games at my place!"
```
If it_is_friday is false, then Python 2.7 wouldn't bother checking the value of it_is_raining

## Garbage Collection
A garbage collector automatically frees up memory that a program isn't using anymore.


Methods:
- tracing garbage collection
- reference count
- manual memory management

