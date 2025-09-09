# Assignment 2
## Questions
1. How many steps would it take to perform a linear search for the number 8 in the ordered array, [2, 4, 6, 8, 10, 12, 13]?
   it takes 4 steps to perform a linear search for the number 8 in the ordered array.
2. How many steps would binary search take for the previous example?
   it would take 2 steps for the binaery search to take for the previous example.
3. What is the maximum number of steps it would take to perform a binary search on an array of size 100,000?
   it would take 17 steps as maximum number of steps it would take to perform a binary search on an array of size 100,000
4. Write a C++ code that implements the linear and binary search algorithms. The algorithm should be able to calculate the number of steps against the given search?
   link to the code is here.
   ''' C++
   #include <iostream>
using namespace std;
// Linear Search
int linearSearch(int arr[], int n, int numtofind, int &steps) {
    steps = 0;
    for (int i = 0; i < n; i++) {
        steps++;
        if (arr[i] == numtofind) {
            return i; 
        }
    }
    return -1; 
}
// Binary Search 
int binarySearch(int arr[], int n, int numtofind, int &steps) {
    int left = 0, right = n - 1;
    steps = 0;
    while (left <= right) {
        int mid = (left + right) / 2;
        steps++;
        if (arr[mid] == numtofind) return mid;
        if (arr[mid] < numtofind)
            left = mid + 1;
        else
            right = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = {1, 7, 12, 19, 23, 34, 45, 56, 78};
    int n = sizeof(arr) / sizeof(arr[0]);

    int numtofind;
    cout << "plug in a number to search: ";
    cin >> numtofind;

    int stepsL, stepsB;

    cout << "\n--- Results ---\n";

    if (linearSearch(arr, n, numtofind, stepsL) != -1)
        cout << "The amount of steps it took the linear search to find your number is: " << stepsL << "\n";
    else 
        cout << "the linear search didn't find your number and the steps are:" << stepsL << "\n";

    if (binarySearch(arr, n, numtofind, stepsB) != -1)
        cout << "he amount of steps it took the binary search to find your number is:" << stepsB << "\n";
    else
        cout << "the binary search didn't find your number and the steps are:" << stepsB << "\n";

    return 0;
}

## video link 
https://drive.google.com/file/d/1ol0ruRkZHhVs-Iox_LTgbPIFI1_4nXyk/view?usp=sharing
