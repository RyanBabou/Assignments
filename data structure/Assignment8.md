# Assignment 8
### Task
1.

```text
        1
         \
          5
         / \
        2   9
        \   /\
         4 6  10
        /   \
       3     8
```
2. The maximum number of steps it would take to search for a value is 10 steps because log_2(1000)=9.9 
3.
```text
function findMax(root):
    if root is null:
        return null
    node = root
    while node.right is not null:
        node = node.right
    return node.value
```
4.
```text
#include <iostream>
#include <vector>
using namespace std;
class Node {
public:
    int val;
    Node* left;
    Node* right;
    Node(int v) : val(v), left(nullptr), right(nullptr) {}
};

Node* insert(Node* root, int v) {
    if (root == nullptr) {
        return new Node(v);
    }
    if (v < root->val) {
        root->left = insert(root->left, v);
    } else {
        root->right = insert(root->right, v);
    }
    return root;
}
int main() {
    vector<int> a = {1, 5, 9, 2, 4, 10, 6, 3, 8};
    Node* root = nullptr;

    for (int x : a) {
        root = insert(root, x);
    }
    cout << "Binary search tree built successfully." << endl;
    return 0;
}
```
## link
