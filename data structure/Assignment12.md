# Assignment 12
## Task
1. The best case function is
   ```text
   return if low > high
   ```
 2. The function will keep recursing into negative numbers and never stop. At some point it will cause a stack overflow error.
3.   the fixed code is:
   
   ```text
   def sum(low, high)
    return 0 if high < low
    return high + sum(low, high - 1)
end
```
4.  The recursive code is:
   ```text
   def print_numbers(item)
    if item.is_a?(Numeric)
        puts item
    else
        item.each do |element|
            print_numbers(element)
        end
    end
end
 ```
## Link
https://drive.google.com/file/d/1mvMC1wjQQYPFFPvoWpjQhMy6Kw1iLC3_/view?usp=sharing
