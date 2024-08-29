# DFS

Depth-First Search (DFS) is a graph traversal algorithm that explores a graph by starting at a root node and exploring as far as possible along each branch before backtracking. This approach dives deep into the graph's structure before moving to another branch.


Graph Representation:
A graph G consists of a set of nodes (or vertices) V and a set of edges E that connect pairs of nodes. A graph can be directed or undirected.
G = (V, E)

The graph is typically represented using an adjacency list, where each node u in V has a list of neighbors:
Adj[u] = {v | (u, v) is in E}


DFS can be implemented using either recursion or an explicit stack.

Recursive DFS:
Start: Begin at a specified starting node s.
Mark as Visited: Mark the current node as visited to avoid revisiting it.
Explore: Recursively visit all unvisited neighbors of the current node.
Backtrack: When all neighbors are visited, backtrack to the previous node and continue the exploration.

Iterative DFS:
Stack: Use a stack to manage the exploration of nodes.
Push: Push the starting node onto the stack.
Pop: Pop the top node from the stack and visit it.
Push Neighbors: Push all unvisited neighbors of the current node onto the stack.
Repeat: Continue until the stack is empty.


Recursive DFS:
procedure DFS(G, u, visited):
    visited[u] = true
    for each v in Adj[u]:
        if not visited[v]:
            DFS(G, v, visited)
            
Iterative DFS:
procedure DFS_iterative(G, s):
    let S be a stack
    S.push(s)
    while S is not empty:
        u = S.pop()
        if u is not visited:
            visit(u)
            mark u as visited
            for each v in Adj[u]:
                if not visited[v]:
                    S.push(v)
                    
Time Complexity:
The time complexity of DFS is O(V + E), where V is the number of nodes and E is the number of edges. This is because each node and edge is explored exactly once.

Applications:
Pathfinding: DFS can be used to find paths between two nodes in a graph.
Cycle Detection: DFS can be used to detect cycles in a graph.
Topological Sorting: In directed acyclic graphs (DAGs), DFS can be used to perform a topological sort.
Connected Components: DFS can help identify connected components in an undirected graph.
