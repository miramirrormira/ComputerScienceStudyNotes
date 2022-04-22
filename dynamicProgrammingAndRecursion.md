# Dynamic Programming and Recursion

What is Dynamic Programming?
Dynamic programming is mainly an optimization over plain recursion. Wherever we see a recursive solution that has repeated calls for same inputs, we optimize it using Dynamic Programming. The idea is to simply store the results of subproblems, so that we do not have to re-compute them when needed later. This simple optimization reduces time complexities from exponential to polynomial. 


## Memoization
Memoization ensures that a function doesn't run for the same inputs more than once by keeping a record of the results for the given inputs (usually in a dictionary).
```
struct Fib {
  var cache: [Int: Int] = [:]
  f(n: Int) {
     if let ans = cache[n] { return ans }
     if n <= 1 { return 1}
     cache[n] = f(n-1) + f(n-1)
     return cache[n]
  }
}
```

## Bottom-up Algorithms
With bottom-up approach, we start with knowing how to solve the problem for a simple case, like a list with only one element. Then we figure out how to solve the problem for two elements, and so on. 
Work from case 0 to case 1 ... to case N

## Top-Down Approach
Work from case N to case N-1 ... to case 0
