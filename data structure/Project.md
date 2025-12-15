# Project
## Task 1
```text
    #include <iostream>
#include <vector>
#include <string>
#include <unordered_set>

using namespace std;

struct Player {
    string first_name;
    string last_name;
    string team;
};
vector<string> findCommonPlayers(const vector<Player>& basketball,
                                 const vector<Player>& football) {
    unordered_set<string> names;
    vector<string> result;
    for (const auto& p : basketball) {
        names.insert(p.first_name + " " + p.last_name);
    }
    for (const auto& p : football) {
        string fullName = p.first_name + " " + p.last_name;
        if (names.count(fullName)) {
            result.push_back(fullName);
        }
    }
    return result;
}
int main() {
    vector<Player> basketball_players = {
        {"Jill", "Huang", "Gators"},
        {"Janko", "Barton", "Sharks"},
        {"Wanda", "Vakulskas", "Sharks"},
        {"Jill", "Moloney", "Gators"},
        {"Luuk", "Watkins", "Gators"}
    };

    vector<Player> football_players = {
        {"Hanzla", "Radosti", "32ers"},
        {"Tina", "Watkins", "Barleycorns"},
        {"Alex", "Patel", "32ers"},
        {"Jill", "Huang", "Barleycorns"},
        {"Wanda", "Vakulskas", "Barleycorns"}
    };

    vector<string> commonPlayers =
        findCommonPlayers(basketball_players, football_players);

    for (const auto& name : commonPlayers) {
        cout << name << endl;
    }
    return 0;
}
```
## Task 2
```text
#include <iostream>
#include <vector>

using namespace std;

// Function to find the missing number
int findMissingNumber(const vector<int>& nums) {
    int n = nums.size();

    // Sum of numbers from 0 to n
    int expectedSum = n * (n + 1) / 2;

    int actualSum = 0;
    for (int num : nums) {
        actualSum += num;
    }

    return expectedSum - actualSum;
}

int main() {
    vector<int> example1 = {2, 3, 0, 6, 1, 5};
    vector<int> example2 = {8, 2, 3, 9, 4, 7, 5, 0, 6};

    cout << findMissingNumber(example1) << endl; // 4
    cout << findMissingNumber(example2) << endl; // 1

    return 0;
}
```
## Task 3
```text
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int maxProfit(const vector<int>& prices) {
    if (prices.empty()) return 0;

    int minPrice = prices[0];
    int maxProfit = 0;

    for (int i = 1; i < prices.size(); i++) {
        minPrice = min(minPrice, prices[i]);
        maxProfit = max(maxProfit, prices[i] - minPrice);
    }

    return maxProfit;
}
int main() {
    vector<int> prices = {10, 7, 5, 8, 11, 2, 6};

    cout << maxProfit(prices) << endl; 

    return 0;
}
```
## Task 4
```text
#include <iostream>
#include <vector>
#include <climits>
using namespace std;
int highestProduct(const vector<int>& nums) {
    int max1 = INT_MIN, max2 = INT_MIN;
    int min1 = INT_MAX, min2 = INT_MAX;

    for (int num : nums) {
        if (num > max1) {
            max2 = max1;
            max1 = num;
        } else if (num > max2) {
            max2 = num;
        }
        if (num < min1) {
            min2 = min1;
            min1 = num;
        } else if (num < min2) {
            min2 = num;
        }
    }
    return max(max1 * max2, min1 * min2);
}
int main() {
    vector<int> nums = {5, -10, -6, 9, 4};
    cout << highestProduct(nums) << endl; 
    return 0;
}

```
## Task 5
```text
#include <iostream>
#include <vector>

using namespace std;

// Function to sort temperature readings in O(N)
vector<double> sortTemperatures(const vector<double>& temps) {
    const int RANGE = 21; // 97.0 to 99.0 inclusive, step 0.1
    vector<int> counts(RANGE, 0);

    // Count occurrences
    for (double temp : temps) {
        int index = static_cast<int>((temp - 97.0) * 10);
        counts[index]++;
    }

    // Rebuild sorted result
    vector<double> sortedTemps;
    for (int i = 0; i < RANGE; i++) {
        while (counts[i] > 0) {
            sortedTemps.push_back(97.0 + i * 0.1);
            counts[i]--;
        }
    }

    return sortedTemps;
}

int main() {
    vector<double> temps = {
        98.6, 98.0, 97.1, 99.0, 98.9,
        97.8, 98.5, 98.2, 98.0, 97.1
    };

    vector<double> sorted = sortTemperatures(temps);

    for (double t : sorted) {
        cout << t << " ";
    }

    return 0;
}
```
## Task 6
```text
#include <iostream>
#include <vector>
#include <unordered_set>

using namespace std;

// Function to find the length of the longest consecutive sequence
int longestConsecutive(const vector<int>& nums) {
    unordered_set<int> numSet(nums.begin(), nums.end());
    int longest = 0;

    for (int num : numSet) {
        // Only start counting if this is the beginning of a sequence
        if (!numSet.count(num - 1)) {
            int currentNum = num;
            int currentLength = 1;

            while (numSet.count(currentNum + 1)) {
                currentNum++;
                currentLength++;
            }

            longest = max(longest, currentLength);
        }
    }

    return longest;
}

int main() {
    vector<int> nums1 = {10, 5, 12, 3, 55, 30, 4, 11, 2};
    vector<int> nums2 = {19, 13, 15, 12, 18, 14, 17, 11};

    cout << longestConsecutive(nums1) << endl; // Expected output: 4
    cout << longestConsecutive(nums2) << endl; // Expected output: 5

    return 0;
}
```
