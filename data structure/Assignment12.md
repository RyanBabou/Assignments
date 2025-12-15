# Assignment 12
## Task
1. The base case function is
   ```text
    if (low > high) return;
   ```
 2. The function will keep recursing into negative numbers and never stop. At some point it will cause a stack overflow error. 
3.   the fixed code is:
   
   ```text
   int sum(int low, int high) {
    if (high < low) return 0;
    return high + sum(low, high - 1);
}
```
4.  The recursive code is:
   ```text
   #include <iostream>
#include <vector>
#include <variant>

using namespace std;

using Item = variant<int, vector<variant<int, vector<Item>>>>; // forward recursion workaround
using Array = vector<Item>;

void print_numbers(const Array& arr) {
    for (const auto& element : arr) {
        if (holds_alternative<int>(element)) {
            cout << get<int>(element) << endl;
        } else {
            print_numbers(get<Array>(element));
        }
    }
}
 ```
## Link
https://drive.google.com/file/d/1iYLzuBZBSK0zeOQ1TorCOgNzvwtkAAs4/view?usp=sharing
