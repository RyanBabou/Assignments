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
#include <iostream>
#include <string>
using namespace std;
int main() {
    string name = "Ryan";
    hash<string> hash_fn;
    size_t hash_value = hash_fn(name);
    cout << "Hash value of " << name << " is: " << hash_value << endl;
    return 0;
}
### 3.

