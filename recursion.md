# Recursion

```
def fact(n):
    if n <= 1:
        return 1
    else:
        return n * fact(n-1)
```

- **Stack overflow** occurs when the base case is not reached or defined
  
## Difference between direct and indirect recursion
Direct recursion: a function is called direct recursive if it calls the same function.
```
def directRecFun():
    # some code...
    directRecFun()
    # some code...
```

Indirect recursion: a function fun1 is called indirect recursive if it calls another function fun2, which calls fun1 directly or indirectly.
```
def indirectRecFun1():
    # some code...
    indirectRecFun2()
    # some code...

def indirectRecFun2():
    # some code...
    indirectRecFun1()
    # some code...
```

## tailed and non-tailed recursion
A recursive function is tail recursive when recursive call is the last thing executed by the function.

Why do we care about tailed or non-tailed recursion?
The tail recursive functions considered better than non-tail recursive functions as tailed recursive functions can be optimized by the compiler. 