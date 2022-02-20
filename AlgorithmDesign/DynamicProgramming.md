# Dynamic Programming

Dynamic programming (DP) is a way of writing recursive algorithms in a more computationally efficient manner.

This is done by breaking the problem into subproblems, then storing (also known as caching) the results of the subproblems so that they do not have to be re-computed when needed again.

The two key attributes that a problem must have in order for DP to be applicable are:
- [*optimal substructure*](https://en.wikipedia.org/wiki/Optimal_substructure)  
  The solution to a given optimization problem can be obtained by the combination of optimal solutions to its sub-problems.
- [*overlapping sub-problems*](https://en.wikipedia.org/wiki/Overlapping_subproblems)
  It is said that a problem has *overlapping sub-problems* if it can be broken down into sub-problems, and the solutions to these sub-problem are reused multiple times.

DP uses one of two techniques for improving the efficiency:
- [*memoization*]()  
  An optimisation technique in which a sub-problem's result is cached, so if the same sub-problem occurs the cached result is returned.
  
- *tabulation*  
  

There are two ways of implementing DP:
- *top-down (memoization)*  
  This starts at the initial problem and then solves the sub-problems at each recursion. As the solution to a new sub-problem is found it is memoized

- *bottom-up (tabulation)*


See:
- https://stackoverflow.blog/2022/01/31/the-complete-beginners-guide-to-dynamic-programming/
- https://towardsdatascience.com/beginners-guide-to-dynamic-programming-8eff07195667
- https://programming.guide/dynamic-programming-vs-memoization-vs-tabulation.html
- https://en.wikipedia.org/wiki/Dynamic_programming
- https://en.wikipedia.org/wiki/Memoization

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

// This DP implementation uses top-down with memoization
// Its initial call would not supply memo, eg: FibTopDown(10);
public int FibTopDown(int n, int?[] memo = null)
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
> The Fibonacci sequence also has a closed-form solution, which is O(1), which is constant time.
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
