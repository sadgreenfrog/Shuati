## Dynamic Programming

Dynamic Programming is a tool that will help make your recursive code more efficient.

More appropriately, I’d argue that we should always begin by identifying that we have a problem in front of us that requires the use of recursion.From there 
(and we will dive deeper into this later) we will be in a position to acknowledge that there may be some redundancy in the recursive calculations we are doing, 
and that perhaps there is a way through which we can improve upon our solution.

That method of improvement is dynamic programming.

I think it is counterproductive to look at a brand new problem and try to jump to the conclusion of whether or not it is a DP problem.

## The steps to tackling DP:

Fibonacci as an example:

## 1. Recursion

The initial step will always (always) be to begin by outlining what your pure, raw, unadulterated recursive solution will look like.

```python
def fib(n):
  if n == 1 or n == 2: # Base case
    return 1
  else:
    return fib(n-1) + fib(n-2)
```

The problem of this aprroach is that there are a lot of duplicates in our computation. E.g, f(5) = f(4) + f(3), f(4) = f(3) + f(2), we can see it calculates the
f(3) twice, we are repeating the same process many times. 

## 2. Recursion + Memoization

DP can and should be used if, by nature of your Step 1 solution, there are:

1) you’re solving the same subproblem multiple times over, and

2) by finding the optimal solution to a subproblem, you’re able to extract an optimal solution to the entire problem more-or-less for free.

Once we find the situations meet above conditions, we can find a way to solve it.

1) One line of code to store the result of a recursive call once we’ve calculated it

2) One piece of logic to check whether an item has already been calculated; if it has been, we will retrieve it and use it as opposed to recalculating it

```python
fibonacci_cashe = {}
def fib(n):
  if n in fibonacci_cache:
    return fibonacci_cache[n]
    
  if n == 1 or n==2 : # Base case
    value = 1
  else:
    value = fib(n-1) + fib(n-2)
   # Cache the value and return it
  fibonacci_cache[n] = value
  return value
```
## 3. Iteration + Tabulation

We will also use tabulation instead of memoization. Fundamentally, both accomplish the same goal — they store calculations we’ve previously done in order to 
reuse them for future iterations. However, tabulation will involve storing calculations in an array (most often a 2-dimensional one), while memoization most 
commonly refers to storing calculations in a set, object, dictionary, etc. Tabulation is what will allow us to iteratively walk through an array without relying 
on recursive calls.



https://medium.com/@mitrovic.aleksandar/the-ultimate-guide-to-dynamic-programming-65865ef7ec5b




