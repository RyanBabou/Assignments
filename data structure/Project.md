# Project
1.
```text
    struct Player {
    string first_name;
    string last_name;
    string team;
};

vector<string> playersInBothSports(const vector<Player>& a, const vector<Player>& b) {
    unordered_set<string> names;
    vector<string> result;

    for (const auto& p : a)
        names.insert(p.first_name + " " + p.last_name);

    for (const auto& p : b) {
        string full = p.first_name + " " + p.last_name;
        if (names.count(full))
            result.push_back(full);
    }

    return result;
}
```
2.
```text
int findMissing(const vector<int>& nums) {
    int n = nums.size();
    long long expected = (long long)n * (n + 1) / 2;
    long long actual = 0;

    for (int x : nums) actual += x;
    return expected - actual;
}
```
3.
```text
int maxProfit(const vector<int>& prices) {
    if (prices.empty()) return 0;

    int minPrice = prices[0];
    int maxProfit = 0;

    for (int price : prices) {
        minPrice = min(minPrice, price);
        maxProfit = max(maxProfit, price - minPrice);
    }

    return maxProfit;
}

```
4.
```text
int highestProduct(const vector<int>& nums) {
    int max1 = INT_MIN, max2 = INT_MIN;
    int min1 = INT_MAX, min2 = INT_MAX;

    for (int x : nums) {
        if (x > max1) { max2 = max1; max1 = x; }
        else if (x > max2) max2 = x;

        if (x < min1) { min2 = min1; min1 = x; }
        else if (x < min2) min2 = x;
    }

    return max(max1 * max2, min1 * min2);
}

```
5.
```text
vector<double> sortTemps(const vector<double>& temps) {
    const int size = 21; 
    int count[size] = {0};

    for (double t : temps) {
        int idx = (int)((t - 97.0) * 10);
        count[idx]++;
    }

    vector<double> sorted;
    for (int i = 0; i < size; i++) {
        double value = 97.0 + (i * 0.1);
        while (count[i]--)
            sorted.push_back(value);
    }

    return sorted;
}
```
6.
```text
int longestConsecutive(const vector<int>& nums) {
    unordered_set<int> s(nums.begin(), nums.end());
    int longest = 0;

    for (int x : nums) {
        if (!s.count(x - 1)) { 
            int current = x;
            int length = 1;

            while (s.count(current + 1)) {
                current++;
                length++;
            }

            longest = max(longest, length);
        }
    }

    return longest;
}
```
