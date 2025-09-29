# Assignment 5
## Task
## 1.
#include <iostream>
#include <unordered_map>
#include <vector>
using namespace std;
int main() {
vector<int> arr = {200, 400, 100, 50, 350};
unordered_map<int, bool> MedicalRecord;
for (int x : arr) {
MedicalRecord[x] = true;
}
int q = 400;
if (MedicalRecord.count(q))
cout << q << " found" << endl;
else
cout << q << " not found" << endl;

return 0;
}
## 2.
#include <iostream>
#include <string>
#include <functional>
using namespace std;
int main(){
string name = "Ryan Babou";
size_t h = hash<string>{}(name); 
cout << name << " -> hash = " << h << endl;
return 0;
}
## 3.

| Index | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   |
|-------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| Value | 200 | T   | ⋄   | ⋄   | ⋄   | 50  | 350 | ⋄   | 400 | ⋄   |

T = Tombstone

Introducing the tombstone makes the searches slower because the probe has to keep checking past deleated cells instead pof stopping right away.
