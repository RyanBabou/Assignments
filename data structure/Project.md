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
