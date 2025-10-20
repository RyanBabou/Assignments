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
2. The maximum number of steps it would take to search for a value within is 10 steps because log_2(1000)=9.9 which we can round to 10
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
struct Node {
    int val;
    Node* left;
    Node* right;
    Node(int v): val(v), left(nullptr), right(nullptr) {}
};

Node* insert(Node* root, int v) {
    if (!root) return new Node(v);
    if (v < root->val) root->left = insert(root->left, v);
    else               root->right = insert(root->right, v);
    return root;
}

int main() {
    vector<int> a = {1, 5, 9, 2, 4, 10, 6, 3, 8};
    Node* root = nullptr;
    for (int x : a) root = insert(root, x);
    auto printInOrder = [&](auto&& self, Node* n) -> void {
        if (!n) return;
        self(self, n->left);
        cout << n->val << " ";
        self(self, n->right);
    };
    printInOrder(printInOrder, root);
    cout << "\n";
    return 0;
}

```
