# Assignment 11
## Task
1. Dijkstra’s algorithm fails on negative weights because it assumes that once a vertex’s shortest distance is picked, that distance cannot be improved later. For example, if a graph has edges A to B = 1, A to C = 4, and B to C = −3, the shortest path from A to C is A to  B to  C with a total cost of 1 + (−3) = −2. But Dijkstra would choose the direct path A to C with cost 4 and finalize C before checking the path through B. Since the algorithm never rechecks a vertex once it is marked as final, it cannot update C’s distance to the correct value of −2. This is why Dijkstra gives the wrong result when negative weights exist.
## link
