# Assignment 5
## Task
### 1.
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
### 2.
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
### 3.

