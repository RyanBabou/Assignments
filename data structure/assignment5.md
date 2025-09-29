# Assignment 5
## Task
### 1.
#include <bits/stdc++.h>
using namespace std;
int main() {
vector<int> arr = {200, 400, 100, 50, 350};
unordered_set<int> s(arr.begin(), arr.end());
vector<int> queries = {50, 125, 350};
for (int q : queries) {
bool found = s.find(q) != s.end();
cout << q << (found ? " -> found" : " -> not found") << "\n";
}
return 0;
}'''
### 2.
#include <bits/stdc++.h>
using namespace std;
int main(){
string name = "Ryan Babou"; // ← replace with your exact full name if needed
size_t h = hash<string>{}(name); // implementation-defined hash
cout << name << " -> hash = " << h << "\n";
return 0;
}'''
### 3.

