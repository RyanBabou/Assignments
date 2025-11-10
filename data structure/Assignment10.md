# Assignment 10
## Task
1.
    
```text
    A
   / \
  B   C
 / \   \
D   E---F
     \
      G

```
2.

```text
#include <iostream>
#include <queue>
#include <stack>
using namespace std;
const int N = 7;
int graphMat[N][N];
bool visited[N];
int id(char c) { return c - 'A'; }
char nameOf(int i) { return char('A' + i); }
void resetVisited() {
    for (int i = 0; i < N; i++) visited[i] = false;
}
void addEdge(char u, char v) {
    int a = id(u);
    int b = id(v);
    graphMat[a][b] = 1;
    graphMat[b][a] = 1;
}
void BFS(char start) {
    resetVisited();
    queue<int> q;
    int s = id(start);
    visited[s] = true;
    q.push(s);
    cout << "BFS from " << start << ":";
    while (!q.empty()) {
        int u = q.front();
        q.pop();
        cout << " " << nameOf(u);
        for (int v = 0; v < N; v++) {
            if (graphMat[u][v] && !visited[v]) {
                visited[v] = true;
                q.push(v);
   }
   }
    }
    cout << endl;
}
void DFS_iter(char start) {
    resetVisited();
    stack<int> st;
    st.push(id(start));
cout << "DFS from " << start << " (iterative):";
while (!st.empty()) {
int u = st.top();
st.pop();
if (visited[u]) continue;
visited[u] = true;
cout << " " << nameOf(u);
 for (int v = N - 1; v >= 0; v--) {
  if (graphMat[u][v] && !visited[v]) {
   st.push(v);
            }
        }
    }
    cout << endl;
}
void DFS_rec_help(int u) {
    visited[u] = true;
    cout << " " << nameOf(u);
    for (int v = 0; v < N; v++) {
        if (graphMat[u][v] && !visited[v]) {
            DFS_rec_help(v);
        }
    }
}
void DFS_rec(char start) {
    resetVisited();
    cout << "DFS from " << start << " (recursive):";
    DFS_rec_help(id(start));
    cout << endl;
}
int main() {
    addEdge('A', 'B');
    addEdge('A', 'C');
    addEdge('B', 'D');
    addEdge('B', 'E');
    addEdge('C', 'F');
    addEdge('E', 'F');
    addEdge('E', 'G');
    BFS('A');
    DFS_iter('A');
    DFS_rec('A');
    return 0;
}
```
3.  BFS and DFS run in O(V+E) time because they check every vertex and they examine each edge at most once, they both use O(V) with BFS storing discovered vertices in a queue and DFS storing them in a stack or recursion path.
## Link

