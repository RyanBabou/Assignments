# Assignment 8
### Task
1.

```text
        1
         \
          5
           \
            9
           /
          2
           \
            4
             \
              10
             /
            6
           /
          3
           \
            8
```
2. The maximum number of steps it would take to search for a value within is 10 steps because log_2(1000)=10
3.
'''text
function findMax(root):
    if root is null: 
        return null
    node = root
    while node.right is not null:
        node = node.right
    return node.value
'''
4.
'''text
#include <iostream>
using namespace std;

struct Node {
    int value;
    Node* left;
    Node* right;
    Node(int v) : value(v), left(nullptr), right(nullptr) {}
};

Node* insert(Node* root, int x) {
    if (root == nullptr) {
        return new Node(x);
    }
    Node* cur = root;
    while (true) {
        if (x < cur->value) {
            if (cur->left == nullptr) {
                cur->left = new Node(x);
                break;
            } else {
                cur = cur->left;
            }
        } else {
            if (cur->right == nullptr) {
                cur->right = new Node(x);
                break;
            } else {
                cur = cur->right;
            }
        }
    }
    return root;
}

int main() {
    int arr[] = {1, 5, 9, 2, 4, 10, 6, 3, 8};
    int n = sizeof(arr) / sizeof(arr[0]);

    Node* root = nullptr;
    for (int i = 0; i < n; ++i) {
        root = insert(root, arr[i]);
    }

    return 0;
}
'''
