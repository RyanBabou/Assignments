# Assignment 7
## Task
1.
   #include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
};
Node* head = nullptr;

void addAtStart(int value) {
    Node* newNode = new Node;
    newNode->data = value;
    newNode->next = head;
    head = newNode;
    cout << "Added " << value << " at the start.\n";
}
void deleteAtStart() {
    Node* temp = head;
    cout << "Deleted " << temp->data << " from the start.\n";
    head = head->next;
    delete temp;
}

void printList() {
    cout << "Current list: ";
    Node* current = head;
    while (current != nullptr) {
        cout << current->data << " -> ";
        current = current->next;
    }
    cout << endl;
}

int main() {
    addAtStart(5);
    addAtStart(15);
    addAtStart(25);
    addAtStart(35);
    printList();
    deleteAtStart();
    printList();
    return 0;
}
## link
https://drive.google.com/file/d/1gdA514eQccn3gdnwazICovMLIQlu2RdX/view?usp=sharing
