# Assignment 5
## Task
### 1.
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> array = {200, 400, 100, 50, 350};


    unordered_set<int> H(array.begin(), array.end());
    vector<int> queries = {50, 999, 200, 351};
    for (int q : queries) {
        bool found = H.find(q) != H.end(); // average O(1)
        cout << q << (found ? " found" : " not found") << "\n";
    }
    return 0;
}
### 2.
#include <bits/stdc++.h>
using namespace std;

int main() {
    string name = "Ryan Babou";
    size_t hv = hash<string>{}(name);
    cout << "hash(\"" << name << "\") = " << hv << "\n";
    return 0;
}
```
### 3.

