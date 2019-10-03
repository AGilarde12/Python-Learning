Euclid's Algorithm works in 3 steps to find the GCD (Greatest common deonominator) of two integers:

1. For two integers a and b, where a > b, divide a by b.
2. If the remainder, r, is 0, then stop: GCD is b.
3. Otherwise, set a to b, b to r, and repeat at step 1 until r is 0. 

```python
def gcd(a, b):
  while (b!= 0):
    temp_val = a
    a = b
    #recalculate b to the value of a
    b = temp_val % b
  # if 0 return a, if not keep going till 0
  return a
```
  
