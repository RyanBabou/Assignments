# Assignment 5
## Task
1.
#include <iostream>
#include <unordered_map>
using namespace std;
int main() {
    int arr[] = {200, 400, 100, 50, 350};
    int n = 5;
    unordered_map<int, bool> hashTable;
    for (int i = 0; i < n; i++) {
        hashTable[arr[i]] = true;
    }
    int key = 100;
    if (hashTable.find(key) != hashTable.end()) {
        cout << key << " found!" << endl;
    } else {
        cout << key << " not found!" << endl;
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
3.
