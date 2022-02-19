# Dynamic Programming

Dynamic programming is a way of writing recursive algorithms to make them more computationally efficient.

This is done by breaking the problem into subproblems, then storing the results of the subproblems so that they do not have to be re-computed when needed again.

Terms:
- memoization
- tabulation

See:
- https://stackoverflow.blog/2022/01/31/the-complete-beginners-guide-to-dynamic-programming/
- https://towardsdatascience.com/beginners-guide-to-dynamic-programming-8eff07195667
- https://programming.guide/dynamic-programming-vs-memoization-vs-tabulation.html

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

public int FibDP(int n)
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
```

> Note:  
> The Fibonacci sequence also has a closed-form solution, which is O(1), which is constant time.

See:
- https://stackoverflow.com/questions/360748/computational-complexity-of-fibonacci-sequence
