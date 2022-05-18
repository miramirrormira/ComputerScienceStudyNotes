# [Master Theorem](https://www.youtube.com/watch?v=T68vN1FNY4o)

$$
T(n) = aT(\frac{n}{b}) + n^d, a >= 1, b > 1
$$
- n: the size of the current problem
- a: the number of subproblems in the recursion
- n/b: the size of each subproblems
- $n^d$: the cost of the work that has to be done outside the recursive calls, eg. cost of dividing and merging.

if $d > log_b^a$, $T(n) = \theta(n^d)$
if $d = log_b^a$, $T(n) = \theta(n^dlog_2^n)$
if $d < log_b^a$, $T(n) = \theta(n^{log_b^a})$

Uses:
- it is used to analyze recurrence relations
- userful for divide and conquer algorithms


Example:
$$
T(n) = 2T(\frac{n}{2}) + n
$$
1. Extract: a = 2, b = 2, and d = 1
2. Determine: $log_b^a$ = $log_2^2$ = 1
3. $log_b^a = d$
4. therefore, $T(n) = \theta(nlog_2^n)$
