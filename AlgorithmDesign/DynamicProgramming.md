# Dynamic Programming

Dynamic programming (DP) is a way of writing recursive algorithms in a more computationally efficient manner.

This is done by breaking the problem into subproblems, then storing (also known as caching) the results of the subproblems so that they do not have to be re-computed when needed again.

The two key attributes that a problem must have in order for DP to be applicable are:

- [*optimal substructure*](https://en.wikipedia.org/wiki/Optimal_substructure)  
  The solution to a given optimization problem can be obtained by the combination of optimal solutions to its sub-problems.

- [*overlapping sub-problems*](https://en.wikipedia.org/wiki/Overlapping_subproblems)
  It is said that a problem has *overlapping sub-problems* if it can be broken down into sub-problems, and the solutions to these sub-problem are reused multiple times.

There are two ways of implementing DP:

- *top-down (memoization)*  
  This starts at the initial (or top) problem and then recurses through the successive sub-problems. The solution to each sub-problem is then memoized,
  that is, if the sub-problem has not be solved, then we solve it and store it in memory (cache it). Any other time we need the solution to this sub-problem,
  then the already calculated result is returned, rather than reculating it.

- *bottom-up (tabulation)*
  This starts at the smallest sub-problem(s) and uses it to solve the next level sub-problem(s), continually building up until reaching (and solving) the desired problem.
  This is a *tabulation* approach as it focuses on sequentially filling the entries of the solution *table* (also storing in a cache)
  until reaching the value of the target problem.

Typically bottom-up (tabulation) will be more efficient than top-down (memoization) by a constant factor, as the last calculation can be returned as the desired result.
However, if not all sub-problems need to be solved, then top-down will only solve required sub-problems.

Memoization only caches solutions to sub-problems that have occurred when solving the original problem.  
Tabulation solves all possible sub-problems until reaching the solution to the original problem.

See:
- https://stackoverflow.blog/2022/01/31/the-complete-beginners-guide-to-dynamic-programming/
- https://towardsdatascience.com/beginners-guide-to-dynamic-programming-8eff07195667
- https://programming.guide/dynamic-programming-vs-memoization-vs-tabulation.html
- https://en.wikipedia.org/wiki/Dynamic_programming
- https://en.wikipedia.org/wiki/Memoization
- https://www.geeksforgeeks.org/tabulation-vs-memoization/
- https://www.baeldung.com/cs/tabulation-vs-memoization
- https://chialunwu.medium.com/wtf-is-memoization-a2979594fb2a

## Example: Fibonacci Numbers

This shows a recursive and a dynamic programming solution for calculating Fibonacci Numbers.
The recursive solution is O(1.6^n) which is exponential time, while the dynamic programming solution is O(n), linear time.

```C#
public int FibRecursive(int n)
{
    if (n > 1)
    {
        return FibRecursive(n-1) + FibRecursive(n-2);
    }
	
    return n;
}

// This DP implementation uses bottom-up with memoization
public int FibBottomUp(int n)
{
    var storage = new int[n+1];
    storage[0] = 0;
    storage[1] = 1;
	
    for (var i = 2; i <= n; i++)
    {
        storage[i] = storage[i-1] + storage[i-2];
    }
	
    return storage[n];
}

private int?[] memo;

// This DP implementation uses top-down with memoization
public int FibTopDown(int n)
{
    if (memo is null)
    {
        memo = new int?[n+1];
    }

    if (memo[n] is null)
    {
        if (n <= 1)
        {
            memo[n] = n;
        }
        else
        {
            memo[n] = FibTopDown(n-1, memo) + FibTopDown(n-2, memo);
        }
    }

    return memo[n].Value;
}
```

> Note:  
> The Fibonacci sequence also has a closed-form solution, which is O(1), or constant time.
> ```C#
> public int FibClosedForm(int n)
> {
>     var sqrtOf5 = Math.Sqrt(5);
>     var part1 = Math.Pow((1 + sqrtOf5)/2, n);
>     var part2 = Math.Pow((1 - sqrtOf5)/2, n);
>
>     // There will likely be mathematical precision errors, so Convert.ToInt32 will round the result.
>     return Convert.ToInt32(1 / sqrtOf5 * (part1 - part2));
> }
> ```


See:
- https://stackoverflow.com/questions/360748/computational-complexity-of-fibonacci-sequence
