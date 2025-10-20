# Assignment 8
## Task
1.           ┌── 10
│       ┌── 9
│       │   │   ┌── 8
│       │   └── 6
│   ┌── 5
│   │   │   ┌── 4
│   │   │   │   └── 3
│   │   └── 2
└── 1
2. 
⌈log_2 1000⌉=10 steps (worst case).
3. 
function findMax(root):
    if root is null:
        return null  // or error/indicator for empty tree
    node = root
    while node.right is not null:
        node = node.right
    return node.value
4.
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

// (Optional) simple inorder print to verify structure; not required for insertion-only
void inorder(Node* root) {
    if (!root) return;
    inorder(root->left);
    cout << root->value << " ";
    inorder(root->right);
}

int main() {
    int arr[] = {1, 5, 9, 2, 4, 10, 6, 3, 8};
    int n = sizeof(arr) / sizeof(arr[0]);

    Node* root = nullptr;
    for (int i = 0; i < n; ++i) {
        root = insert(root, arr[i]);
    }

    // (Optional) check: should print in sorted order: 1 2 3 4 5 6 8 9 10
    // inorder(root); cout << "\n";

    return 0;
}
