# Assignment 12
## Task
1. The best case function is
   ```text
   return if low > high
   ```
 2. The function will keep recursing into negative numbers and never stop. AT some point it will cause a stack overflow error.
3.   the fixed code is:
   
   ```text
   def sum(low, high)
    return 0 if high < low
    return high + sum(low, high - 1)
end
```
