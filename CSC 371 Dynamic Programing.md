# Top Down
```python
F = [0,1,None...]
def fib(n):
	if F[n] != None:
		return F[n]
	else:
		F[n] = fib(n-2) + fib(n-1)
	return F[n]
```

# Bottom up
```python
def fib(n):
Define a local array F with size n+1
F[0] = 0
F[1] = 1
for i range(2,n+1):
	F[i] = F[i-1] + F[i-2]
return F[n]
```

# Dynamic Programming
- Paradigm in algorithm design.
- Uses optimal substructure
- Uses overlapping subproblems.
- Can be implemented bottom up/ top down
- It's a fancy name for a pretty common sense idea:
- Don't duplicate work if you don't have to

## Example 2: Knapsack Problem

# Steps for Dynamic Programing
1. Identify the optimal substructure
2. Find a recursive formulation for the value of the optimal solution
3. .
4. .
5. .
..

